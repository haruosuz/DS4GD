[生命動態のデータサイエンス](https://github.com/haruosuz/DS4GD/tree/master/2017)

----------

# Case Study
**ケーススタディ**

目次
- [Molecular Biology](#molecular-biology)
- [Unix commands](#unix-commands)
- [UniProtKB Swiss-Prot protein sequence database](#uniprotkb-swiss-prot-protein-sequence-database)
- [NCBI assembly summary](#ncbi-assembly-summary)
- [Silva rRNA database](#silva-rrna-database)
- [Annotation of promoter sequences](#annotation-of-promoter-sequences)
- [Annotation of Coding sequences](#annotation-of-coding-sequences)

----------
----------

## Molecular Biology

[分子生物学](https://ja.wikibooks.org/wiki/分子生物学)  

RNAとDNA、それぞれの核酸塩基

![https://ja.wikibooks.org/wiki/分子生物学](https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Difference_DNA_RNA-EN.svg/400px-Difference_DNA_RNA-EN.svg.png)

DNAの複製 (replication)   
転写 (transcription)：DNAからRNAへ  
翻訳 (translation)：RNAからタンパク質へ  

![https://ja.wikibooks.org/wiki/分子生物学](https://upload.wikimedia.org/wikipedia/commons/6/68/Central_Dogma_of_Molecular_Biochemistry_with_Enzymes.jpg)

----------
----------

### Unix commands
Unixコマンド

- [今さら聞けない！ターミナルの使い方【初心者向け】 | TechAcademyマガジン](http://techacademy.jp/magazine/5155)
- [UNIXコマンド入門 (一般ユーザー編) (全16回) - プログラミングならドットインストール](http://dotinstall.com/lessons/basic_unix)
- [バイオインフォマティクス | UNIX | よく使うコマンド集](http://crusade1096.web.fc2.com/unix.html)

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    bash

[ターミナルの主要コマンド](https://techacademy.jp/magazine/5155#sec3): `cd, ls, mkdir, rm, mv, cp, pwd, man, find, clear, exit`

    # ディレクトリ間を移動する
    cd

    # 現在のディレクトリ内に存在する、ディレクトリやファイルを表示する
    ls

    # 今開いているディレクトリまでのパスを表示する
    pwd

    # 「projects」ディレクトリを作成する
    mkdir projects

    # 「projects」ディレクトリへ移動する
    cd projects/

    # 空ファイルを作成する
    touch test.txt

    # ファイルをコピーする
    cp test.txt test2.txt

    # ファイルやディレクトリの名前を変更する
    mv test.txt test1.txt

    # ファイルを削除する
    rm test2.txt

    # コマンドのマニュアルを開く。終了する場合に「q」を入力
    man man

    # ファイルやディレクトリの検索
    find .

    # ターミナル画面をクリアし、表示された文字を全て消去する
    clear

    # ログアウトする
    exit

----------
----------

## UniProtKB Swiss-Prot protein sequence database
[Swiss-Prot](https://ja.wikipedia.org/wiki/Swiss-Prot)タンパク質配列データベース

### Website
[UniProt](http://www.uniprot.org)の[Download latest release](http://www.uniprot.org/downloads)を開く。
<ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/> をブラウザ（Firefox または Chrome）で開く。
*uniprot_sprot.fasta.gz* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

### Download

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    bash

ディレクトリを作成する:  

    # make directories
    mkdir -p ~/projects/uniprot_sprot/data

ディレクトリを移動する:  

    # change directories
    cd ~/projects/uniprot_sprot/data/

圧縮ファイル（*uniprot_sprot.fasta.gz*）を`wget`または`curl`でダウンロードする:  

    # Downloading Data with wget and curl
    curl -O ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz
     # wget ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz

`gunzip`コマンドで解凍する:  

    # decompress files with the command gunzip
    gunzip -c uniprot_sprot.fasta.gz > uniprot_sprot.fasta

### Inspecting Data

`ls -lh`でファイルサイズを確認する:  

    # ls -lh reports human-readable file sizes
    ls -lh

[`cat`](https://ja.wikipedia.org/wiki/Cat_%28UNIX%29)でファイルを標準出力する（Control-Cで動作中のプロセスを停止）:  

    # print a file's contents to standard out (use Control-C to stop)
    cat uniprot_sprot.fasta

[`head`](http://codezine.jp/unixdic/w/head)で先頭部分を表示する:  
[`tail`](http://codezine.jp/unixdic/w/tail)で末尾部分を表示する:  

    # Inspecting Data with Head and Tail
    head uniprot_sprot.fasta
    tail uniprot_sprot.fasta

`grep`で、[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式ファイルのヘッダ（`>`で始まる行）にマッチする行を抽出する:  

    # extract FASTA headers
    grep "^>" uniprot_sprot.fasta

[FASTA headers](http://www.uniprot.org/help/fasta-headers)

    >db|UniqueIdentifier|EntryName ProteinName OS=OrganismName[ GN=GeneName]PE=ProteinExistence SV=SequenceVersion

[パイプ](https://ja.wikipedia.org/wiki/パイプ_%28コンピュータ%29)でプログラムの入出力をつなぐ。
配列の数をカウントする:  

    # wc -l outputs the number of lines
    grep "^>" uniprot_sprot.fasta | wc -l

日本語にちなんで命名されたタンパク質遺伝子 [harakiri, Izumo, Musashi, Shugoshin, Tonsoku](https://ja.wikipedia.org/wiki/Izumo_%28タンパク質%29#.E9.96.A2.E9.80.A3.E9.A0.85.E7.9B.AE) を検索する。

    grep "^>" uniprot_sprot.fasta | grep "harakiri"

    grep "^>" uniprot_sprot.fasta | grep -c "Shugoshin"
    grep "^>" uniprot_sprot.fasta | grep -ci "Shugoshin"

`grep`コマンドは、`-c`オプションでパターンにマッチした行数を表示し、`-i`オプションで大文字小文字を区別しない（ignore case）。

**"harakiri"検索結果**

    >sp|O00198|HRK_HUMAN Activator of apoptosis harakiri OS=Homo sapiens GN=HRK PE=1 SV=1
    >sp|P62816|HRK_MOUSE Activator of apoptosis harakiri OS=Mus musculus GN=Hrk PE=3 SV=1
    >sp|P62817|HRK_RAT Activator of apoptosis harakiri OS=Rattus norvegicus GN=Hrk PE=3 SV=1

"harakiri"遺伝子は3件登録されていた。
タンパク質名(`ProteinName`)は`Activator of apoptosis harakiri`。
生物名(`OS=OrganismName`)より、ヒト(`Homo sapiens`)、ハツカネズミ(`Mus musculus`)、ドブネズミ(`Rattus norvegicus`)の3種に由来する配列であることがわかる。
遺伝子名(`GN=GeneName`)に大文字と小文字（`GN=HRK`と`GN=Hrk`）が存在した。

**"Shugoshin"検索結果**

    >sp|Q0WTB8|SGO2_ARATH SHUGOSHIN 2 OS=Arabidopsis thaliana GN=SGO2 PE=2 SV=1
    >sp|Q562F6|SGO2_HUMAN Shugoshin 2 OS=Homo sapiens GN=SGO2 PE=1 SV=2
    >sp|Q7TSY8|SGO2_MOUSE Shugoshin 2 OS=Mus musculus GN=Sgo2 PE=1 SV=1
    >sp|O13734|SGO2_SCHPO Shugoshin-2 OS=Schizosaccharomyces pombe (strain 972 / ATCC 24843) GN=sgo2 PE=1 SV=1

"Shugoshin"にマッチする遺伝子は19件登録されていた。
タンパク質名(`SHUGOSHIN 2, Shugoshin 2, Shugoshin-2`)と遺伝子名(`SGO2, Sgo2, sgo2`)に表記揺れ（用語の不統一、大文字と小文字）が認められた。

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[パッケージ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/08.html)`seqinr`を呼び出す:  

    library(seqinr)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # Set and Get Working Directory
    setwd("~/projects/uniprot_sprot/data/")
    getwd()
    # List the Files in a Directory
    dir()

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data with SeqinR
    ld <- read.fasta(file = "uniprot_sprot.fasta.gz", seqtype = c("AA"), strip.desc = TRUE)

配列の数をカウントする:  

    # get the number of elements
    length(ld)

- [文字列 | Rを利用して文字列のマッチング,結合,分割,置換を行う関数](http://stat.biopapyrus.net/r/string.html)

[`getAnnot`](https://rdrr.io/rforge/seqinr/man/getAnnot.html)
関数を用いて、配列のアノテーションを取得する:  

    # get sequence annotations
    myAnnotation <- getAnnot(ld)

`grep(pattern, x)`は、`pattern`にマッチするベクトル`x`の全要素の番号を返す。
文字列（"harakiri"など）のパターンにマッチする要素番号を取得する:  

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    pattern <- "harakiri"
    pattern <- "Shiga.* toxin"
    pattern <- "Rhodopsin OS=(Bos taurus|Danio rerio|Homo|Mus|Rattus|Xenopus laevis)"
    i <- grep(pattern = pattern, x = myAnnotation, ignore.case = TRUE)
    length(i)
    unlist(getAnnot(ld[i]))

[リスト](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html)の成分を取り出す:  

    # extract the elements of the list object
    ld[i]

`write.fasta()`関数を用いて、配列データをFASTA形式ファイルとして書き出す:  

    # Writing sequence data out as a FASTA file
    write.fasta(sequences = ld[i], names = getName(ld[i]), file.out = "mySequences.fasta")

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    setwd("~/projects/uniprot_sprot/data/")    # Set Working Directory
    library(seqinr)    # Load the SeqinR package
    lx <- read.fasta(file = "mySequences.fasta", seqtype = c("AA"), strip.desc = TRUE)    # Reading sequence data
    unlist(getAnnot(lx))    # get sequence annotations

`sapply()`は、リストの各要素に関数を適用する。タンパク質配列の長さ（アミノ酸残基数）を求める:  

    # get the length of sequences
    # Apply a Function over a List
    sapply(lx, length)

#### Amino acid usage
タンパク質の[アミノ酸組成](https://kotobank.jp/word/アミノ酸組成-761227)

[アミノ酸の物性](https://www.thermofisher.com/jp/ja/home/life-science/protein-biology/protein-biology-learning-center/protein-biology-resource-library/pierce-protein-methods/amino-acid-physical-properties.html)

![http://www.jalview.org/help/html/misc/aaproperties.html](http://www.jalview.org/help/html/misc/properties.gif)

`summary()`関数でデータの要約:  

    summary(lx[[1]])

配列の長さ(length)、アミノ酸組成(composition)、物理化学的クラスの割合(AA.Property)が出力される。

[`AAstat()`](https://www.rdocumentation.org/packages/seqinr/versions/3.3-3/topics/AAstat)
関数を用いて、タンパク質の配列情報（アミノ酸残基数、物理化学的クラスの割合、等電点の理論値）を求める:  

    AAstat(lx[[1]])

![http://www.r-exercises.com/2017/05/10/accessing-and-manipulating-biological-databases-solutions-part-3/](http://www.r-exercises.com/wp-content/uploads/2017/05/Fig3-300x300.png)

アミノ酸の個数を出力:  

    AAstat(lx[[1]], plot = FALSE)$Compo

物理化学的クラス (Tiny, Small, Aliphatic, Aromatic, Non-polar, Polar, Charged, Positive, Negative) のうち、[芳香族アミノ酸](https://ja.wikipedia.org/wiki/芳香族アミノ酸) Aromatic の割合を出力:  

    AAstat(lx[[1]], plot = FALSE)$Prop$Aromatic

`sapply()`関数は、リストの各要素に関数を適用する。複数タンパク質配列の物理化学的クラスの割合を求める:  

    sapply(lx, function(x) AAstat(x, plot=FALSE)$Prop )

複数タンパク質配列のアミノ酸使用の絶対度数と相対度数を求める:  

    # absolute frequencies
    X <- sapply(lx, function(x) AAstat(x, plot=FALSE)$Compo )

    # relative frequencies
    X <- sapply(lx, function(x) summary(x)$composition )

データをカンマ区切りファイルとして出力する:  

    write.csv(t(X), file="table.csv")

    # open current working directory
    system("open .")

タンパク質のアミノ酸使用パターンを比較する。`matplot()`関数でプロットする:  

    # plot amino acid usage profiles together using matplot
    matplot(X, type="l", col=rainbow(12), lty=1:6)
    legend("topleft", legend=colnames(X), col=rainbow(12), lty=1:6)
    # lty: 0=blank, 1=solid (default), 2=dashed, 3=dotted, 4=dotdash, 5=longdash, 6=twodash

クラスター分析

    # Hierarchical cluster analysis
    plot(hclust(dist(t(X))))

ヒートマップ

    # Heatmap for amino acid usage profiles
    heatmap(t(X))

#### [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
ペアワイズ配列アラインメント

[Comparing two sequences using a dotplot](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#comparing-two-sequences-using-a-dotplot)  
ドットプロットで2つの配列を比較

    s1 <- lx[[1]]
    s2 <- lx[[3]]
    dotPlot(s1, s2)
    nmbr <- 3; dotPlot(s1, s2, wsize = nmbr, wstep = nmbr, nmatch = nmbr, xlab = getName(s1), ylab = getName(s2))

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

[Pairwise global alignment of protein sequences](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-global-alignment-of-protein-sequences-using-the-needleman-wunsch-algorithm)  
2つのタンパク質配列間のグローバル・アライメント

    library(Biostrings)
    data(BLOSUM50)

    aln_global <- pairwiseAlignment(toupper(c2s(s1)), toupper(c2s(s2)), substitutionMatrix = BLOSUM50, gapOpening = -2, gapExtension = -8, scoreOnly = FALSE)
    aln_global
    writePairwiseAlignments(aln_global)
    writePairwiseAlignments(aln_global, file="aln_global.txt")

[Pairwise local alignment of protein sequences](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-local-alignment-of-protein-sequences-using-the-smith-waterman-algorithm)  
2つのタンパク質配列間のローカル・アライメント

    aln_local <- pairwiseAlignment(toupper(c2s(s1)), toupper(c2s(s2)), substitutionMatrix = BLOSUM50, gapOpening = -2, gapExtension = -8, scoreOnly = FALSE, type="local")
    aln_local
    writePairwiseAlignments(aln_local, file="aln_local.txt")

#### [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#multiple-alignment-and-phylogenetic-trees)
多重配列アライメントと系統樹

    # Read an XStringSet object from a file
    library(Biostrings)
    mySequences <- readAAStringSet(file = "mySequences.fasta")

    # Multiple Sequence Alignment using ClustalW
    #source("http://www.bioconductor.org/biocLite.R"); biocLite("msa")
    library(msa)
    myAlignment <- msa(mySequences, "ClustalW")
    myAlignment

    # write an XStringSet object to a file
    writeXStringSet(unmasked(myAlignment), file = "myAlignment.fasta")

    system("open .")

[SeaView](http://www2.tba.t-com.ne.jp/nakada/takashi/phylogeny/seaview2.html)でアライメントを表示する。

![](http://www2.tba.t-com.ne.jp/nakada/takashi/phylogeny/fig/sv2/sv7.jpg)

[WebLogo](http://weblogo.berkeley.edu/logo.cgi)で配列の保存度を表示する。

![](http://blog.amelieff.jp/images/weblogo2.png)

    # Reading a multiple alignment file into R
    library(seqinr)
    myAln <- read.alignment(file = "myAlignment.fasta", format = "fasta")

    # Calculating genetic distances between protein sequences
    mydist <- dist.alignment(myAln)

    # Building an unrooted phylogenetic tree # 無根系統樹
    #install.packages("ape")
    library(ape)
    mytree <- nj(mydist)
    plot.phylo(mytree, type = "unrooted") # type = "phylogram", "cladogram", "fan", "unrooted", "radial"

    # Building a rooted phylogenetic tree # 有根系統樹
    #library(phangorn); mytree <- midpoint(mytree) # midpoint rooting
    mytree <- root(mytree, outgroup = grep(pattern="DANRE", x=mytree$tip.label), resolve.root = TRUE)
    plot.phylo(ladderize(mytree, right = FALSE), main = "Phylogenetic Tree")

    # Saving a phylogenetic tree as a Newick-format tree file
    write.tree(mytree, file="myTree.newick")


[ロドプシン (Rhodopsin)](https://ja.wikipedia.org/wiki/ロドプシン) のタンパク質配列の多重配列アライメントに基づく有根系統樹を構築する。
外群として ゼブラフィッシュ (Danio rerio、略して"DANRE") を選択し、系統樹に根をつける。
最初にアフリカツメガエル (Xenopus laevis、略して"XENLA") と他の集団が分岐し、
次にウシ (Bos taurus、"BOVIN") と他の集団が分岐し、
最後にヒト ("HUMAN") とネズミ ("RAT"と"MOUSE") が分岐したと推定される。

[SeaView](http://doua.prabi.fr/software/seaview)または[FigTree](http://www.geocities.jp/ancientfishtree/FigTree.html)を用いて、newick形式ファイルの系統樹を表示する。

![](http://en.bio-soft.net/tree/figtree.jpg)

### References
- [Swiss-Prot - Wikipedia](https://ja.wikipedia.org/wiki/Swiss-Prot)
- [Nucleic Acids Res. 2015 Jan;43(Database issue):D204-12. UniProt: a hub for protein information.](http://www.ncbi.nlm.nih.gov/pubmed/25348405)
- [Database (Oxford). 2014 Mar 12;2014:bau016. Expert curation in UniProtKB: a case study on dealing with conflicting and erroneous data.](http://www.ncbi.nlm.nih.gov/pubmed/24622611)

----------
----------

## NCBI assembly summary
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)のゲノム配列のメタデータが記載されている。

### Website
[National Center for Biotechnology Information](http://www.ncbi.nlm.nih.gov)右下[NCBI FTP Site](ftp://ftp.ncbi.nlm.nih.gov/)を開き、[genomes](ftp://ftp.ncbi.nlm.nih.gov/genomes/)/[ASSEMBLY_REPORTS](ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/)に移動する。
 <ftp://ftp.ncbi.nlm.nih.gov/genomes/README_assembly_summary.txt> で内容を確認:  

    assembly_summary_genbank.txt            - current GenBank genome assemblies
    assembly_summary_refseq.txt             - current RefSeq genome assemblies

### Download

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    bash

プロジェクト・ディレクトリを作成し移動する:  

    mkdir -p ~/projects/ncbi_assembly_summary/data
    cd ~/projects/ncbi_assembly_summary/data/

GenBankとRefSeqのゲノム配列のメタデータを記載したファイルを`wget`でダウンロードする:  

    # Download the two master assembly summary files that report assembly meta-data
    wget --background \
     ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_genbank.txt \
     ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt

`tail -f`でファイル出力を監視する（Control-Cで動作中のプロセスを停止）:  

    # Use `tail -f` to constantly monitor files (use Control-C to stop)
    tail -f wget-log

GenBankまたはRefSeqのゲノム配列のメタデータを確認する:  

    # 変数に値を割り当てる:  
    FILE="assembly_summary_genbank.txt"
    FILE="assembly_summary_refseq.txt"

    # ファイルのヘッダ（`#`で始まる行）を確認する:  
    grep "^#" $FILE

    # アセンブリの状況（assembly_level: Contig, Scaffold, Chromosome, Complete Genome）を確認する:  
    grep -v "^#" $FILE | cut -f12 | sort | uniq -c

[腸管出血性大腸菌O157](https://ja.wikipedia.org/wiki/O157) [Escherichia coli O157:H7 Sakai](http://integbio.jp/dbcatalog/record/nbdc00058) の完全ゲノム("Complete Genome")配列データの最新版("latest")のURLを抽出する:  

    NAME="O157.*Sakai"
    grep "$NAME" $FILE
    ftpdirpaths=(`awk -F "\t" '$8 ~ /'"$NAME"'/ && $11=="latest" && $12 ~ /Complete Genome/ {print $20}' $FILE`)

    # 抽出されたURLの数を確認する:  
    echo ${#ftpdirpaths[@]}

    # 抽出されたURLを表示する:  
    echo ${ftpdirpaths[@]}

抽出されたURL <ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF_000008865.1_ASM886v1> をブラウザFirefox/Chromeで開く。

    ファイル名    データファイルの内容
    *.gbff.gz    GenBank flat file format - GenBank形式ファイル
    *.fna.gz    FASTA Nucleic Acids - ゲノム塩基配列
    *.faa.gz    FASTA Amino Acids - 各タンパク質のアミノ酸配列

*README.txt*ファイル、[MD5](https://ja.wikipedia.org/wiki/MD5)[チェックサム](https://ja.wikipedia.org/wiki/チェックサム)ファイル（*md5checksums.txt*）、[GenaBank](http://bi.biopapyrus.net/biodb/genbank.html)形式と[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式の圧縮ファイル（*.gz*）を`wget`でダウンロードする:  

    for URL in ${ftpdirpaths[@]}
    do
      wget $URL/{README.txt,md5checksums.txt,*.gbff.gz,*.fna.gz,*.faa.gz}
    done

`md5`コマンドでチェックサムを計算し、公表されている値と一致するか確認する:  

    md5 *.gz
    cat md5checksums.txt

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[パッケージ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/08.html)`seqinr`を呼び出す:  

    library(seqinr)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    setwd("~/projects/ncbi_assembly_summary/data/")
    getwd()
    dir()

#### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data into R
    ld <- read.fasta(file = "GCF_000008865.1_ASM886v1_genomic.fna.gz", seqtype = c("DNA"), strip.desc = TRUE)

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

#### [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)

GC含量の局所変動:  

    # install.packages('zoo')
    library(zoo)
    windowsize <- 100000
    x <- seq(from = 1, to = length(dna)-windowsize, by = windowsize)
    y <- rollapply(data = dna, width = windowsize, by = windowsize, FUN = GC)
    plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")

2連続塩基組成（観測値/期待値）:  

    rho(dna, wordsize = 2)
    
    par(cex=0.7)
    barplot(sort(rho(dna, wordsize = 2)))
    abline(h=1)

配列間の2連続塩基組成プロファイルを比較する。
全ての配列 (1個の染色体と2個のプラスミド) について、2連続塩基組成を求める。
`sapply()`関数は、リストの各要素に関数を適用する:  

    X <- sapply(ld, rho)

`matplot()`関数でプロットする:  

    matplot(X, type="l", col=1:ncol(X), lty=1:ncol(X))
    legend("topleft", legend=colnames(X), col=1:ncol(X), lty=1:ncol(X))

クラスター分析

    plot(hclust(dist(t(X))))

ヒートマップ

    heatmap(t(X))

### References
- [RefSeq - JI 井上 潤](http://www.geocities.jp/ancientfishtree/RefSeq.html)
- [RefSeq | 重複のない生物の遺伝子データベース（ゲノムデータベース）](http://bi.biopapyrus.net/biodb/refseq.html)
- [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
- [Genomes Download FAQ](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/)
 - [1. What is the best protocol to use to download data?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#protocols)
 - [11. How can I find the sequence and annotation of my genome of interest?](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#howtofind)
 - [14. How can I download RefSeq data for all complete bacterial genomes?](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#allcomplete)

----------
----------

## Silva rRNA database
[リボソームRNA](https://ja.wikipedia.org/wiki/リボソームRNA)データベース

### Website
[Silva rRNA database](https://www.arb-silva.de)の[Download → Archive](https://www.arb-silva.de/download/archive/)をクリックし、[current](https://www.arb-silva.de/no_cache/download/archive/current/)/[Exports](https://www.arb-silva.de/no_cache/download/archive/current/Exports/)を開く。
例えば、*README.txt*ファイルを右クリックし、「リンクのURLをコピー (Copy Link)」する。

    README.txt
    SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz
    SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz.md5

### Download

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    bash

プロジェクト・ディレクトリを作成し移動する:  

    mkdir -p ~/projects/silva/data
    cd ~/projects/silva/data/

*README.txt*ファイル、塩基配列データの圧縮FASTAファイル（*.fasta.gz*）と[MD5](https://ja.wikipedia.org/wiki/MD5)[チェックサム](https://ja.wikipedia.org/wiki/チェックサム)ファイル（*.fasta.gz.md5*）を[`wget`](http://blog.layer8.sh/ja/2012/03/31/wget_command/)でダウンロードする:  

    wget --background \
     https://www.arb-silva.de/fileadmin/silva_databases/current/Exports/README.txt \
     https://www.arb-silva.de/fileadmin/silva_databases/current/Exports/SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz \
     https://www.arb-silva.de/fileadmin/silva_databases/current/Exports/SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz.md5

または

    wget --background https://www.arb-silva.de/fileadmin/silva_databases/current/Exports/{README.txt,SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz.md5,SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz}

`tail -f`でファイル出力を監視する（Control-Cで動作中のプロセスを停止）:  

    # Use `tail -f` to constantly monitor files (use Control-C to stop)
    tail -f wget-log

`md5`コマンドでチェックサムを計算し、公表されている値（492e513a8cc2de298a9b4121c9696278）と一致するか確認する:  

    md5 SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz
    cat SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz.md5

### Inspecting Data

`ls -l`でファイルの詳細情報を表示する:  

    ls -l

`gunzip`コマンドで解凍する:  

    gunzip -c SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz > SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta

`ls -lh`でファイルサイズを確認する:  

    ls -lh

変数に値を割り当てる:  

    DB="SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta"

`head`コマンドを用いて、ファイルの先頭部分を表示する:  

    head -n 3 $DB

`grep`コマンドを用いて、FASTA形式ファイルのヘッダ（`>`で始まる行）を抽出する:  

    grep "^>" $DB

[パイプ](https://ja.wikipedia.org/wiki/パイプ_%28コンピュータ%29)でプログラムの入出力をつなぐ。

配列の登録件数をカウントする:  

    grep "^>" $DB | wc -l

"Bacillus"にマッチする行を抽出する:  

    grep "^>" $DB | grep -c "Bacillus"

`grep`コマンドは、`-c`オプションでパターンにマッチした行数を表示し、`-i`オプションで大文字小文字を区別しない（ignore case）。

    grep "^>" $DB | grep -ci "Bacillus"

[FAQs](https://www.arb-silva.de/documentation/faqs/) "The taxonomic paths are standardized to six ranks; Domain, Phylum, Class, Order, Family and Genus."

Unixコマンド（`grep, cut, sort, uniq`）を組み合わせて、データの列を要約する。  
分類階級の[ドメイン](https://ja.wikipedia.org/wiki/ドメイン_%28分類学%29)：古細菌、真正細菌、真核生物（Domain: Archaea, Bacteria, Eukarya）をカウントする:  

    grep "^>" $DB | cut -d" " -f2 | cut -d";" -f1 | sort | uniq -c

ファイルで真正細菌（"Bacteria"）にマッチする行を抽出し、分類階級の[門](https://ja.wikipedia.org/wiki/門_%28分類学%29)（Phylum）をカウントし、`output.txt`ファイルへ出力する:  

    grep "^>" $DB | grep "Bacteria" | cut -d" " -f2 | cut -d";" -f2 | sort | uniq -c | sort -nr > output.txt

出力ファイルを確認する:  

    cat output.txt

### References
- [SILVA ribosomal RNA database - Wikipedia](https://en.wikipedia.org/wiki/SILVA_ribosomal_RNA_database)
- [blastn for silva database (SE)](http://cell-innovation.nig.ac.jp/wiki2/tiki-index.php?page=P000001306)

----------
----------

2017-05-13

## [Annotation of promoter sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/hrichard/Annotation_of_promoter_sequences.pdf)
**[プロモーター](https://ja.wikipedia.org/wiki/プロモーター)配列のアノテーション**

### Transcription Factor Binding sites annotation
**[転写因子結合部位](https://ja.wikipedia.org/wiki/転写因子#.E8.BB.A2.E5.86.99.E5.9B.A0.E5.AD.90.E7.B5.90.E5.90.88.E9.A0.98.E5.9F.9F)のアノテーション**

一般に転写因子は、長さ6〜10の塩基に結合する。
転写因子PHOタンパク質の結合モチーフGCACGT[TG][TC]配列は実験的に検出されているが、実験を行うことは時間とコストがかかる。
代わりに、同時制御された（同じ条件で転写される）配列群を統計解析することにより、それらの配列に共通の結合モチーフを探す。
ここでは、酵母ゲノムの塩基組成を考慮して、期待されるよりも高頻度に出現するk-mer（連続塩基）を検索する。

### Part 1 Loading sequences and counting k-mers
**配列の読み込みと塩基のカウント**

	library(seqinr)
	yeast <- read.fasta(file = "http://www.lcqb.upmc.fr/hrichard/sequences/yeast_s_cerevisae_genomic_chr1-4.fna")
	
	##Chr1 pos 1 to 100
	
	##let's put all chromosome together
	yeastseqs = c()
	##Length of the chromosomes
	for (i in 1:length(yeast)){
	    cat("Chromosome", i, ":", length(yeast[[i]]), "\n")
	    yeastseqs = c(yeastseqs, yeast[[i]])
	}
	
	cat("total length:", length(yeastseqs) )
	##we want to compute the frequency of each nucleotide

Let's compute the frequency of the four letters now, that will be handy for later.

4連続塩基の頻度を計算:

	nuc.count = table(yeastseqs)

	nuc.freq = nuc.count/ sum(nuc.count)

	nuc.count

	nuc.freq

DNA中のアデニン（A）の数とチミン（T）の数が等しく、シトシン（C）の数とグアニン（G）の数が等しい。

[シャルガフの法則 Chargaff's rule](https://kotobank.jp/word/シャルガフの法則-789047)  
[シャルガフの経験則](https://ja.wikipedia.org/wiki/エルヴィン・シャルガフ#.E3.82.B7.E3.83.A3.E3.83.AB.E3.82.AC.E3.83.95.E3.81.AE.E7.B5.8C.E9.A8.93.E5.89.87)  

### Part 2 Detect promoter sequences
**プロモーター配列の検出**

We define the function expectedFreq accordingly

関数`expectedFreq`を定義する:  

	expectedFreq <- function(w, nfreq, len){
	  eF = 1
	  k = length(w)
	  for (c in s2c(w)){
	    eF = eF * nfreq[c]
	    }
	  eF = eF*(len - k + 1)
	  return(eF)
	}

Let's read the sequences for PHO:

[PHO](http://www.lcqb.upmc.fr/hrichard/sequences/regulatory_seq_PHO.fasta)の配列を読み込む:  

	pho = read.fasta(file = "http://www.lcqb.upmc.fr/hrichard/sequences/regulatory_seq_PHO.fasta")
	
	phoseqs = c()
	for (i in 1:length(pho)){
	    phoseqs = c(phoseqs, pho[[i]]) 
	}
	
	pho.length = length(phoseqs)
	
	cat("Length:", pho.length)

We can now compute the number of occurrences for all words of length 4, and compare with the expected count

4連続塩基の出現回数（観測度数）を計算し、期待度数と比較する:  

	pho.count4 = count(phoseqs, 4)
	
	##To get the same names for the expected counts
	pho.exp4 = pho.count4
	
	for (i in 1:length(pho.exp4)){
	  word = names(pho.exp4)[i]
	  pho.exp4[i] = expectedFreq(word, nuc.freq, pho.length)
	}
	
	#
	plot( as.vector(pho.exp4), as.vector(pho.count4), 
	      pch = 19, col = "blue", cex =0.7, 
	      xlab = "Expected count", ylab = "Oberved count")
	abline(a = 0, b =1, col = "red")

The points above the diagonal are observed more often than expected. Let's look how the 20 most overrepresented correspond to the PHO motif.

対角線より上の点は、期待されるよりも高頻度に観測される文字列（4連続塩基）。PHOモチーフで高頻度に観測された上位20の文字列（4連続塩基）を確認する:  

	pho.sig4 = pho.count4 / pho.exp4
	##Check the distribution
	hist(pho.sig4, br =40)
	
	sorted.sig4 = sort(pho.sig4, decreasing = TRUE)
	overrep.words4 = names(sorted.sig4[1:20])
	
	cat(overrep.words4, sep = "\n")


k = 4 解析で、高頻度に観測された上位20の文字列（4連続塩基）は、PHOモチーフ GCACGT[GT][GT][GT] に整列させられるか？モチーフに整列させられない文字列が高頻度ある理由は？

k = 6 解析で、高頻度に観測される上位20の文字列（6連続塩基）を列挙し、PHOモチーフ GCACGT[GT][GT][GT] に整列させる。

----------
----------
2017-05-20

## [Annotation of Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/hrichard/Annotation_of_Coding_sequences.pdf)
**タンパク質をコードする配列のアノテーション**

遺伝子の[コーディング領域](https://ja.wikipedia.org/wiki/コーディング領域)はタンパク質に翻訳される領域を指す。

### Gene annotation
**遺伝子領域の推定**

遺伝子領域の推定

![http://www.nite.go.jp/nbrc/genome/description/analysis2.html](http://www.nite.go.jp/data/000021952.gif)

[塩基配列のうち、タンパク質として機能していると予想される領域をＯＲＦ（Open Reading Frame：推定遺伝子領域）と呼びます。
ＯＲＦは、開始コドンと呼ばれる３塩基から始まり、終止コドンと呼ばれる３塩基で終わります。また、アミノ酸に対応するコドンも解読されており、ＯＲＦの推定はコンピュータを用いて行います。](http://www.nite.go.jp/nbrc/genome/description/analysis2.html)

![http://www.toho-u.ac.jp/sci/biomol/glossary/bio/genetic_code.html](http://www.toho-u.ac.jp/sci/biomol/glossary/bio/j5mt8h000000dkv7-img/codon.jpg)

### Loading genomic sequence and annotations
**ゲノム配列とアノテーションの読み込み**

![https://en.wikipedia.org/wiki/Enterobacter_cloacae](https://upload.wikimedia.org/wikipedia/commons/thumb/7/79/Enterobacter_cloacae_01.png/240px-Enterobacter_cloacae_01.png)

We will be analysing the genome of E. clocae for which we have also a reference annotation. E. clocae is a clinically significant Gram-negative, facultatively-anaerobic, rod-shaped bacterium, more info (https://en.wikipedia.org/wiki/Enterobacter_cloacae)
Let's first load its genomic sequence and get the annotation in a dataframe.

腸内細菌[エンテロバクター属](https://ja.wikipedia.org/wiki/エンテロバクター属)に属するEnterobacter cloacaeのゲノム配列を読み込み、データフレーム内のアノテーションを取得する:  

	library(seqinr)

	ecseq <- read.fasta(file = "http://www.lcqb.upmc.fr/hrichard/sequences/eclocae.genome.fasta")[[1]]

	#Size of the genome
	cat("Length of the E. clocae genome:", length(ecseq))

	ecannot <- read.delim("http://www.lcqb.upmc.fr/hrichard/sequences/eclocae.annotation.tsv") 
	head(ecannot)

遺伝子の長さ gene length のヒストグラムを描画

	##Let's do an histogram of the annotated gene length

	hist(ecannot$Length, br = 40, main = "Length of annotated genes", xlab = "gene length")
	abline(v = mean(ecannot$Length), col = "blue")

	plot(ecdf(ecannot$Length), xlim = c(0, 1000), cex = 0.5, main = "Cumulative distribution", 
	    xlab = "gene length")

### Annotating Open Reading Frames
**オープン リーディング フレームのアノテーション**

[オープンリーディングフレーム (Open Reading Frame; ORF) とは、DNA またはRNA 配列をアミノ酸に翻訳した場合に終了コード配列（termination codon; 終止コドン）を含まない読み取り枠（Reading Frame）がオープンな（Open）状態にある（タンパク質に翻訳される可能性がある）塩基配列を指す。](https://ja.wikipedia.org/wiki/オープンリーディングフレーム)

An Open Reading Frame (ORF) is defined as a stretch of sequence such that:
1. It begins with a start codon (ATG, GTG or TTG)
2. It ends with a stop codon (TAA, TAG or TGA).
3. There are no in phase stop codon within the sequences.

The first way for people to annotate a genome was to mark, for each phase and on each strand, the stop and the start codon and detect the longest ORF at each position.

DNA鎖の[開始コドン](https://ja.wikipedia.org/wiki/開始コドン) start codon (ATG, GTG or TTG) と[終止コドン](https://ja.wikipedia.org/wiki/終止コドン) stop codon (TAA, TAG or TGA) をマークし、最長のオープンリーディングフレーム longest ORF を検出する

	start = c("ATG", "GTG", "TTG", "atg", "gtg", "ttg")
	stop = c("TAA", "TAG", "TGA", "taa", "tag", "tga")

	##Do a function to return a list of positions with the phase
	##for a given list of codons
	findOcc <- function(ntseq, codonlist){
	  occs = c()
	  for (i in 1:(length(ntseq)-2)){
	    ccod = paste(ntseq[i:(i+2)], collapse = "")
	    if (ccod %in% codonlist){
	      #cframe = (i %% 3 ) + 1
	      occs = c(occs, i)
	    }
	  }
	  posocc = data.frame(pos = occs, frame = (occs %% 3) + 1)
	  return(posocc)
	}

	###Let's get the start and end codons on the first 10万 positions.

	Startpos = findOcc(ecseq[1:100000], start)
	Stoppos = findOcc(ecseq[1:100000], stop)

We can plot the results for a stretch of a chromosome, and compare with the annotation.
Let's first prepare a plotting function.

染色体のDNA配列に開始コドンと終止コドンをマークした結果をプロットし、アノテーションと比較する。

プロット関数を用意する。

	##Plots the annotation together with the on the positions from beginning to end
	PlotPhaseAndAnnotation <- function(begin, end, startpos, stoppos, annot){
	  plot(c(begin, end), c(0.2, 3), type =  "n",
	       ylab = "frame", xlab= "genomic coordinate",
	       yaxp = c(1,3, 2))
	  
	  points(startpos$pos, startpos$frame, col = "darkgreen", 
	         cex = 0.5, pch = 19)
	  points(stoppos$pos, stoppos$frame-0.05, col = "red", 
	         cex = 0.5, pch = 19)
	  
	  genefw = subset(annot, Strand == "+" & Replicon.Name == "chr")
	  genebw = subset(annot, Strand == "-" & Replicon.Name == "chr")
	  ##Annotations
	  rect(genefw$Start, ((genefw$Start) %% 3) + 0.7, genefw$Stop, 
	       ((genefw$Start) %% 3) + 0.9, col = "cyan", lwd = 0.5)
	  
	  rect(genebw$Start, ((genebw$Start) %% 3) + 0.65, genebw$Stop, 
	       ((genebw$Start) %% 3) + 0.45, col = "pink", lwd = 0.5)
	}


Let's plot some ranges of coordinates now.
You can notice on the second plot that some long ORF occur with no genes on the forward strand (frame 2 in the middle)

DNA配列の領域 (1500..20000) と (75000..90000) をプロットする

	PlotPhaseAndAnnotation(1500, 20000, Startpos, Stoppos, ecannot)
	
	PlotPhaseAndAnnotation(75000, 90000, Startpos, Stoppos, ecannot)

Let's detect all the ORFs from a collection of start and stop positions.

開始位置と終止位置のコレクションからORFを検出する

	library(dplyr, quietly =TRUE)
	
	allpos = rbind(data.frame(Startpos, type = 1), data.frame(Stoppos, type = -1))
	allpos = allpos %>% arrange(pos) %>% group_by(frame) %>% 
	          mutate(stopnum = cumsum(lag(as.integer(type == -1), default = 0)))
	
	by_frame = allpos %>% group_by(frame, stopnum)
	ORFpos = summarise(by_frame, start = min(pos), end = max(pos), 
	                   tstart = type[which.min(pos)], 
	                   tend = type[which.max(pos)],
	                   len = end - start + 1)
	ORFpos = ORFpos %>% filter(len > 20)

We can now look at the histogram of the ORF length and compare it to the histogram of the real genes in order to decide at which value it is unlikely that a ORF was due to chance.

「ORFの長さのヒストグラム」と「実際の遺伝子のヒストグラムを比較することで、ORFが偶然の可能性を判断する。

	## Plot the histogram of lengths
	##
	
	hist(ecannot$Length, br = seq(0, 100000, by = 20), 
	     xlim = c(0,1000), ylim = c(0, 0.01), col = "blue", freq = FALSE)
	hist(ORFpos$len, br = seq(0, 100000, by = 20), add = TRUE, freq = FALSE, col = "red", alpha= 0.2)
	
	##We also compare the ORF with the annotation on a stretch
	
	
	PlotPhaseAndAnnotation(75000, 90000, Startpos, Stoppos, ecannot)
	
	rect( ORFpos$start, ORFpos$frame - 0.6, ORFpos$end, ORFpos$frame - 0.8,
	      col = "red", lwd = 0.5)

A classical threshold is usually set at 150 nt. But in this case we miss some of the shorter genes. Those are called False Negative predictions.

閾値を50アミノ酸(150塩基)に設定した場合、短い遺伝子を予測できない（偽陰性）。

	table(ecannot$Length < 50)

### Statistical properties of coding regions
**タンパク質[コーディング領域](https://ja.wikipedia.org/wiki/コーディング領域)の統計的性質**

In order to detect more genes we will assess the coding potential of the regions by comparing its probability under two different models:
- The codons model: in this model the probability of a sequence is the product of the probabilities of all the codons which are occurring.
- The independant nucleotides models: in this model the probability of a sequence is the product of the frequencies of its nucleotides.
We can use a sliding window of a given size and compare in each window compute the log ratio of the probabilities.
The probabilities of all codons are precomputed and given in the beginning. We write a function to compute the log ratio of probabilities for a given window.

より多くの遺伝子を検出するために、2つの異なるモデルの確率を比較することによって、領域のコーディングポテンシャルを評価する：
- コドン・モデル：配列の確率は、コドンの確率の積
- ヌクレオチド・モデル：配列の確率は、ヌクレオチドの頻度の積

指定サイズのスライディング・ウインドウ(sliding window)を使用し、各ウインドウで確率の対数比を計算する。

ウィンドウ内のコドンの確率の対数比を計算する関数

	pcodons = c(aaa = 0.0287,aac = 0.02533,aag = 0.01372,aat = 0.01221,aca = 0.00505,
	            acc = 0.02957,acg = 0.01735,act = 0.00475,aga = 0.00197,agc = 0.01977,
	            agg = 0.00173,agt = 0.00577,ata = 0.00335,atc = 0.02926,atg = 0.02716,
	            att = 0.02405,caa = 0.00792,cac = 0.01197,cag = 0.0355,cat = 0.01034,
	            cca = 0.00647,ccc = 0.00685,ccg = 0.02485,cct = 0.00671,cga = 0.00278,
	            cgc = 0.02546,cgg = 0.00639,cgt = 0.01872,cta = 0.00209,ctc = 0.01366,
	            ctg = 0.06566,ctt = 0.01106,gaa = 0.03175,gac = 0.0245,gag = 0.02462,
	            gat = 0.02809,gca = 0.01557,gcc = 0.03395,gcg = 0.03721,gct = 0.01111,
	            gga = 0.00671,ggc = 0.03416,ggg = 0.01381,ggt = 0.01989,gta = 0.00781,
	            gtc = 0.01699,gtg = 0.03232,gtt = 0.01433,taa = 3e-05,tac = 0.01453,
	            tag = 3e-05,tat = 0.01333,tca = 0.00615,tcc = 0.01153,tcg = 0.00926,
	            tct = 0.00704,tga = 4e-05,tgc = 0.00663,tgg = 0.01568,tgt = 0.00388,
	            tta = 0.00701,ttc = 0.01932,ttg = 0.00752,ttt = 0.01897)
	
	ntproba = seqinr::count(ecseq[1:10000], wordsize = 1, freq =TRUE)

	##The function
	
	CodingScore <- function(cseq, pcodon, pnt){
	  lpcodon = log(pcodon)
	  lpnt = log(pnt)
	  ntlogproba = 0
	  codonlogproba = 0
	  for (i in seq(1,(length(cseq)-2), by = 3)){
	    ccodon = cseq[i:(i+2)]
	    cc = paste(ccodon, collapse = "")
	    ntlogproba = ntlogproba + lpnt[[ccodon[1]]] + lpnt[[ccodon[2]]] + lpnt[[ccodon[3]]]
	    codonlogproba = codonlogproba + lpcodon[[cc]]  
	  }
	  logoddsratio = codonlogproba - ntlogproba
	  return(logoddsratio)
	}

	##The window function, we just compute it every 4 codons.
	CodingWindow <- function(cseq, start, end, pcodon, pnt, windowsize = 66, smsize =5){
	   realend = end - windowsize + 1
	   xcoords = seq(start, realend, by = 12)
	   scores = sapply(xcoords, 
	                   function(x) {
	                     to = x+windowsize-1
	                     CodingScore(cseq[x:to], pcodon, pnt)})
	   res = data.frame(pos = xcoords, logp = scores)
	   res$winlogp = 0
	   for (x in (smsize+1):(nrow(res)-smsize)){
	       res$winlogp[x] = mean(res$logp[(x-smsize):(x+smsize)])
	   }
	   res$scalelogp = res$winlogp - min(res$winlogp)
	   res$scalelogp = res$scalelogp / max(res$scalelogp)
	  return(res)
	}

Let's do this analysis for all the three phases in one region.

領域内の3つのフレームを調べる

	phase1 = CodingWindow(ecseq, 70002, 80000, pcodons, ntproba, smsize = 1)
	phase2 = CodingWindow(ecseq, 70003, 80000, pcodons, ntproba, smsize = 1)
	phase3 = CodingWindow(ecseq, 70001, 80000, pcodons, ntproba, smsize = 1)

	##Check the distribution of the logratio of windows

	hist(phase1$winlogp, br = 40, main = "distribution of log ratios, phase 1")

There is a clear separation between the likely coding and the likely non coding regions. We can also see that directly when checking the annotation.

	PlotPhaseAndAnnotation(70000, 80000, Startpos, Stoppos, ecannot)
	
	points(phase1$pos,phase1$scalelogp , t = "l", col = "blue")
	points(phase2$pos,phase2$scalelogp+1 , t = "l", col = "red")
	points(phase3$pos,phase3$scalelogp+2 , t = "l", col = "green")
	
	abline(h = c(mean(phase3$scalelogp+2),
	             mean(phase2$scalelogp+1),
	             mean(phase1$scalelogp)), 
	       lwd =2, lty = 3)

### Annotation of the ORFs
**ORFのアノテーション**

1. Compute the log odds ratio on all the ORFs that were annotated in the first part and use it to decide if an ORF is a coding gene. Check now how is the length distribution of the genes.
2. Add an ORF annotation for the reverse strand (You can modify the function by using the coordinate -1, -2 and -3 on the y axis).

----------
----------




