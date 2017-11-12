**[DATA SCIENCE FOR GENOME DYNAMICS / GENOME INFORMATICS (GIGA)](https://github.com/haruosuz/DS4GD/tree/master/2017giga)**  
**生命動態のデータサイエンス**

----------

# Case Study
**ケーススタディ**

Table of Contents
- [2017-12-12](#2017-12-12)
- [2017-12-05](#2017-12-05)
- [LAST: Genome-Scale Sequence Comparison](#last)
- [Assignment 5](#assignment-5)
- [Assignment 4](#assignment-4)
- [ASSIGNMENT](#assignment)
- [UniProtKB Swiss-Prot protein sequence database](#uniprotkb-swiss-prot-protein-sequence-database)
- [NCBI assembly summary](#ncbi-assembly-summary)
- [Silva rRNA database](#silva-rrna-database)

----------
## 2017-12-12

----------
## 2017-12-05

### LAST
[LAST: Genome-Scale Sequence Comparison](http://last.cbrc.jp)

http://kazumaxneo.hatenablog.com/?page=1497582787
2017-06-15
ゲノムの相同性の高い領域の網羅的な検索 LAST
2017-06-15
Oxford Nanoporeリードのマッピング
http://kazumaxneo.hatenablog.com/archive/2017/06/15

Check compiler version using:

	gcc --version
	g++ --version

最新版のダウンロード

Download the lastest version [last-912.zip](http://last.cbrc.jp/last-912.zip) using:

	wget http://last.cbrc.jp/last-912.zip

インストール

[Installation](http://last.cbrc.jp/doc/last.html)

	# Setup
	unzip last-912.zip
	cd last-912/
	make

	# Install (optional)
	PATH_TO_LAST=/path/to/your/last-912
	make install prefix=$PATH_TO_LAST

	# Export LAST path (either add to .bashrc or type as is in the terminal):
	export PATH=$PATH:$PATH_TO_LAST/bin

使用法

Usage

[LAST Tutorial](http://last.cbrc.jp/doc/last-tutorial.html)

	cd $PATH_TO_LAST/examples

例1: ヒトとフグのミトコンドリアのゲノムを比較する

Example 1: Compare the human and fugu mitochondrial genomes

	lastdb -cR01 humdb humanMito.fa
	lastal humdb fuguMito.fa > myalns.maf

Understanding the output

	less -S myalns.maf

例2: 脊椎動物と無脊椎動物のタンパク質を比較する

Example 2: Compare vertebrate proteins to invertebrate proteins

	lastdb -p -cR01 invdb invertebrate.fa
	lastal invdb vertebrate.fa

----------

http://apprize.info/data/bioinformatics/3.html

see the newest files at the bottom

	ls -lrt

----------

Retrieving a DNA sequence from NCBI

    library("seqinr")
    ACCESSION <- "NC_001477"
    ld <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"))
    d <- ld[[1]]
    write.fasta(sequences=d, names=sapply(seqs, getAnnot), file.out=paste0(ACCESSION,".fna"))

https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#the-ncbi-sequence-database

Retrieving a list of DNA sequences from NCBI

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
    #write.fasta(sequences=seqs, names=seqnames, file.out="sequence.fasta")
    write.fasta(sequences=seqs, names=sapply(seqs, getAnnot), file.out="sequence.fna")

----------

	# read the sequence into R using the SeqinR package:
    library("seqinr")
    ACCESSION <- "NC_001477" # Dengue virus 1
    #ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
    ld <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"))
    d <- ld[[1]]

## Assignment 5
[Exercises on DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises)

[Answers to the exercises on DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#dna-sequence-statistics-2)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Draw a sliding window plot of GC content in the genome, using a window size of 200 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# write a function to make a sliding window plot:
    slidingwindowplotGC <- function(windowsize, inputseq)
    {
      require("zoo") # this function requires the 'zoo' R package # install.packages('zoo')
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = GC)
      plot(x, y, type="b", xlab="Position (bp)", ylab="GC content")
    }

	# make a sliding window plot with a window size of 200 nucleotides:
    slidingwindowplotGC(200, d)

	# make a sliding window plot of GC content using a window size of 2000 nucleotides:
    slidingwindowplotGC(2000, d)

Q2. Draw a sliding window plot of GC content in the genome sequence using a window size of 20000 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# make a sliding window plot with a window size of 20000 nucleotides:
    slidingwindowplotGC(20000, d)

Q3. Write a function to calculate the AT content of a DNA sequence (ie. the fraction of the nucleotides in the sequence that are As or Ts). What is the AT content of the genome?

	# Here is a function to calculate the AT content of a genome sequence:
    AT <- function(x){ library("seqinr"); 1 - GC(x) }

    # use the function to calculate the AT content of the genome:
    AT(d)

    # Create tests
    x <- s2c("atgc"); AT(x)

Q4. Write a function to draw a sliding window plot of AT content.

	# write a function to make a sliding window plot:
    slidingwindowplotAT <- function(windowsize, inputseq)
    {
      require("zoo")
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      AT <- function(x){ library("seqinr"); 1 - GC(x) }
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = AT)
      plot(x, y, type="b", xlab="Position (bp)", ylab="AT content")
    }

Use it to make a sliding window plot of AT content along the genome, using a windowsize of 2000 nucleotides. 

    par(mfrow=c(2,1))
	# make a sliding window plot of AT content:
    slidingwindowplotAT(2000, d)
	# This is the mirror image of the plot of GC content (because AT equals 1 minus GC):
    slidingwindowplotGC(2000, d)

Q5. Is the 3-nucleotide word GAC over-represented or under-represented in the genome sequence?

	# search for a function to calculate rho by typing:
	help.search("rho")

	# calculate Rho for words of length 3 in the genome
	rho(d, wordsize=3)

### G-language
REST Web Service for Genome Analysis
[English](http://www.g-language.org/wiki/restgenomeanalysisenglish)
[日本語](http://www.g-language.org/wiki/restgenomeanalysisjapanese)

- http://rest.g-language.org/NC_000908 shows genome information for Dengue virus 1 (Accession: NC_000908)
- http://rest.g-language.org/help/gcwin shows a documentation for the 'gcwin' function.
- http://rest.g-language.org/NC_000908/gcwin calculates GC content along the genome.
- http://rest.g-language.org/NC_000908/gcwin/window=2000 uses 2,000-bp window size instead of the default 10,000-bp window size.
- http://rest.g-language.org/NC_000908/gcwin/window=2000/at=1 calculates AT content instead of GC content.

----------
## Assignment 4
[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

[Answers to the exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#dna-sequence-statistics-1)

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
## ASSIGNMENT
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
----------

## UniProtKB Swiss-Prot protein sequence database
[Swiss-Prot](https://ja.wikipedia.org/wiki/Swiss-Prot)タンパク質配列データベース

### Website
[UniProt](http://www.uniprot.org)の[Download latest release](http://www.uniprot.org/downloads)を開く。  
<ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/> をブラウザ（Firefox または Chrome）で開く。  
*uniprot_sprot.fasta.gz* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

Go the UniProt website (http://www.uniprot.org), and then click the link "Download latest release".  
Open the URL <ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/> with your browser (Firefox or Chrome).  
Right click the link *uniprot_sprot.fasta.gz* and select "Copy Link Address".

### Download data

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    # change shell to bash
    bash

ディレクトリを作成する:  

    # make directories
    mkdir -p ~/projects/uniprot_sprot/data

ディレクトリを移動する:  

    # change directories
    cd ~/projects/uniprot_sprot/data/

圧縮ファイル（*uniprot_sprot.fasta.gz*）を`wget`または`curl`でダウンロードする:  

    # download data with wget and curl
      #wget ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz
    curl -O ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz

`gunzip`コマンドで解凍する:  

    # decompress files with the command gunzip
    gunzip -c uniprot_sprot.fasta.gz > uniprot_sprot.fasta

### Inspect data

`ls -lh`でファイルサイズを確認する:  

    # ls -lh reports human-readable file sizes
    ls -lh

[`cat`](https://ja.wikipedia.org/wiki/Cat_%28UNIX%29)でファイルを標準出力する（Control-Cで動作中のプロセスを停止）:  

    # print a file's contents to standard out (use Control-C to stop)
    cat uniprot_sprot.fasta

[`head`](http://codezine.jp/unixdic/w/head)で先頭部分を表示する:  
[`tail`](http://codezine.jp/unixdic/w/tail)で末尾部分を表示する:  

    # inspect data with Head and Tail
    head uniprot_sprot.fasta
    tail uniprot_sprot.fasta

Extract [FASTA headers](http://www.uniprot.org/help/fasta-headers):

    >db|UniqueIdentifier|EntryName ProteinName OS=OrganismName[ GN=GeneName]PE=ProteinExistence SV=SequenceVersion

`grep`で、[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式ファイルのヘッダ（`>`で始まる行）にマッチする行を抽出する:  

    # use grep to extract lines matching the pattern "^>"
    grep "^>" uniprot_sprot.fasta

Pipe the standard output to the next command with the pipe character (|).

[パイプ](https://ja.wikipedia.org/wiki/パイプ_%28コンピュータ%29)でプログラムの入出力をつなぐ。

配列の数をカウントする:  

    # wc -l outputs the number of lines
    grep "^>" uniprot_sprot.fasta | wc -l

日本語にちなんで命名されたタンパク質遺伝子 [harakiri, Izumo, Musashi, Shugoshin, Tonsoku](https://ja.wikipedia.org/wiki/Izumo_%28タンパク質%29#.E9.96.A2.E9.80.A3.E9.A0.85.E7.9B.AE) を検索する。

    # use grep to find a gene "harakiri"
    grep "^>" uniprot_sprot.fasta | grep "harakiri"

    # use grep to count (the -c option stands for count) the number of lines matching the pattern
    grep "^>" uniprot_sprot.fasta | grep -c "Shugoshin"

    # add the option -i to grep to be case insensitive.
    grep "^>" uniprot_sprot.fasta | grep -ci "Shugoshin"

`grep`コマンドは、`-c`オプションでパターンにマッチした行数を表示し、`-i`オプションで大文字小文字を区別しない（ignore case）。

**"harakiri"検索結果**

    # Search Results for "harakiri". There are 3 entries for in the FASTA file.
    >sp|O00198|HRK_HUMAN Activator of apoptosis harakiri OS=Homo sapiens GN=HRK PE=1 SV=1
    >sp|P62816|HRK_MOUSE Activator of apoptosis harakiri OS=Mus musculus GN=Hrk PE=3 SV=1
    >sp|P62817|HRK_RAT Activator of apoptosis harakiri OS=Rattus norvegicus GN=Hrk PE=3 SV=1

"harakiri"遺伝子は3件登録されていた。
タンパク質名(`ProteinName`)は`Activator of apoptosis harakiri`。
生物名(`OS=OrganismName`)より、ヒト(`Homo sapiens`)、ハツカネズミ(`Mus musculus`)、ドブネズミ(`Rattus norvegicus`)の3種に由来する配列であることがわかる。
遺伝子名(`GN=GeneName`)に大文字と小文字（`GN=HRK`と`GN=Hrk`）が存在した。

**"Shugoshin"検索結果**

    # Search Results for "Shugoshin". There are 19 entries for in the FASTA file.
    >sp|Q0WTB8|SGO2_ARATH SHUGOSHIN 2 OS=Arabidopsis thaliana GN=SGO2 PE=2 SV=1
    >sp|Q562F6|SGO2_HUMAN Shugoshin 2 OS=Homo sapiens GN=SGO2 PE=1 SV=2
    >sp|Q7TSY8|SGO2_MOUSE Shugoshin 2 OS=Mus musculus GN=Sgo2 PE=1 SV=1
    >sp|O13734|SGO2_SCHPO Shugoshin-2 OS=Schizosaccharomyces pombe (strain 972 / ATCC 24843) GN=sgo2 PE=1 SV=1

"Shugoshin"にマッチする遺伝子は19件登録されていた。
タンパク質名(`SHUGOSHIN 2, Shugoshin 2, Shugoshin-2`)と遺伝子名(`SGO2, Sgo2, sgo2`)に表記揺れ（用語の不統一、大文字と小文字）が認められた。

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[パッケージ](https://stats.biopapyrus.jp/r/basic/package.html)`seqinr`を呼び出す:  

    # Load the SeqinR package
    library(seqinr)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # Set and Get Working Directory
    setwd("~/projects/uniprot_sprot/data/")
    getwd()

    # List the Files in a Directory
    dir()

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data
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
文字列（"harakiri", "Shiga.* toxin", "Rhodopsin OS=(生物名)" 等）のパターンにマッチする要素番号を取得する:  

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

    setwd("~/projects/uniprot_sprot/data/")                                            # Set Working Directory
    library(seqinr)                                                                    # Load the SeqinR package
    lx <- read.fasta(file = "mySequences.fasta", seqtype = c("AA"), strip.desc = TRUE) # Reading sequence data
    unlist(getAnnot(lx))                                                               # get sequence annotations

#### Amino acid usage
**タンパク質の[アミノ酸組成](https://kotobank.jp/word/アミノ酸組成-761227)**

[アミノ酸の物性](https://www.thermofisher.com/jp/ja/home/life-science/protein-biology/protein-biology-learning-center/protein-biology-resource-library/pierce-protein-methods/amino-acid-physical-properties.html)

![http://www.jalview.org/help/html/misc/aaproperties.html](http://www.jalview.org/help/html/misc/properties.gif)

[タンパク質の配列から機能を予測する](http://www.iu.a.u-tokyo.ac.jp/lectures/AG01/100511/motif.html) 平成22年度、清水謙多郎

`sapply()`は、リストの各要素に関数を適用する。タンパク質配列の長さ（アミノ酸残基数）を求める:  

    # Apply a Function over a List
    # get the length of sequences
    sapply(lx, length)

`summary()`関数でデータの要約:
 
    # Object Summaries
    summary(lx[[1]])

配列の長さ(length)、アミノ酸組成(composition)、物理化学的クラスの割合(AA.Property)が出力される。

[`AAstat()`](https://www.rdocumentation.org/packages/seqinr/versions/3.3-3/topics/AAstat)
関数を用いて、タンパク質の配列情報（アミノ酸残基数、物理化学的クラスの割合、等電点の理論値）を求める:  

    ?AAstat

    # Get protein statistics
    AAstat(lx[[1]])

![http://www.r-exercises.com/2017/05/10/accessing-and-manipulating-biological-databases-solutions-part-3/](http://www.r-exercises.com/wp-content/uploads/2017/05/Fig3-300x300.png)

アミノ酸の個数を出力:  

    # Get amino acid counts
    AAstat(lx[[1]], plot = FALSE)$Compo

物理化学的クラス (Tiny, Small, Aliphatic, Aromatic, Non-polar, Polar, Charged, Positive, Negative) の割合を出力:

    # Get the percentage of each physico-chemical classes
    AAstat(lx[[1]], plot = FALSE)$Prop

    AAstat(lx[[1]], plot = FALSE)$Prop$Aromatic

`sapply()`関数は、リストの各要素に関数を適用する。複数タンパク質配列の物理化学的クラスの割合を求める:  

    # Apply a Function over a List
    # get the percentage of each physico-chemical classes
    sapply(lx, function(x) AAstat(x, plot=FALSE)$Prop )

複数タンパク質配列のアミノ酸使用の絶対度数と相対度数を求める:  

    # absolute frequencies
    X <- sapply(lx, function(x) AAstat(x, plot=FALSE)$Compo )

    # relative frequencies
    X <- sapply(lx, function(x) summary(x)$composition )

データをカンマ区切りファイルとして出力する:  

    # Export data as a CSV file to be read by spreadsheets:
    write.csv(t(X), file="table.csv")

    # open current working directory
    system("open .")

タンパク質のアミノ酸使用パターンを比較する。`matplot()`関数でプロットする:  

    # plot amino acid usage profiles together using matplot
    matplot(X, type="l", col=rainbow(12), lty=1:6)
    legend("topleft", legend=colnames(X), col=rainbow(12), lty=1:6)
    # lty: 0=blank, 1=solid (default), 2=dashed, 3=dotted, 4=dotdash, 5=longdash, 6=twodash

クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)

    # Hierarchical cluster analysis
    plot(hclust(dist(t(X))))

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    # Heatmap for amino acid usage profiles
    heatmap(t(X))

#### [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
ペアワイズ配列アラインメント

ドットプロットで2つの配列を比較:  

    # Comparing two sequences using a dotplot
    s1 <- lx[[1]]
    s2 <- lx[[3]]
    dotPlot(s1, s2)
    nmbr <- 3; dotPlot(s1, s2, wsize = nmbr, wstep = nmbr, nmatch = nmbr, xlab = getName(s1), ylab = getName(s2))

for文でループ処理を行う。複数のドットプロットをファイル出力する:  
 
    pdf("Rplot.pdf") # create a PDF device called "Rplot.pdf"
    for (n1 in 1:length(lx)) {
      for (n2 in n1:length(lx)) {
        s1 <- lx[[n1]]
        s2 <- lx[[n2]]
        dotPlot(s1, s2, xlab=getName(s1), ylab=getName(s2))
      }
    }
    dev.off(which = dev.cur()) # close the device

2つのタンパク質配列間の大域的/局所的アライメント:  

    # Pairwise global/local alignment of protein sequences
    library(Biostrings)
    data(BLOSUM50)
    type <- "global" # Pairwise global alignment
    #type <- "local" # Pairwise local alignment
    aln <- pairwiseAlignment(toupper(c2s(s1)), toupper(c2s(s2)), substitutionMatrix = BLOSUM50, 
                             gapOpening = -2, gapExtension = -8, scoreOnly = FALSE, type = type)
    writePairwiseAlignments(aln)
    writePairwiseAlignments(aln, file=paste0(type,"_aln.txt") )

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

    # 多重アライメント
    # Reading a multiple alignment file into R
    library(seqinr)
    myAln <- read.alignment(file = "myAlignment.fasta", format = "fasta")

    # 距離
    # Calculating genetic distances between protein sequences
    mydist <- dist.alignment(myAln)

    # 無根系統樹
    # Building an unrooted phylogenetic tree
    #install.packages("ape")
    library(ape)
    mytree <- nj(mydist)
    plot.phylo(mytree, type = "unrooted") # type = "phylogram", "cladogram", "fan", "unrooted", "radial"

    # 有根系統樹
    # Building a rooted phylogenetic tree
    #library(phangorn); mytree <- midpoint(mytree) # midpoint rooting
    outgroup <- "DANRE"
    mytree <- root(mytree, outgroup = grep(pattern = outgroup, x = mytree$tip.label), resolve.root = TRUE)
    plot.phylo(ladderize(mytree, right = FALSE), main = "Phylogenetic Tree")

    # Saving a phylogenetic tree as a Newick-format tree file
    write.tree(mytree, file="myTree.newick")

[SeaView](http://doua.prabi.fr/software/seaview)でnewick形式ファイルの系統樹を表示する。

[ロドプシン (Rhodopsin)](https://ja.wikipedia.org/wiki/ロドプシン) のタンパク質配列の多重配列アライメントに基づく系統樹を構築する。
外群として ゼブラフィッシュ (Danio rerio、略して"DANRE") を選択し、系統樹に根をつける。
有根系統樹より、
最初にアフリカツメガエル (Xenopus laevis、略して"XENLA") と他の集団が分岐し、
次にウシ (Bos taurus、"BOVIN") と他の集団が分岐し、
最後にヒト ("HUMAN") とネズミ ("RAT"と"MOUSE") が分岐したと推定される。

### BLAST

	# change directories
	cd ~/projects/uniprot_sprot/data/
	
	# Variables
	QUERY=mySequences.fasta
	DB=uniprot_sprot.fasta
	PROGRAM=blastn; DBTYPE=nucl
	PROGRAM=blastp; DBTYPE=prot
	OUT=${PROGRAM}-$(basename $QUERY)-$(basename $DB).txt
	EVALUE=1e-20

	# Building a BLAST database with local sequences
	makeblastdb -in $DB -dbtype $DBTYPE -hash_index -parse_seqids

	# Running BLAST
	$PROGRAM -db $DB -query $QUERY -out $OUT \
	 -evalue $EVALUE \
	 -max_target_seqs 20 \
	 -max_hsps 1 \
	 -outfmt 7

	# -max_target_seqs $(grep -c '^>' $DB) \
	# 6 = Tabular, 7 = Tabular with comment lines,

### References
- [Swiss-Prot - Wikipedia](https://ja.wikipedia.org/wiki/Swiss-Prot)
- [Nucleic Acids Res. 2015 Jan;43(Database issue):D204-12. UniProt: a hub for protein information.](http://www.ncbi.nlm.nih.gov/pubmed/25348405)
- [Database (Oxford). 2014 Mar 12;2014:bau016. Expert curation in UniProtKB: a case study on dealing with conflicting and erroneous data.](http://www.ncbi.nlm.nih.gov/pubmed/24622611)

- BLAST
 - [Local BLAST の使い方〜導入・準備編（MacOSX版）〜 2011 - 統合TV (togotv)(2011-04-20)](http://togotv.dbcls.jp/20110420.html)
 - [Local BLAST の使い方〜検索実行・オプション編（MacOSX版）〜 2011 - 統合TV (togotv)(2011-06-08)](http://togotv.dbcls.jp/20110608.html)
 - [Local BLAST (togotv)(2011-02-25)](http://togotv.dbcls.jp/20110225.html)
 - [BLASTパッケージのインストール](http://bio-info.biz/tips/other_install_blast.html)
 - [BLASTデータベースの作り方について](http://bio-info.biz/tips/other_blast_db.html)
 - [井上 潤：Blast+](http://www.geocities.jp/ancientfishtree/BLASTplus_JI.html)

- BLAST® Command Line Applications User Manual - NCBI Bookshelf
- [Options for the command-line applications.](http://www.ncbi.nlm.nih.gov/books/NBK279675/)

- [Building a BLAST database with local sequences](http://www.ncbi.nlm.nih.gov/books/NBK279688/)
- [BLASTデータベースの作り方について](http://bio-info.biz/tips/other_blast_db.html)
- [makeblastdb | blast検索用のデータベースを作成する方法](http://bi.biopapyrus.net/seq/blast/makeblastdb.html)

- [Extracting data from BLAST databases with blastdbcmd](http://www.ncbi.nlm.nih.gov/books/NBK279689/)
- [自家製BLAST用DBから必要な配列エントリ取得 | ぼうのブログ](http://bonohu.jp/blog/2014/08/08/yetanother-blastdbcmd/)
- [Blasted Bioinformatics!?: My IDs not good enough for NCBI BLAST+](http://blastedbio.blogspot.com/2012/10/my-ids-not-good-enough-for-ncbi-blast.html)

----------
----------

## NCBI assembly summary
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)のゲノム配列のメタデータが記載されている。

ftp://ftp.ncbi.nlm.nih.gov/genomes/README_assembly_summary.txt

	The assembly_summary files report metadata for the genome assemblies on the NCBI genomes FTP site.
	assembly_summary_genbank.txt            - current GenBank genome assemblies
	assembly_summary_refseq.txt             - current RefSeq genome assemblies

- [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
- [RefSeq - JI 井上 潤](http://www.geocities.jp/ancientfishtree/RefSeq.html)
- [RefSeq | 重複のない生物の遺伝子データベース（ゲノムデータベース）](http://bi.biopapyrus.net/biodb/refseq.html)

### Website
NCBIウェブサイト (https://www.ncbi.nlm.nih.gov) にアクセスし、右下のリンク"NCBI FTP Site"をクリックして開く。  
<ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> をブラウザ（Firefox または Chrome）で開く。  
*assembly_summary_genbank.txt*, *assembly_summary_refseq.txt*を右クリックし、「リンクのURLをコピー (Copy Link)」する。

Go to the NCBI website (https://www.ncbi.nlm.nih.gov), and then click the link "NCBI FTP Site".   
Open the URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> with your browser (Firefox or Chrome).  
Right click the link *assembly_summary_genbank.txt*, *assembly_summary_refseq.txt*, and select "Copy Link Address".

### Download data

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    # change shell to bash
    bash

ディレクトリを作成し移動する:  

    # make directories
    mkdir -p ~/projects/ncbi_assembly_summary/data

    # change directories
    cd ~/projects/ncbi_assembly_summary/data/

[How can I find the sequence and annotation of my genome of interest?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#howtofind)

[assembly summary report files](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#asmsumfiles)

GenBankとRefSeqのゲノム配列のメタデータを記載したファイルを`wget`でダウンロードする:  

    # Download the two master assembly summary files that report assembly meta-data
    wget --background \
     ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_genbank.txt \
     ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt

`tail -f`でファイル出力を監視する（Control-Cで動作中のプロセスを停止）:  

    # Use `tail -f` to constantly monitor files (use Control-C to stop)
    tail -f wget-log

GenBankまたはRefSeqのゲノム配列のメタデータを確認する:  

変数に値（ファイル名）を割り当てる:  

    # create a variable and assign it a value
    FILE="assembly_summary_genbank.txt"
    FILE="assembly_summary_refseq.txt"

ファイルのヘッダ（`#`で始まる行）を確認する:  

    # use grep to extract header lines (those that begin with #)
    grep "^#" $FILE

http://apprize.info/data/bioinformatics/7.html

    # pipe output to `less`, and then press / and enter -N (--LINE-NUMBERS)
    grep "^#" $FILE | tail -n 1 | tr "\t" "\n" | less

アセンブリの状況（assembly_level: Contig, Scaffold, Chromosome, Complete Genome）を確認する:  

    # Pipe the standard output to the next command with the pipe character (|)
    # Using grep, cut, sort, uniq to summarize columns of data
    grep -v "^#" $FILE | cut -f12 | sort | uniq -c

[腸管出血性大腸菌O157](https://ja.wikipedia.org/wiki/O157) [Escherichia coli O157:H7 Sakai](http://integbio.jp/dbcatalog/record/nbdc00058) の完全ゲノム("Complete Genome")配列データの最新版("latest")のURLを抽出する:  

List the ftp_path (column 20) for the assemblies of interest, in this case those that have organism_name of "Escherichia coli O157:H7 Sakai" (column 8), "latest" version_status (column 11) and "Complete Genome" assembly_level (column 12)

    NAME="O157.*Sakai"
    ftpdirpaths=(`awk -F "\t" '$8 ~ /'"$NAME"'/ && $11=="latest" && $12 ~ /Complete Genome/ {print $20}' $FILE`)

抽出されたURLを表示する:  

    # All elements are extracted with:
    echo ${ftpdirpaths[@]}

抽出されたURLの数を確認する:  

    # access how many elements are in the array (and each element’s index) with the following:
    echo ${#ftpdirpaths[@]}
    echo ${!ftpdirpaths[@]}

抽出されたURL <ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/008/865/GCF_000008865.1_ASM886v1> をブラウザFirefox/Chromeで開く。

    ファイル名と内容
    *_genomic.gbff.gz: GenBank flat file format - GenBank形式ファイル
    *.fna.gz: FASTA Nucleic Acids - ゲノム塩基配列
    *.faa.gz: FASTA Amino Acids - 各タンパク質のアミノ酸配列

Open the URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/008/865/GCF_000008865.1_ASM886v1> with your browser (Firefox or Chrome).  

    File formats and content
    *_genomic.gbff.gz: GenBank flat file format of the genomic sequence(s).
    *_genomic.fna.gz: FASTA format of the genomic sequence(s).
    *_protein.faa.gz: FASTA format of the protein sequence(s).

ftp://ftp.ncbi.nlm.nih.gov/genomes/all/README.txt

*README.txt*ファイル、[MD5](https://ja.wikipedia.org/wiki/MD5)[チェックサム](https://ja.wikipedia.org/wiki/チェックサム)ファイル（*md5checksums.txt*）、[GenaBank](http://bi.biopapyrus.net/biodb/genbank.html)形式と[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式の圧縮ファイル（*.gz*）を`wget`でダウンロードする:  

    # Data files could be downloaded using the following commands:
    for URL in ${ftpdirpaths[@]}
    do
      wget $URL/{README.txt,md5checksums.txt,*_genomic.gbff.gz,*_genomic.fna.gz,*_protein.faa.gz}
    done

    # see the newest files
    ls -lrt

`md5`コマンドでチェックサムを計算し、公表されている値と一致するか確認する:  

    # compare MD5 checksum values with those in *md5checksums.txt*
    md5 *.gz
    cat md5checksums.txt

[How can I download RefSeq data for all complete bacterial genomes?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#allcomplete)
Also see the Downloading Genomic Data Factsheet.
ftp://ftp.ncbi.nlm.nih.gov/pub/factsheets/HowTo_Downloading_Genomic_Data.pdf

    NAME="Ensifer|Sinorhizobium"
    awk -F "\t" '$8 ~ /'"$NAME"'/ && $11=="latest" && $12 ~ /Complete/ && $5 ~ /representative/ {print $20}' $FILE > ftpdirpaths
    awk 'BEGIN{FS=OFS="/";filesuffix="genomic.fna.gz"}{ftpdir=$0;asm=$10;file=asm"_"filesuffix;print ftpdir,file}' ftpdirpaths > ftpfilepaths
    wget -i ftpfilepaths

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[パッケージ](https://stats.biopapyrus.jp/r/basic/package.html)`seqinr`を呼び出す:  

    # Load the SeqinR package
    library(seqinr)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # Set and Get Working Directory
    setwd("~/projects/ncbi_assembly_summary/data/")
    getwd()

    # List the Files in a Directory
    dir()

#### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)

[Reading sequence data into R](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#reading-sequence-data-into-r)

    # `read.fasta()`関数で配列データを読み込む:  
    ld <- read.fasta(file = "GCF_000008865.1_ASM886v1_genomic.fna.gz", seqtype = c("DNA"), strip.desc = TRUE)

配列の数をカウントする:  

    # get the number of elements
    length(ld)

[`getAnnot`](https://rdrr.io/rforge/seqinr/man/getAnnot.html)
関数を用いて、配列のアノテーションを取得する:  

    # get sequence annotations
    getAnnot(ld)

1個の染色体(chromosome)と2個のプラスミド(plasmid)を含む。

変数`dna`にリストの1番目の要素を代入する:  

    # store the first element of the list object `ld` in a variable `dna`
    dna <- ld[[1]]

[Length of a DNA sequence](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#length-of-a-dna-sequence)

    # DNA配列の長さ
    length(dna)

[Base composition of a DNA sequence](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#base-composition-of-a-dna-sequence)

    # DNA配列の塩基組成
    table(dna)

[GC Content of DNA](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#gc-content-of-dna)

    # DNA配列のGC含量
    GC(dna)

`summary()`関数でデータの要約:  

    # Object Summaries
    summary(dna)

DNA配列の長さ(length)、塩基組成(composition)、GC含量(GC)が出力される。

[DNA words](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-words)

    # 2連続塩基含量
    count(dna, 2)

#### [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)

[A sliding window plot of GC content](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#a-sliding-window-plot-of-gc-content)

    # GC含量の局所変動
    # install.packages('zoo')
    library(zoo)
    windowsize <- 100000
    x <- seq(from = 1, to = length(dna)-windowsize, by = windowsize)
    y <- rollapply(data = dna, width = windowsize, by = windowsize, FUN = GC)
    plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")

[Over-represented and under-represented DNA words](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#over-represented-and-under-represented-dna-words)

    # 2連続塩基組成（観測値/期待値）
    rho(dna, wordsize = 2)
    
    par(cex=0.7)
    barplot(sort(rho(dna, wordsize = 2)))
    abline(h=1)

配列間の2連続塩基組成プロファイルを比較する。
全ての配列 (1個の染色体と2個のプラスミド) について、2連続塩基組成を求める。
`sapply()`関数は、リストの各要素に関数を適用する:  

    # Apply a Function over a List
    X <- sapply(ld, rho)

`matplot()`関数でプロットする:  

    matplot(X, type="l", col=1:ncol(X), lty=1:ncol(X))
    legend("topleft", legend=colnames(X), col=1:ncol(X), lty=1:ncol(X))

クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)

    # Hierarchical cluster analysis
    plot(hclust(dist(t(X))))

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    heatmap(X, margins=c(15,5))

### References

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/
Genomes Download FAQ

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#protocols
2. What is the best protocol to use to download large data sets?

http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#howtofind
12. How can I find the sequence and annotation of my genome of interest?

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#allcomplete
15. How can I download RefSeq data for all complete bacterial genomes?

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

    wget --background https://www.arb-silva.de/fileadmin/silva_databases/current/Exports/{README.txt,SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz.md5,SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz}

`tail -f`でファイル出力を監視する（Control-Cで動作中のプロセスを停止）:  

    # Use `tail -f` to constantly monitor files (use Control-C to stop)
    tail -f wget-log

`md5`コマンドでチェックサムを計算し、公表されている値（492e513a8cc2de298a9b4121c9696278）と一致するか確認する:  

    md5 SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz
    cat SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta.gz.md5

### Inspect data

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

### BLAST

    # Variables
    PROGRAM=blastp; DBTYPE=prot
    PROGRAM=blastn; DBTYPE=nucl
    DB="SILVA_128_SSURef_Nr99_tax_silva_trunc.fasta"

    # Building a BLAST database with local sequences
    makeblastdb -in $DB -dbtype $DBTYPE -hash_index -parse_seqids

    NAME=X96963.1.1488 # Shigella flexneri

    # Extracting data from BLAST databases with blastdbcmd
    blastdbcmd -db $DB -entry all -outfmt "%i %t" | grep "$NAME" | \
    # grep -v "Chloroplast\|Mitochondria" | \
    awk '{print $1}' | blastdbcmd -db $DB -entry_batch - > $NAME.fasta

    QUERY=$NAME.fasta
    EVALUE=1e-20
    OUT=${PROGRAM}-$(basename $QUERY)-$(basename $DB).txt
    n_cores=$(getconf _NPROCESSORS_ONLN)

    # Running BLAST
    $PROGRAM -db $DB -query $QUERY -out $OUT \
     -evalue $EVALUE \
     -max_target_seqs $(grep -c '^>' $DB) \
     -max_hsps 1 \
     -outfmt 7 \
     -num_threads "${n_cores}"

     # -max_target_seqs 1 \
     # 6 = Tabular, 7 = Tabular with comment lines,


    # Extracting data from BLAST databases with blastdbcmd
    SEQ=$PROGRAM-$(basename $QUERY)-$(basename $DB).fasta
    cat $OUT | grep -v "^#" | awk '{print $2}' | sort -u | blastdbcmd -db $DB -entry_batch - > $SEQ


### References
- [SILVA ribosomal RNA database - Wikipedia](https://en.wikipedia.org/wiki/SILVA_ribosomal_RNA_database)
- [blastn for silva database (SE)](http://cell-innovation.nig.ac.jp/wiki2/tiki-index.php?page=P000001306)

----------
----------

http://apprize.info/data/bioinformatics/3.html
Remedial Unix Shell - Prerequisites: Essential Skills for Getting Started with a Bioinformatics Project - Bioinformatics Data Skills (2015)

http://apprize.info/data/bioinformatics/6.html
Bioinformatics Data - Prerequisites: Essential Skills for Getting Started with a Bioinformatics Project - Bioinformatics Data Skills (2015)

http://apprize.info/data/bioinformatics/7.html
Unix Data Tools - Practice: Bioinformatics Data Skills - Bioinformatics Data Skills (2015)

http://apprize.info/data/bioinformatics/12.html
Bioinformatics Shell Scripting, Writing Pipelines, and Parallelizing Tasks - Practice: Bioinformatics Data Skills - Bioinformatics Data Skills (2015)




