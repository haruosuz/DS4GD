[生命動態のデータサイエンス](https://github.com/haruosuz/DS4GD)

----------

# Case Study
ケーススタディ

- [NCBI Genome List](#ncbi-genome-list)
- [NCBI assembly summary refseq](#ncbi-assembly-summary-refseq)
- [NCBI assembly summary genbank](#ncbi-assembly-summary-genbank)
- [UniProtKB Swiss-Prot protein sequence database](#uniprotkb-swiss-prot-protein-sequence-database)

### 手順

1. [ターミナル](http://techacademy.jp/magazine/5155)を開く。
2. Download: データを[`wget`](http://blog.layer8.sh/ja/2012/03/31/wget_command/)または[`curl`](https://ja.wikipedia.org/wiki/CURL)コマンドでダウンロードする。データの説明（いつ・どこからダウンロードしたのか、日付やウェブサイトのURL等）を記録する。
3. Inspecting Data: データをUnixコマンドで調査する。
4. Working with Data in R: データをR言語で解析・視覚化する。

----------

## NCBI Genome List
ゲノム解読プロジェクト一覧
NCBI [Genome List](http://www.ncbi.nlm.nih.gov/genome/browse/)  

### Website
[National Center for Biotechnology Information](http://www.ncbi.nlm.nih.gov)右下[NCBI FTP Site](ftp://ftp.ncbi.nlm.nih.gov/)を開き、[genomes](ftp://ftp.ncbi.nlm.nih.gov/genomes/)/[GENOME_REPORTS](ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/)に移動する。
例えば、*README*ファイルを右クリックし、「リンクのURLをコピー (Copy Link)」する。

### Download

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開く。

プロジェクト・ディレクトリを作成し移動する:  

    mkdir -p ~/projects/ncbiGenomeList/data
    cd ~/projects/ncbiGenomeList/data/

`curl`コマンドでファイル*README, overview.txt*をダウンロードする:  

    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/README
    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/overview.txt

または

`wget`コマンドでファイル*README, .txt*をダウンロードする:  

    wget ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/{README,*.txt}

### Inspecting Data

変数に値を割り当てる（`=`の前後にスペースを入れない）:  

    DB='overview.txt'

変数の値にアクセスするには、変数名の前にドル記号を付ける（`$DB`）:  

    echo $DB

`ls -l`でファイルの詳細情報を表示する:  

    ls -l $DB

`head`で先頭部分を表示する。ファイルの一行目（列ラベル）を表示する:  

    head -n 1 $DB

ファイルのジカウイルス（'Zika virus'）にマッチする行を抽出する:  

    grep 'Zika virus' $DB

ファイルの一行目（列ラベル）とジカウイルス（'Zika virus'）にマッチする行を抽出し、`output.txt`ファイルへ出力する:  

    head -n 1 $DB > output.txt
    grep 'Zika virus' $DB >> output.txt

原核生物ゲノム解読プロジェクト・リスト(`prokaryotes.txt`)を用いる。

大腸菌(Escherichia coli)のゲノム解読の状況(Status)を確認する:  

    grep 'E.*coli' prokaryotes.txt | cut -f19 | sort | uniq -c

大腸菌(Escherichia coli)の'Complete Genome'配列の情報 Size (Mb), GC%, Genes, Proteins, Pubmed ID を抽出する:  

    head -n 1 prokaryotes.txt | cut -f1,7-8,15-16,25 > output.txt
    grep 'E.*coli.*Complete' prokaryotes.txt | cut -f1,7-8,15-16,25 >> output.txt

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    setwd('~/projects/ncbiGenomeList/data/')
    getwd()
    dir()

`read.table`関数で、データのインポート。タブ区切りファイル"prokaryotes.txt"を読み込む:  

    d.f <- read.delim("prokaryotes.txt", stringsAsFactors=FALSE, na.strings="-", check.names=FALSE)

    dim(d.f)
    head(d.f)
    colnames(d.f)
    colnames(d.f)[1] <- 'Organism'

`grep(pattern, x)`は、`pattern`にマッチするベクトル`x`の全要素の番号を返す。
大腸菌(Escherichia coli)を抽出する:  

    i <- grep(pattern='Escherichia.coli', x=d.f$Organism, ignore.case=TRUE)
    d.f <- d.f[i,]

'Complete Genome'を抽出する:  

    i <- grep(pattern='Complete', x=d.f$Status, ignore.case=TRUE)
    d.f <- d.f[i,]

`write.table`関数で、データのエクスポート。タブ区切りファイルとして出力する:  

    write.table(d.f[, c(1,7:8,15:16,25)], file="output.txt", sep="\t", quote=FALSE, row.names=FALSE)

大腸菌ゲノムの特徴 Size (Mb), GC%, Genes, Proteins を調べる。
`summary()`関数でデータの要約:  

    summary(d.f[, c(7:8,15:16)])

`sapply()`関数でリストの各要素に関数を適用し、解析結果をカンマ区切りファイルとして出力する:  

    write.csv(sapply(d.f[, c(7:8,15:16)], summary), file='summary.csv', row.names=TRUE)

`psych`パッケージの`pairs.panels`関数で、ヒストグラム、散布図、相関係数を出力する:  

    # install.packages("psych")
    library(psych)
    pairs.panels(d.f[, c(7:8,15:16)])

## References
- [Nucleic Acids Res. 2015 Jan;43(Database issue):D599-605. "Update on RefSeq microbial genomes resources."](http://www.ncbi.nlm.nih.gov/pubmed/25510495)

----------

## NCBI assembly summary refseq
RefSeqのゲノム配列

### Website
[NCBI Genomes Download FAQ](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/)

### Download

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開く。

    bash

プロジェクト・ディレクトリを作成し移動する:  

    mkdir -p ~/projects/ncbi_assembly_summary/data
    cd ~/projects/ncbi_assembly_summary/data/

ゲノム配列データのFTPディレクトリパス（URL）を記載したファイルを`curl`でダウンロードする:  

    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt

[腸管出血性大腸菌O157](https://ja.wikipedia.org/wiki/O157) [Escherichia coli O157:H7 Sakai](http://genome.bio.titech.ac.jp/bacteria/o157/) の完全ゲノム('Complete Genome')配列データの最新版('latest')のURLを抽出する:  

    NAME="O157.*Sakai"
    grep "$NAME" assembly_summary_refseq.txt
    ftpdirpaths=(`awk -F "\t" '$8 ~ /'"$NAME"'/ && $11=="latest" && $12 ~ /Complete Genome/ {print $20}' assembly_summary_refseq.txt`)

    # 抽出されたURLの数を確認する:  
    echo ${#ftpdirpaths[@]}

    # 抽出されたURLを表示する:  
    echo ${ftpdirpaths[@]}

抽出されたURL <ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF_000008865.1_ASM886v1> をブラウザ（FirefoxまたはChrome）で開く。

	拡張子		データファイルの内容  
	fna.gz		FASTA Nucleic Acids - ゲノム塩基配列  
	faa.gz		FASTA Amino Acids - 各タンパク質のアミノ酸配列  

[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式の圧縮ファイル（*.faa.gz*, *.fna.gz*）を`wget`または`curl`でダウンロードする。

*GCF_000008865.1_ASM886v1_genomic.fna.gz, GCF_000008865.1_ASM886v1_protein.faa.gz* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

`curl`でダウンロード:  

    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF_000008865.1_ASM886v1/GCF_000008865.1_ASM886v1_genomic.fna.gz
    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF_000008865.1_ASM886v1/GCF_000008865.1_ASM886v1_protein.faa.gz

または

`wget`でダウンロード:  

    for URL in ${ftpdirpaths[@]}
    do
      wget $URL/{*.faa.gz,*.fna.gz}    done

### Inspecting Data

`ls -l`でファイルの詳細情報を表示する:  

    ls -l

`ls -lh`でファイルサイズを確認する:  

    ls -lh

`gunzip`コマンドで解凍する:  

    for FILE in *.gz; do gunzip -c $FILE > $(basename $FILE .gz); done
    #gunzip *.gz

`head`コマンドを用いて、ファイルの先頭部分を表示する:  

    head *.fna

`grep`コマンドを用いて、FASTA形式ファイルのヘッダ（`>`で始まる行）を抽出する:  

    grep '^>' *.fna

[パイプ](https://ja.wikipedia.org/wiki/パイプ_%28コンピュータ%29)でプログラムの入出力をつなぐ。

`head`で先頭部分を表示する:  

    grep '^>' *.faa | head

配列エントリ数をカウントする:  

    grep '^>' *.faa | wc -l

配列エントリ数をカウントする:  

    grep -c '^>' *.faa *.fna

[アミノアシルtRNA合成酵素](https://ja.wikipedia.org/wiki/アミノアシルtRNA合成酵素) (aminoacyl-tRNA synthetase/synthase) を対象として、文字列'tRNA synth'にマッチする行を抽出し、カウントする:  

    grep -i 'tRNA synth' *.faa | wc -l

[リボソーム](https://ja.wikipedia.org/wiki/リボソーム)タンパク質 ('ribosomal protein') にマッチする行をカウントする:  

    grep -ic 'ribosomal protein' *.faa

`grep`コマンドは、`-c`オプションでパターンにマッチした行数を表示し、`-i`オプションで大文字小文字を区別しない（ignore case）。

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    setwd('~/projects/ncbi_assembly_summary/data/')
    getwd()
    dir()

[パッケージ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/08.html)`seqinr`を呼び出す:  

    library(seqinr)

#### [DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.org/en/latest/src/chapter1.html)

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data into R
    ld <- read.fasta(file = 'GCF_000008865.1_ASM886v1_genomic.fna.gz', seqtype = c('DNA'), strip.desc = TRUE)

変数`ld`は[リスト](http://stat.biopapyrus.net/vector/list.html)。

配列の数をカウントする:  

    length(ld)

`getAnnot`関数を用いて、配列のアノテーションを取得する:  

    getAnnot(ld)

1個の染色体(chromosome)と2個のプラスミド(plasmid)を含む。

変数`dna`にリストの1番目の要素を代入する:  

    dna <- ld[[1]]

DNA配列の長さ:  

    length(dna)

DNA配列の塩基組成:  

    table(dna)

DNA配列のGC含量:  

    GC(dna)

`summary()`関数でデータの要約:  

    summary(dna)

DNA配列の長さ(length)、塩基組成(composition)、GC含量(GC)が出力される。

2連続塩基含量:  

    count(dna, 2)

#### [DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.org/en/latest/src/chapter2.html)

GC含量の局所変動:  

    # install.packages('zoo')
    library(zoo)
    windowsize <- 100000
    x <- seq(from = 1, to = length(dna)-windowsize, by = windowsize)
    y <- rollapply(data = dna, width = windowsize, by = windowsize, FUN = GC)
    plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")

2連続塩基組成（観測値/期待値）:  

    rho(dna, wordsize = 2)
    
    par(cex=0.7); barplot(sort(rho(dna, wordsize = 2))); abline(h=1)

配列間の2連続塩基組成プロファイルを比較する。
全ての配列 [1個の染色体(chromosome)と2個のプラスミド(plasmid)] について、2連続塩基組成を求める。
`sapply()`関数は、リストの各要素に関数を適用する:  

    X <- sapply(ld, rho)

`matplot()`関数でプロットする:  

    matplot(X, type="l", col=1:ncol(X), lty=1:ncol(X))
    legend("topleft", legend=colnames(X), col=1:ncol(X), lty=1:ncol(X))

[クラスター分析](https://github.com/haruosuz/DS4GD/blob/master/hclust.md)

    plot(hclust(dist(t(X))))

[ヒートマップ](https://github.com/haruosuz/DS4GD/blob/master/hclust.md#heat-map)

    heatmap(t(X))

### References
- [NCBI Genomes Download FAQ](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/)
 - [9. How can I find the sequence and annotation of my genome of interest?](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#howtofind) Using the assembly summary files for bacteria or a species under genbank or refseq
 - [12. How can I download RefSeq data for all complete bacterial genomes?](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#allcomplete)
- [What is the difference between RefSeq and GenBank?](http://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)

----------

## NCBI assembly summary genbank
GenBankのゲノム配列

### Website
[NCBI Genomes Download FAQ](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/)

### Download
![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開く。

    bash

プロジェクト・ディレクトリを作成し移動する:  

    mkdir -p ~/projects/ncbi_assembly_summary/data
    cd ~/projects/ncbi_assembly_summary/data/

ゲノム配列データのFTPディレクトリパス（URL）を記載したファイルを`curl`でダウンロードする:  

    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_genbank.txt

アブラムシ細胞内共生細菌ブフネラ Buchnera aphidicola str. APS (Acyrthosiphon pisum) のゲノム配列データの最新版（'latest'）のURLを抽出し、確認する:  

    ftpdirpaths=(`awk -F "\t" '$8 ~ /Buchnera aphidicola str. APS/ && $11=="latest" {print $20}' assembly_summary_genbank.txt`)
    echo ${#ftpdirpaths[@]}
    echo ${ftpdirpaths[@]}

抽出されたURL <ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA_000009605.1_ASM960v1> をブラウザ（FirefoxまたはChrome）で開く。

*GCA_000009605.1_ASM960v1_genomic.fna.gz, GCA_000009605.1_ASM960v1_protein.faa.gz* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

`curl`でダウンロード:  

    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA_000009605.1_ASM960v1/GCA_000009605.1_ASM960v1_genomic.fna.gz
    curl -O ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA_000009605.1_ASM960v1/GCA_000009605.1_ASM960v1_protein.faa.gz

----------

## UniProtKB Swiss-Prot protein sequence database
[Swiss-Prot](https://ja.wikipedia.org/wiki/Swiss-Prot)タンパク質配列データベース

### Website
[UniProt](http://www.uniprot.org)の[Download latest release](http://www.uniprot.org/downloads)を開く。
<ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/> をブラウザ（Firefox または Chrome）で開く。
*uniprot_sprot.fasta.gz* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

### Download

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開く。

プロジェクト・ディレクトリを作成し移動する:  

    mkdir -p ~/projects/uniprot_sprot/data
    cd ~/projects/uniprot_sprot/data/

[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式の圧縮ファイル（*uniprot_sprot.fasta.gz*）を`wget`または`curl`でダウンロードする:  

    wget ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz
    # or
    curl -O ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz

### Inspecting Data

`ls -l`でファイルの詳細情報を表示する:  

    ls -l

`gunzip`コマンドで解凍する:  

    gunzip -c uniprot_sprot.fasta.gz > uniprot_sprot.fasta

`ls -lh`でファイルサイズを確認する:  

    ls -lh

`head`コマンドを用いて、ファイルの先頭部分を表示する:  

    head uniprot_sprot.fasta

[パイプ](https://ja.wikipedia.org/wiki/パイプ_%28コンピュータ%29)でプログラムの入出力をつなぐ。

[FASTA headers](http://www.uniprot.org/help/fasta-headers)

`grep`コマンドを用いて、FASTAファイルのヘッダ（`>`で始まる行）にマッチする行を抽出し、`head`で先頭部分を表示する:  

    grep '^>' uniprot_sprot.fasta | head

配列の数をカウントする:  

    grep '^>' uniprot_sprot.fasta | wc -l

[アミノアシルtRNA合成酵素](https://ja.wikipedia.org/wiki/アミノアシルtRNA合成酵素) (aminoacyl-tRNA synthetase/synthase) を対象として、文字列'tRNA synth'にマッチする行を抽出し、カウントする:  

    grep 'tRNA synth' uniprot_sprot.fasta | wc -l

[リボソーム](https://ja.wikipedia.org/wiki/リボソーム)タンパク質 ('ribosomal protein') にマッチする行をカウントする:  

    grep -ic 'ribosomal protein' uniprot_sprot.fasta

`grep`コマンドは、`-c`オプションでパターンにマッチした行数を表示し、`-i`オプションで大文字小文字を区別しない（ignore case）。

[ベロ毒素](https://ja.wikipedia.org/wiki/ベロ毒素)([Shiga toxin](https://en.wikipedia.org/wiki/Shiga_toxin)) を検索する。'Shiga'にマッチする行を表示する:  

    grep '^>' uniprot_sprot.fasta | grep 'Shiga'

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    setwd('~/projects/uniprot_sprot/data/')
    getwd()
    dir()

[パッケージ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/08.html)`seqinr`を呼び出す:  

    library(seqinr)

`read.fasta()`関数で配列データを読み込む:  

    ld <- read.fasta(file = 'uniprot_sprot.fasta.gz', seqtype = c('AA'), strip.desc = TRUE)

配列の数をカウントする:  

    length(ld)

- [文字列 | Rを利用して文字列のマッチング,結合,分割,置換を行う関数](http://stat.biopapyrus.net/r/string.html)

`getAnnot`関数を用いて、配列のアノテーションを取得する:  

    annotation <- getAnnot(ld)

`grep(pattern, x)`は、`pattern`にマッチするベクトル`x`の全要素の番号を返す。
'Alpha-actinin-2'にマッチする要素番号を取得:  

    i <- grep(pattern='Alpha-actinin-2', x=annotation, ignore.case=TRUE)

[リスト](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html)の成分を取り出す:  

    ld[i]

`write.fasta()`関数を用いて、配列データをFASTA形式ファイルとして書き出す:  

    write.fasta(sequences=ld[i], names=getName(ld[i]), file.out='myseq.fasta')

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    setwd('~/projects/uniprot_sprot/data/')
    library(seqinr)
    lx <- read.fasta(file = 'myseq.fasta', seqtype = c('AA'), strip.desc = TRUE)
    unlist(getAnnot(lx))

`sapply()`は、リストの各要素に関数を適用する。アミノ酸残基数を求める:  

    sapply(lx, length)

#### [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
ペアワイズ配列アラインメント

[ドットプロットで2つの配列を比較](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#comparing-two-sequences-using-a-dotplot)

    s1 <- lx[[1]]
    s2 <- lx[[3]]
    dotPlot(s1, s2)
    wsize <- 3; dotPlot(s1, s2, wsize=wsize, wstep=wsize, nmatch=wsize, xlab=getName(s1), ylab=getName(s2))

for文でループ処理を行う。複数のドットプロットをファイル出力する:  

    pdf("Rplot.pdf") # create a PDF device called Rplot.pdf
    for (n1 in 1:length(lx)) {
      for (n2 in n1:length(lx)) {
        s1 <- lx[[n1]]
        s2 <- lx[[n2]]
        dotPlot(s1, s2, xlab=getName(s1), ylab=getName(s2))
      }
    }
    dev.off(which = dev.cur()) # close the device

[2つのタンパク質配列間のグローバル・アライメント](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-global-alignment-of-protein-sequences-using-the-needleman-wunsch-algorithm)

    # Biostringsパッケージの呼び出し
    library(Biostrings)
    # データ(置換行列)のロード
    data(BLOSUM50)

    # 文字ベクトルを文字列に変換（大文字に変換）し、pairwiseAlignment
    aln_global <- pairwiseAlignment(toupper(c2s(s1)), toupper(c2s(s2)), substitutionMatrix = BLOSUM50, gapOpening = -2, gapExtension = -8, scoreOnly = FALSE)
    aln_global
    writePairwiseAlignments(aln_global)
    writePairwiseAlignments(aln_global, file="aln_global.txt")

[2つのタンパク質配列間のローカル・アライメント](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-local-alignment-of-protein-sequences-using-the-smith-waterman-algorithm)

    aln_local <- pairwiseAlignment(toupper(c2s(s1)), toupper(c2s(s2)), substitutionMatrix = BLOSUM50, gapOpening = -2, gapExtension = -8, scoreOnly = FALSE, type="local")
    aln_local
    writePairwiseAlignments(aln_local, file="aln_local.txt")

#### [Multiple sequence alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_msa#multiple-sequence-alignment)
多重配列アライメント (多重整列) 

    library(Biostrings)
    aaseq <- readAAStringSet(file = 'myseq.fasta')

    library(msa)    aln <- msa(aaseq, method="Muscle")
    aln

    # 多重配列アライメントをファイル出力
    writeXStringSet(unmasked(aln), file="aln.fasta")

[SeaView](http://www2.tba.t-com.ne.jp/nakada/takashi/phylogeny/seaview2.html)を用いて、FASTA形式ファイルの多重配列アライメントを表示する。

![](http://www2.tba.t-com.ne.jp/nakada/takashi/phylogeny/fig/sv2/sv7.jpg)

[WebLogo](http://blog.amelieff.jp/?eid=210264)を用いて、配列の保存度を表示する。

![](http://blog.amelieff.jp/images/weblogo2.png)

#### [Phylogenetic analysis](https://github.com/haruosuz/r4bioinfo/tree/master/R_msa#phylogenetics)
系統解析 

    library(phangorn) # read.aa # dist.ml

    # アミノ酸配列（FASTA形式ファイル）を読み込む
    aln <- read.aa(file = "aln.fasta", format = "fasta")

    # 配列間の距離を計算
    d <- dist.ml(aln, model="Dayhoff")

    # 近隣結合法 NJ (Neighbor-Joining)
    tre <- nj(d)

    # 系統樹を描画
    plot.phylo(tre, type = "phylogram") # type "phylogram", "cladogram", "fan", "unrooted", "radial"

    # 系統樹をnewick形式でファイル出力
    write.tree(tre, file="myseq.newick")

[SeaView](http://doua.prabi.fr/software/seaview)または[FigTree](http://www.geocities.jp/ancientfishtree/FigTree.html)を用いて、newick形式ファイルの系統樹を表示する。

![](http://en.bio-soft.net/tree/figtree.jpg)

#### Amino acid usage
タンパク質のアミノ酸組成

- [Lobry, J.R., Chessel, D. (2003) Internal correspondence analysis of codon and amino-acid usage in thermophilic bacteria. Journal of Applied Genetics, 44:235-261.](http://pbil.univ-lyon1.fr/members/lobry/repro/jag03/)
- [Lobry JR, Gautier C. Nucleic Acids Res. 1994 Aug 11;22(15):3174-80. 'Hydrophobicity, expressivity and aromaticity are the major trends of amino-acid usage in 999 Escherichia coli chromosome-encoded genes.'](http://www.ncbi.nlm.nih.gov/pubmed/8065933)

`AAstat()`関数を用いて、タンパク質の配列情報（アミノ酸残基数、物理化学的クラスの割合、等電点の理論値）を求める:  

    AAstat(lx[[1]])

アミノ酸の個数を出力:  

    AAstat(lx[[1]], plot = FALSE)$Compo

物理化学的クラス (Tiny, Small, Aliphatic, Aromatic, Non-polar, Polar, Charged, Positive, Negative) のうち、[芳香族アミノ酸](https://ja.wikipedia.org/wiki/芳香族アミノ酸) Aromatic の割合を出力:  

    AAstat(lx[[1]], plot = FALSE)$Prop$Aromatic

`sapply()`関数は、リストの各要素に関数を適用する。複数タンパク質配列の物理化学的クラスの割合を求める:  

    sapply(lx, function(x) AAstat(x, plot=FALSE)$Prop )

複数タンパク質配列のアミノ酸使用の絶対度数と相対度数を求める:  

    # 絶対度数
    sapply(lx, function(x) AAstat(x, plot=FALSE)$Compo )

    # 相対度数
    X <- sapply(lx, function(x) summary(x)$composition )

データをカンマ区切りファイルとして出力する:  

    write.csv(t(X), file="table.csv")
タンパク質のアミノ酸使用パターンを比較する。`matplot()`関数でプロットする:  

    matplot(X, type="l", col=rainbow(12), lty=1:6)
    legend("topleft", legend=colnames(X), col=rainbow(12), lty=1:6)
    # lty: 0=blank, 1=solid (default), 2=dashed, 3=dotted, 4=dotdash, 5=longdash, 6=twodash

[クラスター分析](https://github.com/haruosuz/DS4GD/blob/master/hclust.md)

    plot(hclust(dist(t(X))))

[ヒートマップ](https://github.com/haruosuz/DS4GD/blob/master/hclust.md#heat-map)

    heatmap(t(X))

### References
- [Swiss-Prot - Wikipedia](https://ja.wikipedia.org/wiki/Swiss-Prot)
- [Nucleic Acids Res. 2015 Jan;43(Database issue):D204-12. UniProt: a hub for protein information.](http://www.ncbi.nlm.nih.gov/pubmed/25348405)
- [Database (Oxford). 2014 Mar 12;2014:bau016. Expert curation in UniProtKB: a case study on dealing with conflicting and erroneous data.](http://www.ncbi.nlm.nih.gov/pubmed/24622611)

----------

