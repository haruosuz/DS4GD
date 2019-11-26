**[DATA SCIENCE FOR GENOME DYNAMICS (GIGA)](https://github.com/haruosuz/DS4GD/tree/master/2019giga)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「Introduction to R」
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages seqinr & Biostrings」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題No.5 「NCBI accession」
- [NCBI ASSEMBLY_REPORTS](#ncbi-assembly_reports)
- [NCBI RefSeq Release](#ncbi-refseq-release)
- [assignment 8](#assignment-8) 課題No.8 「dotplot」
- [2019-11-26](#2019-11-26)
- [assignment 9](#assignment-9) 課題No.9 「Guest Speaker (1)」
- [assignment 10](#assignment-10) 課題No.10 「Guest Speaker (2)」
- [E-utilities](#e-utilities)
- [Coding sequences](#coding-sequences) タンパク質コード配列
- [assignment 11](#assignment-11) 課題No.11 「Pairwise Sequence Alignment」
- [assignment 12](#assignment-12) 課題No.12 「draft report」
- [assignment 13](#assignment-13) 課題No.13 「presentation slides」

----------
## assignment 0
**選抜課題**

【ASSIGNMENT】
Please describe biological (genome/gene/protein) sequences you're interested in. Please also state your project title and references.

【課題内容】
本授業で解析したい興味ある生物（ゲノム/遺伝子/タンパク質）配列を述べてください。課題のタイトルと参考文献も明記してください。

----------
## assignment 1
**課題No.1 「Introduction to R」**

Watch the following videos and write your comments or questions.- [Introduction to R](https://www.youtube.com/watch?v=WiO44CiSPF0&list=PL8eNk_zTBST_KL2gnciUv1oor0ECw8Hqg)

[Example answer]

I watched the videos #2 to #17 of [Introduction to R](https://www.youtube.com/watch?v=WiO44CiSPF0&list=PL8eNk_zTBST_KL2gnciUv1oor0ECw8Hqg). My questions are as follows:
1. What is difference between Data Frames and Lists in R?


以下の動画レッスンを見て、疑問点を報告する。
- [R言語入門 (全13回)](http://dotinstall.com/lessons/basic_r)

[回答例]

[R言語入門 (全13回)](http://dotinstall.com/lessons/basic_r)の動画レッスン番号 #03 ~ #13 を見た。疑問点は次の通りである。
1. 行列とデータフレームとリストの違いが理解できなかった。
2. 因子ベクトルというものがよくわからなかった。

----------
## assignment 2
**課題No.2 「Installing R packages seqinr & Biostrings」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

RパッケージseqinrとBioconductorパッケージBiostringsをインストールする。

パッケージseqinrのインストール:  

    # Install the "seqinr" package:
    install.packages("seqinr")

BioconductorパッケージBiostringsのインストール:  

    # Install the Bioconductor package called "Biostrings":
    #install.packages("BiocManager")
    BiocManager::install("Biostrings")

Rのバージョンを確認:  

    # Print the version of R running:
    R.version.string

Rパッケージのバージョンを確認:  

    # Print the versions of these packages:
    packageVersion("seqinr")
    packageVersion("Biostrings")

パッケージの呼び出し:  

    # Load the packages into R:
    library("seqinr")
    library("Biostrings")

回答例:  
```
# Example answer:  

> R.version.string[1] "R version 3.6.1 (2019-07-05)"> packageVersion("seqinr")[1] ‘3.6.1’
> packageVersion("Biostrings")[1] ‘2.52.0’
```

----------
## assignment 3
**課題No.3 「DNA Sequence Statistics (1)」**

[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. What are the last twenty nucleotides of the genome sequence?

    tail(seq1, 20)

Q2. What is the length in nucleotides of the genome sequence?

    length(seq1)

Q3. How many of each of the four nucleotides A, C, T and G, and any other symbols, are there in the genome sequence?

    table(seq1)

DDBJ [配列の記載に用いる略号](http://www.ddbj.nig.ac.jp/sub/code-j.html)  
DDBJ [Codes Used in Sequence Description](https://www.ddbj.nig.ac.jp/ddbj/code-e.html)

Q4. What is the GC content of the genome sequence, when (i) all non-A/C/T/G nucleotides are included, (ii) non-A/C/T/G nucleotides are discarded?

	help("GC")
    GC(seq1)
    GC(seq1, exact=FALSE)
    GC(seq1, exact=TRUE)

Q5. How many of each of the four nucleotides A, C, T and G are there in the complement of the genome sequence?

![http://revertra.webcrow.jp/DNA/index.php](http://revertra.webcrow.jp/DNA/dnaseq.png)

	#help.search("complement")
	#help("comp")
    table(comp(seq1))

Q6. How many occurrences of the DNA words CC, CG and GC occur in the genome sequence?

    count(seq=seq1, wordsize=2)

Q7. How many occurrences of the DNA words CC, CG and GC occur in the (i) first 1000 and (ii) last 1000 nucleotides of the genome sequence?
How can you check that the subsequence that you have looked at is 1000 nucleotides long?

    count(seq=head(seq1, 1000), wordsize=2)
    count(seq=tail(seq1, 1000), wordsize=2)

----------
## NCBI Genome List

- [Tatusova et al. Nucleic Acids Res. 2015 Jan;43(Database issue):D599-605. "Update on RefSeq microbial genomes resources."](https://www.ncbi.nlm.nih.gov/pubmed/25510495)
- [*Sinorhizobium meliloti*](https://en.wikipedia.org/wiki/Sinorhizobium_meliloti)
  - [López et al. MBio. 2019 May 28;10(3). pii: e00505-19. "Codon Usage Heterogeneity in the Multipartite Prokaryote Genome: Selection-Based Coding Bias Associated with Gene Location, Expression Level, and Ancestry."](https://www.ncbi.nlm.nih.gov/pubmed/31138741)
- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for the bacterial species *Sinorhizobium meliloti*, you would type just Organism name "Sinorhizobium meliloti" in the search box and press "Search".
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Sinorhizobium%20meliloti), you will see the number of hits to "Sinorhizobium meliloti" in each of the NCBI databases: "Overview (1); Eukaryotes (0); Prokaryotes (199); Viruses (0); Plasmids (65); Organelles (0)". When you click on "Prokaryotes", it will show all the strains belonging to the species.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Sinorhizobium%20meliloti), When you click on the Organism Name "Sinorhizobium meliloti 1021", it will bring you to the record for this organism in the NCBI Genome database.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/1004?genome_assembly_id=300472), you will see the "Summary", "Publications", and "Replicon Info" of the Organism *Sinorhizobium meliloti* 1021. The NCBI accessions for the DNA sequences of the chromosome (Chr) and plasmids (Plsm) pSymA and pSymB are "NC_003047.1", "NC_003037.1" and "NC_003078.1", respectively.

NCBIからDNA配列を取得する:  
```
# Retrieving a DNA sequence from NCBI
library("seqinr")
ACCESSION <- "NC_001477" # Dengue virus 1
#ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
#ACCESSION <- "NC_003037.1" # Sinorhizobium meliloti 1021 plasmid pSymA
# TogoWS REST service http://togows.dbcls.jp/site/en/rest.html
filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 4
**課題No.4 「DNA Sequence Statistics (2)」**

[Exercises on DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

[53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
フォント・ファミリーを指定する

    # setting font in plots
    par(family="mono")

Q1. Draw a sliding window plot of GC content in the genome, using a window size of 200 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# write a function to make a sliding window plot:
    slidingwindowplotGC <- function(windowsize, inputseq)
    {
      require("zoo") # this function requires the 'zoo' R package # install.packages('zoo')
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = GC)
      plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")
    }

	# make a sliding window plot with a window size of 200 nucleotides:
    slidingwindowplotGC(windowsize = 200, inputseq = seq1)

Q2. Draw a sliding window plot of GC content in the genome sequence using a window size of 2000 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# make a sliding window plot of GC content using a window size of 2000 nucleotides:
    slidingwindowplotGC(windowsize = 2000, inputseq = seq1)

Q3. Write a function to calculate the AT content of a DNA sequence (ie. the fraction of the nucleotides in the sequence that are As or Ts). What is the AT content of the genome?

	# Here is a function to calculate the AT content of a genome sequence:
    AT <- function(x){ library("seqinr"); 1 - GC(x) }

    # use the function to calculate the AT content of the genome:
    AT(seq1)

    # AT = 1 - GC, ie. (AT + GC = 1):
    GC(seq1)
    AT(seq1) + GC(seq1)

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
    slidingwindowplotAT(windowsize = 2000, inputseq = seq1)
	# This is the mirror image of the plot of GC content (because AT equals 1 minus GC):
    slidingwindowplotGC(windowsize = 2000, inputseq = seq1)

Q5. Is the 3-nucleotide word GAC over-represented or under-represented in the genome sequence?

	# calculate Rho for words of length 3 in the genome
	rho(sequence = seq1, wordsize=3)

    # rho > 1: over-represented
    # rho < 1: under-represented

----------
## assignment 5
**課題No.5 「NCBI accession」**

Please provide the NCBI accessions for the DNA sequences analyzed.

[Example answer]

NC_001477

The NCBI accession for the DNA sequence of "Dengue virus 1, complete genome" is NC_001477 (https://www.ncbi.nlm.nih.gov/nuccore/NC_001477).

----------

## NCBI ASSEMBLY_REPORTS

NCBIのゲノム配列のメタデータが記載されている *assembly_summary* ファイルを用いて、目的のゲノム配列を見つける。  
Genomes Download FAQ
[How can I find the sequence and annotation of my genome of interest?](http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#howtofind)
Using the assembly summary report files

URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> をブラウザ（Firefox または Chrome）で開く。*README_assembly_summary.txt* をクリックする。  
Open the URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> with your browser (Firefox or Chrome). Click the link *README_assembly_summary.txt*.

```
# ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/README_assembly_summary.txt
The assembly_summary files report metadata for the genome assemblies on the NCBI genomes FTP site.
assembly_summary_genbank.txt            - current GenBank genome assemblies
assembly_summary_refseq.txt             - current RefSeq genome assemblies
```

- April 9, 2018 [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
- 2018-10-23 [RefSeq - JI](http://fish-evol.org/RefSeq.html) 井上 潤
- 2017.03.12 [RefSeq | 詳細な注釈づけられている冗長性のない核酸データベース](https://bi.biopapyrus.jp/db/refseq.html)

### [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)
Rの起動

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # assign a character vector of the directory path to the variable
    WorkingDirectory <- "~/projects/data/ncbi/assembly_reports"
    
    # Invoke a System Command
    system( paste0("mkdir -p ",WorkingDirectory) )
    
    # Set and Get Working Directory
    setwd(WorkingDirectory)
    getwd()
    
    # List the Files in a Directory
    list.files()
    dir()

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    ftp_path <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt"
    #ftp_path <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_genbank.txt"
    download.file(url = ftp_path, destfile = basename(ftp_path))

[ファイルからデータを読み込む](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/40.html)

データのインポート。`read.delim()`関数で、タブ区切り(TSV)ファイルを読み込む:  

    # Loading Data into R
    filename <- "assembly_summary_refseq.txt" # 53M
    #filename <- "assembly_summary_genbank.txt" # 150M
    d <- read.delim(file=filename, skip=1, check.names=FALSE, stringsAsFactors=FALSE) 

[R – データフレームの参照・変更](http://taustation.com/r-datafrrame-display-modification/)

    # Exploring and Transforming Dataframes

    # 行数・列数の参照
    # Dimensions of an Object
    dim(d)

    # 先頭と末尾の表示
    # Return the First or Last Part of an Object
    head(d, n = 1)
    tail(d, n = 1)

    # 列名の参照・変更
    # Column Names
    colnames(d)
    colnames(d)[1] <- "assembly_accession"
    
    # クロス集計
    # Cross Tabulation
    table(d$assembly_level)

Genomes Download FAQ
[How can I download RefSeq data for all complete bacterial genomes?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#allcomplete)

#### [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)

例えば、[デング熱](https://ja.wikipedia.org/wiki/デング熱)を引き起こすウイルス "Dengue virus" の完全ゲノム("Complete Genome")配列データの最新版("latest")のURLを抽出する。  
List the ftp_path (column 20) for the assemblies of interest, in this case those that have organism_name of "Dengue virus" (column 8), "latest" version_status (column 11) and "Complete Genome" assembly_level (column 12).

[文字列 | R で文字列の切り出しや置換などの文字列処理を行う方法](https://stats.biopapyrus.jp/r/basic/string.html)

    # grepl returns a logical vector (match or not for each element of x)
    organism_name <- "Dengue virus"
    organism_name <- "Dengue virus|Rabies"
    TF <- grepl(pattern = organism_name, x = d$organism_name, ignore.case = TRUE) & 
     d$version_status == "latest" & grepl(pattern = "Complete Genome", x = d$assembly_level)
    d[TF,]
    d$ftp_path[TF]

抽出されたURLをブラウザFirefox/Chromeで開く。*README.txt*ファイルを右クリックし、「リンクのURLをコピー (Copy Link)」する。  
Open the URL with your browser (Firefox or Chrome). Right click the link *README.txt*, and select "Copy Link Address".

Genomes Download FAQ
[What is the file content within each specific assembly directory?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#files)

```
# ftp://ftp.ncbi.nlm.nih.gov/genomes/all/README.txt
   *_genomic.fna.gz file
       FASTA format of the genomic sequence(s) in the assembly.
```

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    filesuffix <- "_genomic.fna.gz"
    URLs <- sapply(d$ftp_path[TF], function(x) paste0(x, "/", unlist(strsplit(x, split="/"))[10], filesuffix ) )
    download.file(url = URLs, destfile = basename(URLs), method = "libcurl")

#### [Reading sequence data into R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#reading-sequence-data-into-r)

配列データを読み込む:  

    # Reading sequence data and store them in list variable "seqs"
    lf <- basename(URLs)
    seqs <- list()
    library("seqinr") # Load the SeqinR package
    for (i in 1:length(lf)) seqs <- c(seqs, read.fasta(file=lf[i], seqtype="DNA", strip.desc=TRUE) )

配列の数とアノテーションを確認する:  

    length(seqs) # get the number of elements
    getAnnot(seqs) # get sequence annotations

#### [Writing sequence data out as a FASTA file](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#writing-sequence-data-out-as-a-fasta-file)

配列データをFASTA形式ファイルとして書き出す:  

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs, names=getAnnot(seqs), file.out="mySequences.fna", nbchar=80)

    # open current working directory
    system("open .")

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    # quit and restart R
    setwd("~/projects/data/ncbi/assembly_reports") # Set Working Directory
    library(seqinr) # Load the SeqinR package
    seqs <- read.fasta(file="mySequences.fna", seqtype="DNA", strip.desc=TRUE) # Reading sequence data

リスト`seqs`の1番目の要素を変数`seq1`に代入する:  

    # store the first element of the list object `seqs` in a variable `seq1`
    seq1 <- seqs[[1]]

#### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
[Length of a DNA sequence](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#length-of-a-dna-sequence)  
[Base composition of a DNA sequence](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#base-composition-of-a-dna-sequence)  
[GC Content of DNA](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#gc-content-of-dna)  

DNA配列の統計（長さ、塩基組成、GC含量）を計算する:  

    # `summary` function to calculate DNA Sequence Statistics (length, composition, GC)
    summary(seq1)

[DNA words](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-words)

DNA配列の2連続塩基含量（カウント）:  

    # dinucleotide count
    count(seq = seq1, wordsize = 2)

[Over-represented and under-represented DNA words](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#over-represented-and-under-represented-dna-words)

DNA配列の2連続塩基組成（観測値/期待値）:  

    # dinucleotide relative abundance
    rho(seq = seq1, wordsize = 2)

[棒グラフの描画](https://data-science.gr.jp/implementation/ida_r_barplot.html)

    # Creates a bar plot with a straight line
    par(family="mono", cex=0.7) # Set Graphical Parameters
    barplot(sort(rho(seq = seq1, wordsize = 2)))
    abline(h=1) # Add Straight Lines to a Plot

- [53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
関数 par()
- [50. 高水準作図関数](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/50.html)
棒グラフ barplot()
- [51. 低水準作図関数](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/51.html)
直線 abline

[applyファミリー | R で同じ処理を”並列的”に実行する関数](https://stats.biopapyrus.jp/r/basic/apply.html)

    # Apply a Function over a List
    lapply(seqs, summary)
    sapply(seqs, summary)

DNA配列の長さ、GC含量、アノテーションのデータフレームを作成する:  

    # Apply a Function over a List
    Length <- sapply(seqs, length) # Length of a DNA sequence
    GCcontent <- sapply(seqs, GC) # GC Content of DNA
    Annotation <- unlist(getAnnot(seqs)) # sequence annotations

    # data frame
    df <- data.frame(Length, GCcontent, Annotation)
    df

[CSVやTSVを書き出す](http://a-habakiri.hateblo.jp/entry/2016/12/12/222806)

データのエクスポート。タブ区切り(TSV)やカンマ区切り(CSV)ファイルとして出力する:  

    # Exporting Data
    write.table(df, file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names=NA)
    write.csv(df, file="table.csv", quote=TRUE, row.names=TRUE)

    # open current working directory
    system("open .")

複数のDNA配列の2連続塩基組成（観測値/期待値）を解析する:  

    # dinucleotide relative abundance
    myrho <- sapply(seqs, rho, wordsize = 2)

[列名の参照・変更](http://taustation.com/r-datafrrame-display-modification/#i-4)

    # Column Names
    colnames(myrho)

    # e.g. "NC_001477.1 Dengue virus 1, complete genome"
    #colnames(myrho) <- getAnnot(seqs) # get sequence annotations
    
    # e.g. "NC_001477.1 De"
    #colnames(myrho) <- substr(getAnnot(seqs), start=1, stop=14) # Substrings of a Character Vector
    
    # e.g. "NDv1cg"
    #colnames(myrho) <- sapply(getAnnot(seqs),function(x) paste0(substr(x=unlist(strsplit(x,split=" ")),1,1),collapse=""))

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    # Draw a Heat Map
    heatmap(myrho, margins=c(7, 2), cexCol=0.9, scale="none", col=rev(gray.colors(12)))

[Flip color range of heatmap in base R - Stack Overflow](https://stackoverflow.com/questions/56101927/flip-color-range-of-heatmap-in-base-r)

## References

Using oligonucleotide (k-mer) frequency as genomic signature

- ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
- [Suzuki H et al. (2010) "Predicting plasmid promiscuity based on genomic signature."](https://www.ncbi.nlm.nih.gov/pubmed/20851899)
- [Takahashi M et al. (2009) "Estimation of bacterial species phylogeny through oligonucleotide frequency distances."](https://www.ncbi.nlm.nih.gov/pubmed/19442633)
- [Campbell A et al. (1999) "Genome signature comparisons among prokaryote, plasmid, and mitochondrial DNA."](https://www.ncbi.nlm.nih.gov/pubmed/10430917)

----------

## NCBI RefSeq Release

URL <ftp://ftp.ncbi.nlm.nih.gov/refseq/release> をブラウザ（Firefox または Chrome）で開く。*README* をクリックする。  
Open the URL <ftp://ftp.ncbi.nlm.nih.gov/refseq/release> with your browser (Firefox or Chrome). Click the link *README*.

```
# ftp://ftp.ncbi.nlm.nih.gov/refseq/release/README

The NCBI RefSeq project is an ongoing effort to provide a curated, 
non-redundant collection of reference sequences, representative 
of the central dogma, for each major organism.

Sequence data is available in the following directories:

        ftp://ftp.ncbi.nih.gov/refseq/release/archaea/
        ftp://ftp.ncbi.nih.gov/refseq/release/bacteria/
        ftp://ftp.ncbi.nih.gov/refseq/release/complete/
        ftp://ftp.ncbi.nih.gov/refseq/release/fungi/
        ftp://ftp.ncbi.nih.gov/refseq/release/invertebrate/
        ftp://ftp.ncbi.nih.gov/refseq/release/mitochondrion/
        ftp://ftp.ncbi.nih.gov/refseq/release/plant/
        ftp://ftp.ncbi.nih.gov/refseq/release/plasmid/
        ftp://ftp.ncbi.nih.gov/refseq/release/plastid/
        ftp://ftp.ncbi.nih.gov/refseq/release/protozoa/
        ftp://ftp.ncbi.nih.gov/refseq/release/vertebrate_mammalian/
        ftp://ftp.ncbi.nih.gov/refseq/release/vertebrate_other/
        ftp://ftp.ncbi.nih.gov/refseq/release/viral/
```

### [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)
Rの起動

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # Set Working Directory
    WorkingDirectory <- "~/projects/data/ncbi/refseq_release" # assign a value to a variable
    system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
    setwd(WorkingDirectory); getwd() # Set and Get Working Directory
    dir() # List the Files in a Directory

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
     url <- "ftp://ftp.ncbi.nlm.nih.gov/refseq/release/viral/viral.1.1.genomic.fna.gz" # 58.0 kB
    #url <- "ftp://ftp.ncbi.nlm.nih.gov/refseq/release/viral/viral.2.1.genomic.fna.gz" # 62.1 MB
    #url <- "ftp://ftp.ncbi.nlm.nih.gov/refseq/release/viral/viral.3.1.genomic.fna.gz" # 29.1 MB
    #url <- "ftp://ftp.ncbi.nlm.nih.gov/refseq/release/mitochondrion/mitochondrion.2.1.genomic.fna.gz" # 21.9 MB
    filename <- basename(url)
    download.file(url = url, destfile = filename)

    # open current working directory
    system("open .")

#### [Reading sequence data into R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#reading-sequence-data-into-r)

配列データを読み込む:  

    library(seqinr) # Load the SeqinR package
    #filename <- "viral.1.1.genomic.fna.gz"
    #filename <- "viral.2.1.genomic.fna.gz"
    #filename <- "viral.3.1.genomic.fna.gz"
    #filename <- "mitochondrion.2.1.genomic.fna.gz"
    seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE) # Reading sequence data

    length(seqs)# get the number of elements

配列のアノテーションを取得する:  

    # get sequence annotations
    myAnnot <- getAnnot(seqs)
    head(myAnnot)

[Virus](https://github.com/haruosuz/microbe/blob/master/references/microbe.virus.md)
- https://en.wikipedia.org/wiki/Zika_virus
Zika virus is related to the dengue, yellow fever, Japanese encephalitis, and West Nile viruses.
- https://en.wikipedia.org/wiki/Flavivirus
This genus includes the West Nile virus, dengue virus, tick-borne encephalitis virus, yellow fever virus, Zika virus
- https://en.wikipedia.org/wiki/Filoviridae
Two members of the family that are commonly known are Ebola virus and Marburg virus.

[文字列 | R で文字列の切り出しや置換などの文字列処理を行う方法](https://stats.biopapyrus.jp/r/basic/string.html)

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x)
    pattern <- "Ebola|Marburg" # "viral.2.1.genomic.fna.gz"
    #pattern <- "Influenza" # "viral.2.1.genomic.fna.gz"
    #pattern <- "Zika virus|dengue|yellow fever|Japanese encephalitis|West Nile" # "viral.3.1.genomic.fna.gz"
    #pattern <- "Elephas|Loxodonta|Mammuthus" #
    TF <- grepl(pattern = pattern, x = myAnnot, ignore.case = TRUE)
    sum(TF)
    unlist(myAnnot[TF])


#### [Writing sequence data out as a FASTA file](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#writing-sequence-data-out-as-a-fasta-file)

配列データをFASTA形式ファイルとして書き出す:  

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs[TF], names=myAnnot[TF], file.out="mySequences.fna")

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    # quit and restart R
    setwd("~/projects/data/ncbi/refseq_release") # Set Working Directory
    library(seqinr) # Load the SeqinR package
    seqs <- read.fasta(file="mySequences.fna", seqtype="DNA", strip.desc=TRUE) # Reading sequence data

配列の数とアノテーションを確認する:  

    length(seqs) # get the number of elements
    getAnnot(seqs) # get sequence annotations

#### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)

[applyファミリー | R で同じ処理を”並列的”に実行する関数](https://stats.biopapyrus.jp/r/basic/apply.html)

DNA配列の統計（長さ、塩基組成、GC含量）を計算する:  

    # Apply a Function over a List
    # `summary` function to calculate DNA Sequence Statistics (length, composition, GC)
    lapply(seqs, summary)
    sapply(seqs, summary)

#### [Over-represented and under-represented DNA words](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#over-represented-and-under-represented-dna-words)

DNA配列のk連続塩基組成（観測値/期待値）を解析する:  

    # oligonucleotide relative abundance
     k = 2 # 2-mers or dinucleotide
    #k = 3 # 3-mers or trinucleotide
    #k = 4 # 4-mers or tetranucleotide
    #k = 5 # 5-mers or pentanucleotide
    myrho <- sapply(seqs, rho, wordsize = k)

    # Column Names
    colnames(myrho) <- sapply(getAnnot(seqs),function(x) paste0(substr(x=unlist(strsplit(x,split=" ")),1,1),collapse=""))
    colnames(myrho)

    # Set Graphical Parameters
    par(family="mono", cex=0.7)

    # Draw a Heat Map
    heatmap(myrho, margins=c(7, 2), cexCol=0.9, scale="none", col=rev(gray.colors(12)))

    # get sequence annotations
    unlist(getAnnot(seqs))

## References
- オリゴヌクレオチド組成
[Oligonucleotide Composition](https://github.com/haruosuz/mgsa/blob/master/references/mgsa.nucleotide_composition.md#oligonucleotide) | 
[k-mer](https://github.com/haruosuz/mgsa/blob/master/references/mgsa.nucleotide_composition.md#k-mer)

----------
### Elongation Factor
翻訳伸長因子
[EF-Tu](https://ja.wikipedia.org/wiki/EF-Tu)
[EF-G](https://ja.wikipedia.org/wiki/EF-G)

[重複遺伝子EF-Tu/1aとEF-G/2に基づく超生物界の複合系統樹](https://www.brh.co.jp/research/formerlab/miyata/2005/post_000008.html)

----------
## assignment 8
**課題No.8 「dotplot」**

ドットプロットで2つの配列を比較
[Comparing two sequences using a dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)

Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Download FASTA-format files of two protein sequences from UniProt.

    # CySp1 - Cylindrical silk protein 1 - Nephila clavata (Joro spider)
    library("seqinr")
    seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q2V0S3.fasta")[[1]]
    seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q2V0S4.fasta")[[1]]
    length(seq1) # 757
    length(seq2) # 1259

    # setting font in plots
    par(family="mono")

Q2. Create a dotplot for two sequences.

    dotPlot(seq1, seq2, wsize = 3, wstep = 3, nmatch = 3)

Q3. Create a self-similarity dot-plot; i.e. Comparing the sequence against itself.

    dotPlot(seq1, seq1, wsize = 3, wstep = 3, nmatch = 3)
    dotPlot(seq2, seq2, wsize = 3, wstep = 3, nmatch = 3)

![https://moshbox.jp/?p=27311](https://moshbox.jp/be/wp-content/uploads/2017/03/Terminal_Commands-01.png)

    # change shell to bash
    bash

[(Rで)塩基配列解析](http://www.iu.a.u-tokyo.ac.jp/~kadota/r_seq.html)
「2-1. 配列解析基礎」坊農秀雅 (DBCLS)
[講義資料](http://www.iu.a.u-tokyo.ac.jp/~kadota/bioinfo_ngs_sokushu_2014/20140905_2-1_bono.pdf)

	# 配列取得方法
	## togowsの利用 http://togotv.dbcls.jp/20110425.html
    curl -L "http://togows.dbcls.jp/entry/protein/NP_009193.fasta" > HsDJ1.pep.fa
    curl -L "http://togows.dbcls.jp/entry/protein/NP_001232899.fasta" > BmDJ1.pep.fa

	# dottup
	dottup -asequence HsDJ1.pep.fa -bsequence BmDJ1.pep.fa -wordsize 4

	# needle, water
	needle HsDJ1.pep.fa BmDJ1.pep.fa	water HsDJ1.pep.fa BmDJ1.pep.fa

http://kazumaxneo.hatenablog.com/entry/2018/08/24/132149
ラージゲノムにも対応したdot plot解析ツール D-GENIES - macでインフォマティクス

----------
## 2019-11-26

- https://github.com/haruosuz/DS4GD/blob/master/2019giga/README.md#guest-speaker

```
# print working directory
pwd

# make directory
mkdir 1

# change directory
cd 1

# list directory contents
ls
```

- https://www.ncbi.nlm.nih.gov/assembly
Browse by Organism
  - https://www.ncbi.nlm.nih.gov/assembly/organism/
Aspergillus oryzae (ascomycetes)	AoryTK10_1.0
    - https://www.ncbi.nlm.nih.gov/assembly/GCA_009684975.1/
FTP directory for GenBank assembly
      - ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/009/684/975/GCA_009684975.1_AoryTK10_1.0

*GCA_009684975.1_AoryTK10_1.0_genomic.fna.gz*ファイルを右クリックし、「リンクのURLをコピー (Copy Link)」する。  
Right click the link *GCA_009684975.1_AoryTK10_1.0_genomic.fna.gz*, and select "Copy Link Address".

```
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/009/684/975/GCA_009684975.1_AoryTK10_1.0/GCA_009684975.1_AoryTK10_1.0_genomic.fna.gz

# -l     use a long listing format
ls -l

# decompress file
# Redirecting Standard Out to a File
gzip -dc GCA_009684975.1_AoryTK10_1.0_genomic.fna.gz > Ao.fa

# -h, --human-readable	print human readable sizes
ls -lh

# Inspecting Data with Head
head -n 10 Ao.fa

# Creating Simple Programs with Grep and Pipes
grep '>' Ao.fa
grep '>' Ao.fa | wc
```

*a.sh*
```
#!/bin/sh

echo Hello
```

Running scripts
```
chmod 755 a.sh

./a.sh
```

- [Kirr's homepage](http://kirill-kryukov.com/kirr/)
  - http://kirill-kryukov.com/study/naf/
  - http://kirr.dyndns.org/sequence-compression-benchmark/
- https://github.com/KirillKryukov
  - https://github.com/KirillKryukov/naf
Nucleotide Archival Format - Compressed file format for DNA/RNA/protein sequences

```
# https://github.com/KirillKryukov/naf/blob/master/README.md#installing
git clone --recurse-submodules https://github.com/KirillKryukov/naf.git
cd naf && make && make test && make install

# https://github.com/KirillKryukov/naf/blob/master/README.md#compressing
ennaf -h
```

----------
## assignment 9
**課題No.9 「Guest Speaker (1)」**

https://www.ncbi.nlm.nih.gov/assembly/organism/ 
Download the DNA sequence of your genome of interest.
Report your results of analyzing sequence data.

```
mkdir -p ~/projects
cd ~/projects/
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/009/684/975/GCA_009684975.1_AoryTK10_1.0/GCA_009684975.1_AoryTK10_1.0_genomic.fna.gz
gzip -dc GCA_009684975.1_AoryTK10_1.0_genomic.fna.gz > Ao.fa
grep '>' Ao.fa | wc
```

----------
## assignment 10
**課題No.10 「Guest Speaker (2)」**

----------

## [E-utilities](https://github.com/haruosuz/bioinfo/blob/master/references/README.bioinfo.tools.md#e-utilities)
The Entrez Programming Utilities (E-utilities)

### [NCBI Genome List](#ncbi-genome-list)
Searching for sequence data in the NCBI database http://www.ncbi.nlm.nih.gov/genome/browse/
- [Escherichia coli str. K-12 substr. MG1655](https://www.ncbi.nlm.nih.gov/genome/167?genome_assembly_id=161521)
- [Sinorhizobium meliloti 1021](https://www.ncbi.nlm.nih.gov/genome/1004?genome_assembly_id=300472)
- [Mammuthus primigenius (woolly mammoth)](https://www.ncbi.nlm.nih.gov/genome/6934?genome_assembly_id=37154)

### [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)
Rの起動

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # Set Working Directory
    WorkingDirectory <- "~/projects/data/ncbi/eutils" # assign a value to a variable
    system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
    setwd(WorkingDirectory); getwd() # Set and Get Working Directory
    dir() # List the Files in a Directory

複数のDNA配列をNCBIから取得する:  

    # Retrieving a list of DNA sequences from NCBI

    # Load the SeqinR package
    library("seqinr")

    # create a function to retrieve several nucleotide sequences from NCBI
    retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype="DNA", strip.desc=TRUE)[[1]]

    # Make a vector containing NCBI GenBank/RefSeq accessions
    ACCESSIONs <- c("NC_003047", "NC_003037", "NC_003078") # Sinorhizobium meliloti 1021
    ACCESSIONs <- c("NC_001542.1", "NC_001477.1", "NC_002640.1", "NC_001475.2", "NC_001474.2") # "Dengue virus|Rabies"

    # Retrieve the sequences and store them in list variable "seqs"
    seqs <- lapply(ACCESSIONs,  retrieve_ncbi_fna)

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs, names=getAnnot(seqs), file.out="mySequences.fna", nbchar=80)

    # open current working directory
    system("open .")

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    # quit and restart R
    setwd("~/projects/data/ncbi/eutils") # Set Working Directory
    library(seqinr) # Load the SeqinR package
    seqs <- read.fasta(file="mySequences.fna", seqtype="DNA", strip.desc=TRUE) # Reading sequence data

配列の数とアノテーションを確認する:  

    length(seqs) # get the number of elements
    getAnnot(seqs) # get sequence annotations


----------

## [Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#annotation-of-coding-sequences)
[DDBJ タンパク質コード配列; CDS feature について](https://www.ddbj.nig.ac.jp/ddbj/cds.html) |
[DDBJ Protein Coding Sequence; CDS feature](https://www.ddbj.nig.ac.jp/ddbj/cds-e.html)

### [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)
Rの起動

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    # Set Working Directory
    WorkingDirectory <- "~/projects/data/ncbi/eutils" # assign a value to a variable
    system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
    setwd(WorkingDirectory); getwd() # Set and Get Working Directory
    dir() # List the Files in a Directory

- [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2019giga/CaseStudy.md#ncbi-genome-list)
  - [Escherichia coli str. K-12 substr. MG1655](https://www.ncbi.nlm.nih.gov/genome/167?genome_assembly_id=161521)

| Type | RefSeq | INSDC |
|:-----|:-------|:------|
| Chr | NC_000913.3 | U00096.3 |

タンパク質コード配列（CDS）のデータをNCBIから取得する:  
Retrieving Protein Coding Sequence (CDS) data from NCBI:  

    # Retrieving sequence data using SeqinR
    library("seqinr") # Loading seqinr package
    ACCESSION <- "NC_000913" # Escherichia coli str. K-12 substr. MG1655
    seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype="DNA", strip.desc=TRUE)

    # Writing sequence data out as a FASTA file
    write.fasta(sequences=seqs, names=getAnnot(seqs), file.out=paste0(ACCESSION,".ffn"))

    # open current working directory
    system("open .")

    # Reading sequence data into R
    library("seqinr") # Loading seqinr package
    filename <- paste0(ACCESSION,".ffn")
    #filename <- "NC_000913.ffn"
    seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)

配列の数とアノテーションを確認する:  

    # get the number of elements
    length(seqs)

    # get sequence annotations
    # Return the First or Last Part of an Object
    head(getAnnot(seqs), n = 1)
    tail(getAnnot(seqs), n = 3)

[applyファミリー | R で同じ処理を”並列的”に実行する関数](https://stats.biopapyrus.jp/r/basic/apply.html)

DNA配列の長さ、GC含量、アノテーションのデータフレームを作成する:  

    # Apply a Function over a List
    Length <- sapply(seqs, length) # Length of a DNA sequence
    GCcontent <- sapply(seqs, GC) # Global G+C content
    GCpos1 <- sapply(seqs, GCpos, pos=1) # G+C in the first position of the codon bases GC1
    GCpos2 <- sapply(seqs, GCpos, pos=2) # G+C in the second position of the codon bases GC2
    GCpos3 <- sapply(seqs, GCpos, pos=3) # G+C in the third position of the codon bases GC3

    # data frame
    df <- data.frame(Length, GCcontent, GCpos1, GCpos2, GCpos3)
    head(df)

[CSVやTSVを書き出す](http://a-habakiri.hateblo.jp/entry/2016/12/12/222806)

データのエクスポート。タブ区切り(TSV)やカンマ区切り(CSV)ファイルとして出力する:  

    # Exporting Data
    write.table(df, file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names=NA)
    write.csv(df, file="table.csv", quote=TRUE, row.names=TRUE)

    # open current working directory
    system("open .")

- https://github.com/haruosuz/introBI/blob/master/2017/CaseStudy.md#2017-10-05

`summary()`関数でデータフレームの列を要約する。  
CDSの要約統計量（最小値、中央値、最大値など）を求める:  

    # Generic function for Object Summaries
    summary(df)

[R | R を利用した統計解析およびデータの視覚化](https://stats.biopapyrus.jp/r/)

[53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
フォント・ファミリーを指定する

    # setting font in plots
    par(family="mono")

    # Generic function for plotting of R objects
    plot(df)

    # histograms and correlations for a data matrix
    #install.packages("psych")
    library(psych)
    pairs.panels(df)

遺伝暗号 [Genetic code](https://en.wikipedia.org/wiki/Genetic_code) | [Genetic Codes - NCBI](https://www.ncbi.nlm.nih.gov/Taxonomy/Utils/wprintgc.cgi)

    # to plot genetic code as in textbooks
    tablecode()

### codon usage
**[コドン使用](https://github.com/haruosuz/DS4GD/blob/master/2018giga/CaseStudy.md#codon-usage)**

テスト用の配列データを作成する。  
[`count`](https://rdrr.io/rforge/seqinr/man/count.html)関数で3連続塩基`(wordsize = 3)`をカウントする。  
[`uco`](https://rdrr.io/rforge/seqinr/man/uco.html)関数でコドン使用頻度`(index = "eff", "freq", "rscu")`を計算する。

```
# Create tests
testseq <- s2c("ttcttt")

## trimer frequencies
count(seq = testseq, wordsize = 3)

## absolute codon frequencies or codon counts `eff`
uco(seq = testseq, index = "eff")

## relative codon frequencies `freq`
uco(seq = testseq, index = "freq")

## Relative Synonymous Codon Usage `rscu`
uco(seq = testseq, index = "rscu")
```

- [Sharp et al. (2010) "Forces that influence the evolution of codon bias."](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2871821/)
  - [Table 1.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2871821/table/RSTB20090305TB1/?report=objectonly)
Codon usage in E. coli. Codon usage is compared between a set of 40 highly expressed genes (high; see Sharp et al. 2005) and the genome as a whole (all); the data are relative synonymous codon usage values (the ratio of the observed number to that expected if all codons for an amino acid were used equally). Nineteen codons occurring at significantly higher frequencies (see Henry & Sharp 2007) in the high dataset are shown in bold. The data are for E. coli strain K-12 MG1655 (accession number U00096).
- [tRNADB-CE : tRNA gene database curated manually by experts](http://trna.ie.niigata-u.ac.jp/cgi-bin/trnadb/whole_spe_list_inc.cgi?STYPE=B&DTYPE=CMP)
  - Anticodon table [Escherichia coli K-12](http://trna.ie.niigata-u.ac.jp/cgi-bin/trnadb/whole_anticodon.cgi?GID=|U00096&DTYPE=CMP&VTYPE=1)

大腸菌ゲノムにおける全遺伝子群と高発現遺伝子群のコドン使用頻度を計算する。

- [リストをベクトルに変換するunlist()関数](https://ito-hi.blog.so-net.ne.jp/2011-07-12)

`unlist()`関数は、リストの要素を端からベクトルとして結合して 1 つのベクトルとしてまとめる。
CDSの結合(concatenate)データのコドン使用頻度`("eff", "freq", "rscu")`を計算し、カンマ区切りファイルとして出力する:  
```
# Compute codon usage for a set of highly expressed genes (high) and the genome as a whole (all), 
# and export data as a CSV file to be read by spreadsheets:

# 全遺伝子群(all)のコドン使用頻度
# Codon usage for the collection of all genes
df.uco.all <- uco(unlist(seqs), as.data.frame=TRUE)
write.csv(df.uco.all[order(df.uco.all$AA),], file="table.uco.all.csv", quote=TRUE, row.names=FALSE)

# 高発現遺伝子群(high)のコドン使用頻度
# Codon usage for the collection of highly expressed genes encoding ribosomal proteins
pattern <- "ribosomal subunit protein"
TF <- grepl(pattern = pattern, x = getAnnot(seqs), ignore.case = TRUE)
sum(TF) # unlist(getAnnot(seqs[TF]))
df.uco.high <- uco(unlist(seqs[TF]), as.data.frame=TRUE)
write.csv(df.uco.high[order(df.uco.high$AA),], file="table.uco.high.csv", quote=TRUE, row.names=FALSE)

# open current working directory
system("open .")
```


[`getTrans`](https://www.rdocumentation.org/packages/seqinr/versions/3.4-5/topics/getTrans)
関数を用いて、核酸配列をタンパク質に翻訳する:  

    # Translate nucleic acid sequences into proteins
    myTrans <- getTrans(ffn)
    myTrans[[1]]

----------

### amino acid usage
**[アミノ酸](https://ja.wikipedia.org/wiki/アミノ酸)使用**

平成22年度、清水謙多郎 [タンパク質の配列から機能を予測する](http://www.iu.a.u-tokyo.ac.jp/lectures/AG01/100511/motif.html)

`[[ ]]`はリスト内の要素（ベクトル）を取り出す。
リストの1番目の要素を取り出す:  

    # extract the 1st element:
    faa1 <- faa[[1]]

`summary()`関数でデータの要約:  

    # Object Summaries
    summary(faa1)

配列の長さ(length)、アミノ酸組成(composition)、物理化学的クラスの割合(AA.Property)が出力される。

![http://www.r-exercises.com/2017/05/10/accessing-and-manipulating-biological-databases-solutions-part-3/](http://www.r-exercises.com/wp-content/uploads/2017/05/Fig3-300x300.png)

[`AAstat()`](https://www.rdocumentation.org/packages/seqinr/versions/3.3-3/topics/AAstat)
関数を用いて、タンパク質の配列情報（アミノ酸残基数、物理化学的クラスの割合、[等電点](https://ja.wikipedia.org/wiki/等電点)の理論値）を求める:  

    # Get protein statistics
    AAstat(seq=faa1)

    aa <- AAstat(seq=faa1, plot=FALSE)

    # Get amino acid counts
    aa$Compo

    # Get the percentage of each physico-chemical classes
    aa$Prop
    aa$Prop$Aromatic

[`getAnnot`](https://rdrr.io/rforge/seqinr/man/getAnnot.html)
関数を用いて、配列のアノテーションを取得する:  

    # get sequence annotations
    myAnnot <- getAnnot(faa)

[文字列 | R で文字列の切り出しや置換などの文字列処理を行う方法](https://stats.biopapyrus.jp/r/basic/string.html)

[転移酵素](https://ja.wikipedia.org/wiki/転移酵素) "transferase" と、機能が不明なタンパク質 "hypothetical protein" を抽出する:  

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x)
    pattern <- "transferase|hypothetical.protein"
    TF <- grepl(pattern = pattern, x = myAnnot, ignore.case = TRUE)
    #TF <- !grepl(pattern = "hypothetical.protein", x = myAnnot, ignore.case = TRUE)
    sum(TF)
    myAnnot[TF]

[リスト](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html)の成分を取り出す:  

    # extract the elements of the list object
    faa[TF]

`sapply()`関数は、リストの各要素に関数を適用する。  
複数タンパク質配列のアミノ酸使用の絶対度数と相対度数を求める:  

    # absolute frequencies
    X <- sapply(faa[TF], function(x) AAstat(x, plot=FALSE)$Compo )
    write.csv(t(X), file="table.aa_af.csv")

    # relative frequencies
    X <- sapply(faa[TF], function(x) summary(x)$composition )
    write.csv(t(X), file="table.aa_rf.csv")

    # open current working directory
    system("open .")

[26. names 属性と要素のラベル](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/26.html)

    # Exploring and Transforming Dataframes
    dim(X)
    colnames(X) <- sub(pattern=".+protein=(.+)\\] \\[(protein_id|pseudo)=.+", replacement="\\1", getAnnot(faa[TF]))

クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)

    # Hierarchical cluster analysis
    plot(hclust(dist(t(X))), hang=-1)

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    # Draw a Heat Map
    heatmap(X, margins=c(14, 2), cexCol=0.9, scale="none", col=rev(gray.colors(12)))

----------
## assignment 11
**課題No.11 「Pairwise Sequence Alignment」**

[Exercises on Sequence Alignment](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Download FASTA-format files of two protein sequences of interest from UniProt.

    library("seqinr")
    seq1 <- read.fasta(file = "http://togows.dbcls.jp/entry/protein/NP_009193.fasta")[[1]]
    seq2 <- read.fasta(file = "http://togows.dbcls.jp/entry/protein/NP_001232899.fasta")[[1]]

    seq1string <- toupper(c2s(seq1))	# convert the sequence to a string and to uppercase
    seq2string <- toupper(c2s(seq2))	# convert the sequence to a string and to uppercase

Q2. What is the alignment score for the optimal global alignment between the two proteins, when you use the BLOSUM50 scoring matrix?
(set gapOpening = -9.5 and gapExtension = -0.5)

	library("Biostrings")		# load the Biostrings package
	data(BLOSUM50)			# load the BLOSUM50 scoring matrix
    myglobalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
	gapOpening = -9.5, gapExtension = -0.5)	# align the two sequences
	myglobalAlign

Q3. Use the writePairwiseAlignments() function to view the optimal global alignment.

    writePairwiseAlignments(myglobalAlign)

Q4. What global alignment score do you get for the two proteins, when you use the BLOSUM62 alignment matrix?

	data(BLOSUM62)			# load the BLOSUM62 scoring matrix
    myglobalAlign2 <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM62",
	gapOpening = -9.5, gapExtension = -0.5)	# align the two sequences
	myglobalAlign2

Q5. What is the alignment score for the optimal local alignment between the two proteins?

    mylocalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
	gapOpening = -9.5, gapExtension = -0.5, type="local")
	mylocalAlign

----------
## assignment-12
**課題No.12 「draft report」**

Integrate and edit your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it in PDF format.

これまでの課題（興味あるDNA/タンパク質の配列解析の結果）を統合・編集してレポートのドラフトを作成し、PDFファイルで提出する。

----------
## assignment-13
**課題No.13 「presentation slides」**

https://github.com/haruosuz/DS4GD/tree/master/2018giga#final-presentation

2019-07-16 最終発表のスライド <YOUR_NAME.pdf> を提出する。
発表時間：1人あたり最大5分

生物学的データ（ゲノムDNA配列やタンパク質配列）の解析結果を報告する。解析の例として、DNA配列の統計（長さ、GC含量、連続塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル/ローカル・アラインメント）、Pythonによる配列解析などが含まれる。

Submit your PDF presentation slides for your final presentation 最終発表 Tuesday 2019-07-16.
Five minutes will be allocated for each presentation, including presentation and discussion.

Report your main findings on analyses of biological data (e.g. genome DNA sequences and protein sequences) you're interested in. The analyses can include DNA sequence statistics (length, GC Content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global/local alignment), sequence analysis with Python, etc.

----------
