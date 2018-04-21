**[生命情報解析 / 生命動態のデータサイエンス [DS2]](https://github.com/haruosuz/DS4GD/tree/master/2018)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

Table of Contents
- [assignment 3](#assignment-3) 課題No.3
- [assignment 2](#assignment-2) 課題No.2
- [assignment 1](#assignment-1) 課題No.1
- [ASSIGNMENT](#assignment) 選抜課題
- [dotplot](#dotplot)
- [UniProtKB Swiss-Prot protein sequence database](#uniprotkb-swiss-prot-protein-sequence-database)
- [NCBI assembly summary](#ncbi-assembly-summary)
- [NCBI sequence database](#ncbi-sequence-database)

----------
## assignment 3
[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

SeqinRパッケージを用いて、配列データをRに読み込む:  

	# read the sequence into R using the SeqinR package:
    library("seqinr")
    ACCESSION <- "NC_001477" # Dengue virus 1
    #ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
    ld <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"))
    d <- ld[[1]]

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. What are the last twenty nucleotides of the genome sequence?

    d[(length(d)-20+1):length(d)]

Q2. What is the length in nucleotides of the genome sequence?

    length(d)

Q3. How many of each of the four nucleotides A, C, T and G, and any other symbols, are there in the genome sequence?

    table(d)

Q4. What is the GC content of the genome sequence, when (i) all non-A/C/T/G nucleotides are included, (ii) non-A/C/T/G nucleotides are discarded?

	help("GC")
    GC(d)
    GC(d, exact=FALSE)

Q5. How many of each of the four nucleotides A, C, T and G are there in the complement of the genome sequence?

![http://revertra.webcrow.jp/DNA/index.php](http://revertra.webcrow.jp/DNA/dnaseq.png)

	help.search("complement")
	help("comp")
    table(comp(d))

Q6. How many occurrences of the DNA words CC, CG and GC occur in the genome sequence?

    count(seq=d, wordsize=2)

Q7. How many occurrences of the DNA words CC, CG and GC occur in the (i) first 1000 and (ii) last 1000 nucleotides of the genome sequence?
How can you check that the subsequence that you have looked at is 1000 nucleotides long?

    count(seq=d[1:1000], wordsize=2)
    count(seq=d[(length(d)-1000+1):length(d)], wordsize=2)

----------
## assignment 2
**課題No.2 「Installing R packages seqinr & Biostrings」**    

RパッケージseqinrとBioconductorパッケージBiostringsをインストールする。

パッケージseqinrのインストール:  

    # Install the "seqinr" package:
    install.packages("seqinr")

BioconductorパッケージBiostringsのインストール:  

    # Install the Bioconductor package called "Biostrings":
    source("https://bioconductor.org/biocLite.R")
    biocLite("Biostrings")

パッケージの呼び出し:  

    # Load the packages into R:
    library("seqinr")
    library("Biostrings")

Rパッケージのバージョンを確認:  

    # Print the versions of these packages:
    packageVersion("seqinr")
    packageVersion("Biostrings")

Rのバージョンを確認:  

    # Print the version of R running:
    R.version.string

回答例:  

    # Example answer:  

    > packageVersion("seqinr")
    [1] ‘3.4.5’

    > packageVersion("Biostrings")
    [1] ‘2.42.1’

    > R.version.string
    [1] "R version 3.3.3 (2017-03-06)"

Record the version of R and R packages by the `sessionInfo()` function.

    > sessionInfo()
    R version 3.3.3 (2017-03-06)
    Platform: x86_64-apple-darwin13.4.0 (64-bit)
    Running under: OS X Mavericks 10.9.5

References:

https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages

----------
## assignment 1
**課題No.1 「R言語入門」**    
〆切：2018-04-16 23:59:00

次の動画レッスンを見て、疑問点を報告する。[R言語入門 (全13回) - プログラミングならドットインストール](http://dotinstall.com/lessons/basic_r)【回答例】動画レッスン番号 #03 ~ #13 を見た。疑問点は次の通りである。
- 因子ベクトルというものがよくわからなかった。
- 行列とデータフレームとリストの違いが理解できなかった。

----------
## ASSIGNMENT
選抜課題

【課題内容】
本授業で解析したいDNAまたはタンパク質の配列を300文字以内で述べてください。課題のタイトルと参考文献も明記してください。

DNAまたはタンパク質の配列を検索するには、

- NCBIウェブサイト (https://www.ncbi.nlm.nih.gov) にアクセスし、ウェブページ上部の検索ボックスにキーワード（例えば、"Candidatus Midichloria mitochondrii"）を入力して、"Search"ボタンを押す
https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#retrieving-genome-sequence-data-via-the-ncbi-website

または

- UniProtウェブサイト (http://www.uniprot.org) にアクセスし、ウェブページ上部の検索ボックスにキーワード（例えば、"antibiotic resistance Clostridium difficile"）を入力して、"Search"ボタンを押す
https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#viewing-the-uniprot-webpage-for-a-protein-sequence

---

Please describe DNA or protein sequences you're interested in. Please also state your project title and references.

To find DNA or protein sequences,

- go to the NCBI website (https://www.ncbi.nlm.nih.gov), type keywords (e.g. "Candidatus Midichloria mitochondrii") in the Search box at the top of the webpage, and press the “Search” button beside the Search box.
http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#retrieving-genome-sequence-data-via-the-ncbi-website

or

- go the UniProt website (http://www.uniprot.org). At the top of the UniProt website, you will see a search box, and you can type keywords (e.g. "antibiotic resistance Clostridium difficile") that you are looking for in this search box, and then click on the “Search” button to search for it.
http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#viewing-the-uniprot-webpage-for-a-protein-sequence

----------

## dotplot

ヒトの[血小板由来成長因子](https://ja.wikipedia.org/wiki/血小板由来成長因子) (Platelet-Derived Growth Factor, PDGF) と [サル肉腫ウイルスの癌遺伝子 v-sis](https://www.wikigenes.org/e/mesh/e/21827.html) のアミノ酸配列は類似性が高い。([Doolittle RF et al., 1983](https://www.ncbi.nlm.nih.gov/pubmed/6304883))

    # "sp|P01127|PDGFB_HUMAN Platelet-derived growth factor subunit B OS=Homo sapiens GN=PDGFB PE=1 SV=1"          
    # "sp|P01128|TSIS_WMSV PDGF-related-transforming protein sis OS=Woolly monkey sarcoma virus GN=V-SIS PE=3 SV=1"

    library("seqinr")
    seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/P01127.fasta")[[1]]
    seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/P01128.fasta")[[1]]

    # Comparing two sequences using a dotplot
    dotPlot(seq1, seq2)

----------
----------

## NCBI assembly summary
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)のゲノム配列のメタデータが記載されている。

ftp://ftp.ncbi.nlm.nih.gov/genomes/README_assembly_summary.txt

### Website
NCBIウェブサイト (https://www.ncbi.nlm.nih.gov) にアクセスし、右下のリンク"NCBI FTP Site"をクリックして開く。  
<ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> をブラウザ（Firefox または Chrome）で開く。  
*assembly_summary_genbank.txt*, *assembly_summary_refseq.txt*を右クリックし、「リンクのURLをコピー (Copy Link)」する。

Go to the NCBI website (https://www.ncbi.nlm.nih.gov), and then click the link "NCBI FTP Site".   
Open the URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> with your browser (Firefox or Chrome).  
Right click the link *assembly_summary_genbank.txt*, *assembly_summary_refseq.txt*, and select "Copy Link Address".


    ファイル名と内容
    *_genomic.gbff.gz: GenBank flat file format - GenBank形式ファイル
    *_genomic.fna.gz: FASTA Nucleic Acids - ゲノム塩基配列
    *_protein.faa.gz: FASTA Amino Acids - 各タンパク質のアミノ酸配列


    File formats and content
    *_genomic.gbff.gz: GenBank flat file format of the genomic sequence(s).
    *_genomic.fna.gz: FASTA format of the genomic sequence(s).
    *_protein.faa.gz: FASTA format of the protein sequence(s).

ftp://ftp.ncbi.nlm.nih.gov/genomes/all/README.txt

----------
## NCBI sequence database

[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)のゲノム配列決定プロジェクト一覧
[Genome List](http://www.ncbi.nlm.nih.gov/genome/browse/)  

- 全生物 <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/overview.txt>
- 真核生物 <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/eukaryotes.txt>
- 原核生物 <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prokaryotes.txt>
- 原核生物の参照ゲノム <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_reference_genomes.txt>
- 原核生物の代表ゲノム <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_representative_genomes.txt>
- ウイルス <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/viruses.txt>
- プラスミド <ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/plasmids.txt>

https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#the-ncbi-sequence-database

NCBIからDNA配列を取得:  

    # Retrieving a DNA sequence from NCBI
    library("seqinr")
    ACCESSION <- "NC_001477"
    ld <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"))
    d <- ld[[1]]
    write.fasta(sequences=d, names=sapply(seqs, getAnnot), file.out=paste0(ACCESSION,".fna"))

NCBIから複数のDNA配列を取得:  

    # Retrieving a list of DNA sequences from NCBI
    library("seqinr")
    # create a function to retrieve several nucleotide sequences from NCBI
    retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)[[1]]
    
    seqnames <- c("NC_001477", "NC_001474", "NC_001475", "NC_002640") # Make a vector containing the names of the sequences
    seqs <- lapply(seqnames,  retrieve_ncbi_fna) # Retrieve the sequences and store them in list variable "seqs"
	length(seqs)      # Print out the number of sequences retrieved
	seq1 <- seqs[[1]] # Get the 1st sequence
	seq1[1:20]        # Print out the first 20 letters of the 1st sequence
	seq2 <- seqs[[2]] # Get the 2nd sequence
	seq2[1:20]        # Print out the first 20 letters of the 2nd sequence

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs, names=seqnames, file.out="sequence.fna")

----------

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

年月日を確認:  

    # Get Current Date and Time
    Sys.Date()

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    Directory <- paste0("~/projects/",Sys.Date())

    # Invoke a System Command
    system( paste0("mkdir -p ",Directory) )

    # Set and Get Working Directory
    setwd(Directory)
    getwd()

    # List the Files in a Directory
    dir()

[Ｒ言語のデータの入出力と編集](https://www1.doshisha.ac.jp/~mjin/R/02.html)

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    # Loading Data into R
    filename <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_reference_genomes.txt"
    d <- read.delim(file = filename, stringsAsFactors=FALSE, check.names=FALSE)

[データフレーム](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html)の行と列の数、先頭部分、列名の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    head(d, n = 1)
    colnames(d)

- [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
- [RefSeq - JI 井上 潤](http://www.geocities.jp/ancientfishtree/RefSeq.html)
- [RefSeq | 重複のない生物の遺伝子データベース（ゲノムデータベース）](http://bi.biopapyrus.net/biodb/refseq.html)

[文字列の処理](http://stat.biopapyrus.net/r/string.html)  

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    pattern <- "Escherichia coli.*K-12"
    i <- grep(pattern = pattern, x = d$`Organism name`, ignore.case = TRUE)
    length(i)
    d[i,]
    d$`Chromosome RefSeq`[i]

[パッケージ](https://stats.biopapyrus.jp/r/basic/package.html)`seqinr`を呼び出す:  

    # Load the SeqinR package
    library(seqinr)

NCBIからDNA配列を取得:  

    # Retrieving a list of DNA sequences from NCBI

    # create a function to retrieve several nucleotide sequences from NCBI
    retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)[[1]]
    
    ACCESSIONs <- d$`Chromosome RefSeq`[i] # Make a vector containing RefSeq accessions of Chromosome sequences

    ld <- lapply(ACCESSIONs,  retrieve_ncbi_fna) # Retrieve the sequences and store them in list variable "ld"

	# write the sequences to a FASTA-format file
    write.fasta(sequences=ld, names=sapply(ld, getAnnot), file.out="sequence.fna")

配列の数をカウントする:  

    # get the number of elements
    length(ld)

[`getAnnot`](https://rdrr.io/rforge/seqinr/man/getAnnot.html)
関数を用いて、配列のアノテーションを取得する:  

    # get sequence annotations
    getAnnot(ld)

変数`dna`にリストの1番目の要素を代入する:  

    # store the first element of the list object `ld` in a variable `dna`
    dna <- ld[[1]]

#### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)

DNA配列の長さ:  

    # Length of a DNA sequence
    length(dna)

DNA配列の塩基組成:  

    # Base composition of a DNA sequence
    table(dna)

[GC Content of DNA](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#gc-content-of-dna)

DNA配列のGC含量:  

    # GC Content of DNA
    GC(dna)

`summary()`関数でデータの要約:  

    # Object Summaries
    summary(dna)

DNA配列の長さ(length)、塩基組成(composition)、GC含量(GC)が出力される。

2連続塩基含量:  

    # DNA words
    count(dna, 2)

#### [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)

2連続塩基組成（観測値/期待値）:  

    # Over-represented and under-represented DNA words
    rho(dna, wordsize = 2)
    
    par(cex=0.7)
    barplot(sort(rho(dna, wordsize = 2)))
    abline(h=1)

[Campbell A et al. (1999) "Genome signature comparisons among prokaryote, plasmid, and mitochondrial DNA."](https://www.ncbi.nlm.nih.gov/pubmed/10430917)

![](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC17754/bin/pq1692140001.jpg)

Sliding windowでゲノムの局所的な塩基組成（GC content, GC skew）を解析する:  

    library(zoo)
    pdf(file="Rplot.pdf") # create a PDF device called "Rplot.pdf"
    par(mfcol=c(1,1), cex=1.5, mai = c(1.2, 1.2, 0.1, 0.1)) # c(bottom, left, top, right)

    # x-axis: Position
    windowsize <- 10000
    x <- seq(from = 1, to = length(dna)-windowsize, by = windowsize) / 10^6
    xlab <- "Position (Mbp)"

    # y-axis: GC content
    y <- rollapply(data = dna, width = windowsize, by = windowsize, FUN = GC)
    plot(x, y, type="l", xlab=xlab, ylab="GC content")

    # y-axis: GC skew
    GCskew <- function(x){ y <- table(x); (y["c"] - y["g"]) / (y["c"] + y["g"]) }
    y <- rollapply(data = dna, width = windowsize, by = windowsize, FUN = GCskew)
    plot(x, y, type="l", xlab=xlab, ylab="GC skew"); abline(h = 0)
    plot(x, cumsum(y), type="l", xlab=xlab, ylab="Cumulative GC skew")

    dev.off() # close the device

    # open current working directory
    system("open .")

- [Hiromi Nishida "ゲノム比較解析"](https://sites.google.com/site/microbioinformatics/genomu-bi-jiao-jie-xi)
- [小池、木ノ内 (2010) "バクテリアの塩基配列における文字の含量を用いた解析"](http://www.topic.ad.jp/ipsj-tohoku/archive/2010/report/report14/10-6-A5-1.pdf)
- [Arakawa K, Tomita M. (2007)](https://www.ncbi.nlm.nih.gov/pubmed/19461976/) ["バクテリアゲノムの複製による選択度合いを定量化"](http://www.iab.keio.ac.jp/research/highlight/papers/200904130118.html)

![](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2684130/bin/EBO-03-159-g002.jpg)

----------
## References

2018/04/14(Sat)
https://connpass.com/event/75699/
Dr. Bonoの生命科学データ解析-読書会 @大阪

2017/12/16(Sat)
https://connpass.com/event/69633/
Dr. Bonoの生命科学データ解析-読書会

