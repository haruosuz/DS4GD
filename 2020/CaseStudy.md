**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2020)**  
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
- [assignment 5](#assignment-5) 課題No.5 「Guest Speaker (1)」
- [assignment 5](#assignment-5) 課題No.6 「Guest Speaker (2)」
- [assignment 5](#assignment-5) 課題No.7 「Guest Speaker (3)」
- [assignment 8](#assignment-8) 課題No.8 「dotplot」
- [assignment 9](#assignment-9) 課題No.9 「」
- [assignment 10](#assignment-10) 課題No.10 「」
- 
- [assignment 11](#assignment-11) 課題No.11 「Pairwise Sequence Alignment」
- [Installing R packages](#installing-r-packages)
- [assignment 12](#assignment-12) 課題No.12 「Multiple Alignment and Phylogenetic Trees」
- [assignment 13](#assignment-13) 課題No.13 「draft report」
- [assignment 14](#assignment-14) 課題No.14 「presentation slides」
- [E-utilities](#e-utilities)
  - [fna](#fna)
  - [faa](#faa)
- [Coding sequences](#coding-sequences) タンパク質コード配列
  - [codon usage](#codon-usage) コドン使用
  - [amino acid usage](#amino-acid-usage) アミノ酸使用

----------
## assignment 0
**選抜課題**

【ASSIGNMENT】
Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

【課題内容】
本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

----------
## assignment 1
**課題No.1 「Introduction to R」**

Watch the following videos and write your comments or questions.
- [Introduction to R](https://www.youtube.com/watch?v=WiO44CiSPF0&list=PL8eNk_zTBST_KL2gnciUv1oor0ECw8Hqg)

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

> R.version.string
[1] "R version 3.6.1 (2019-07-05)"

> packageVersion("seqinr")
[1] ‘3.6.1’

> packageVersion("Biostrings")
[1] ‘2.52.0’
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

https://github.com/haruosuz/bioinfo/blob/master/references/README.bioinfo.tools.md#dotplot

----------


----------
## assignment 11
**課題No.11 「Pairwise Sequence Alignment」**

[Exercises on Sequence Alignment](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Download FASTA-format files of two protein sequences of interest from UniProt.

    library("seqinr")
    seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q9CD83.fasta")[[1]]
    seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/A0PQ23.fasta")[[1]]
    seq1string <- toupper(c2s(seq1)) # convert the sequence to a string and to uppercase
    seq2string <- toupper(c2s(seq2)) # convert the sequence to a string and to uppercase

Q2. What is the alignment score for the optimal global alignment between the two proteins, when you use the BLOSUM50 scoring matrix?
(set gapOpening = -9.5 and gapExtension = -0.5)

	library("Biostrings") # load the Biostrings package
	data(BLOSUM50) # load the BLOSUM50 scoring matrix
    myglobalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
                      gapOpening = -9.5, gapExtension = -0.5) # align the two sequences
	myglobalAlign

Q3. Use the writePairwiseAlignments() function to view the optimal global alignment.

    writePairwiseAlignments(myglobalAlign)

Q4. What global alignment score do you get for the two proteins, when you use the BLOSUM62 alignment matrix?

	data(BLOSUM62) # load the BLOSUM62 scoring matrix
    myglobalAlign2 <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM62",
                       gapOpening = -9.5, gapExtension = -0.5) # align the two sequences
	myglobalAlign2

Q5. What is the alignment score for the optimal local alignment between the two proteins?

    mylocalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
                     gapOpening = -9.5, gapExtension = -0.5, type="local")
	mylocalAlign

----------
## Installing R packages

多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)

Rパッケージ
[`msa`](https://bioconductor.org/packages/release/bioc/html/msa.html),
[`ape`](http://ape-package.ird.fr/ape_installation.html)
のインストール:  
```
# Install the "msa" package:
if (!requireNamespace("BiocManager", quietly = TRUE))
     install.packages("BiocManager")

BiocManager::install("msa")

# Install the "ape" package:
install.packages("ape")
```

Rパッケージのバージョン出力:  
```
# Print the versions of these packages:
packageVersion("msa")
packageVersion("ape")
```

Rパッケージの呼び出し:  
```
# Load the packages into R:
library("msa")
library("ape")
```

----------
## assignment 12
**課題No.12 「Multiple Alignment and Phylogenetic Trees」**

- [Exercises on Multiple Alignment and Phylogenetic Trees](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter5.html#exercises)
  - [Answers to the exercises on Multiple Alignment and Phylogenetic Trees](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#multiple-alignment-and-phylogenetic-trees)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Calculate the genetic distances between >3 protein sequences of interest. Which are the most closely related proteins, based on the genetic distances?
```
seqnames <- c("Q9YRR4", "Q9YP96", "B0LSS3", "Q6TFL5", "Q32ZE1") # Make a vector containing the names of the sequences
# retrieve several sequences from UniProt
library("seqinr") # Load the SeqinR package
retrieve_seqs_uniprot <- function(ACCESSION) read.fasta(file=paste0("http://www.uniprot.org/uniprot/",ACCESSION,".fasta"), seqtype="AA", strip.desc=TRUE)[[1]]
seqs <- lapply(seqnames,  retrieve_seqs_uniprot) # Retrieve the sequences and store them in list variable "seqs"

# write out the sequences to a FASTA file
write.fasta(seqs, seqnames, file="myseq.fasta")

# Read an XStringSet object from a file
library(Biostrings)
mySequences <- readAAStringSet(file = "myseq.fasta")

# Multiple Sequence Alignment using ClustalW
library(msa)
myAlignment <- msa(mySequences, "ClustalW")

# write an XStringSet object to a file
writeXStringSet(unmasked(myAlignment), file = "myaln.fasta")

# read the FASTA-format alignment into R
myaln <- read.alignment(file = "myaln.fasta", format = "fasta")

# calculate the genetic distances between the protein sequences
mydist <- dist.alignment(myaln)
mydist

# get sequence annotations
unlist(getAnnot(seqs))
```

Q2. Build an unrooted phylogenetic tree of the proteins, using the neighbour-joining algorithm. Which are the most closely related proteins, based on the tree?
```
# setting font in plots
par(family="mono")

# construct a phylogenetic tree with the neighbor joining algorithm
library(ape)
mytree <- nj(mydist)
plot.phylo(mytree, type="unrooted")
```

Q3. Build a rooted phylogenetic tree of the proteins, using an outgroup. Which are the most closely related proteins, based on the tree? What extra information does this tree tell you, compared to the unrooted tree in Q2?
```
mytree <- root(mytree, outgroup = "Q32ZE1", resolve.root = TRUE)
plot.phylo(mytree, main = "Phylogenetic Tree")
```

----------
## assignment 13
**課題No.13 「draft report」**

Integrate and edit your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it in PDF format.

これまでの課題（興味あるDNA/タンパク質の配列解析の結果）を統合・編集してレポートのドラフトを作成し、PDFファイルで提出する。

----------
## assignment 14
**課題No.14 「presentation slides」**

Submit your presentation slides for your final presentation Tuesday 2020-01-14.  
**Ten** minutes will be allocated for each presentation, including presentation and discussion.

Report your main findings on analyses of biological data (e.g. DNA and protein sequences) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global sequence alignment, and local sequence alignment), multiple sequence alignment, and phylogenetic trees, etc.

2020-01-14 最終発表のスライドを提出する。  
発表時間：1人あたり最大**10**分

生物学的データ（ゲノムDNA配列やタンパク質配列）の解析結果を報告する。解析の例として、DNA配列の統計（長さ、GC含量、連続塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル配列アライメント、ローカル配列アライメント）、多重配列アライメント、系統樹などが含まれる。

----------

## [E-utilities](https://github.com/haruosuz/bioinfo/blob/master/references/README.bioinfo.tools.md#e-utilities)
The Entrez Programming Utilities (E-utilities)

- prokka [Output Files](https://github.com/tseemann/prokka/blob/master/README.md#output-files)

| Extension | Description |
| --------- | ----------- |
| .fna | Nucleotide FASTA file of the input contig sequences. |
| .ffn | Nucleotide FASTA file of all the prediction transcripts (CDS, rRNA, tRNA, tmRNA, misc_RNA) |
| .faa | Protein FASTA file of the translated CDS sequences. |

- data
  - [Yanagiya et al. (2018) Front Microbiol. 9:2602. "Novel Self-Transmissible and Broad-Host-Range Plasmids Exogenously Captured From Anaerobic Granules or Cow Manure."](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6232296/)
  - https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/ebolavirus
  - https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/Zika%20virus
  - https://www.ncbi.nlm.nih.gov/genome/browse/#!/organelles/Mammuthus

### [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)
Rの起動

配列データをNCBIから取得する:  
Retrieving sequence data from NCBI:  
```
# Set Working Directory
WorkingDirectory <- "~/projects/data/ncbi/eutils" # assign a value to a variable
system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
setwd(WorkingDirectory); getwd() # Set and Get Working Directory

library("seqinr") # Loading seqinr package

# Accession Numbers of Sequence Data
ACCESSION <- "AP018710" # https://www.ncbi.nlm.nih.gov/nuccore/AP018710 plasmid pSN1216-29
#ACCESSION <- "NC_002549" # https://www.ncbi.nlm.nih.gov/nuccore/NC_002549 Zaire ebolavirus
#ACCESSION <- "NC_007596" # https://www.ncbi.nlm.nih.gov/nuccore/NC_007596 Mammuthus primigenius mitochondrion 
#ACCESSION <- "NC_015529" # https://www.ncbi.nlm.nih.gov/nuccore/NC_015529 Mammuthus columbi mitochondrion 

## nucleotide FASTA
fna.seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype="DNA", strip.desc=TRUE)

## CDS nucleotide FASTA
ffn.seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype="DNA", strip.desc=TRUE)

## CDS protein FASTA
faa.seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_aa&retmode=text"), seqtype="AA", strip.desc=TRUE)

# 配列の数をカウントする:  
# get the number of elements
length(fna.seqs)
length(ffn.seqs)
length(faa.seqs)

# 配列データをFASTA形式ファイルとして書き出す:  
# Writing sequence data out as a FASTA file
write.fasta(sequences=fna.seqs, names=getAnnot(fna.seqs), file.out=paste0(ACCESSION,".fna"))
write.fasta(sequences=ffn.seqs, names=getAnnot(ffn.seqs), file.out=paste0(ACCESSION,".ffn"))
write.fasta(sequences=faa.seqs, names=getAnnot(faa.seqs), file.out=paste0(ACCESSION,".faa"))

dir() # List the Files in a Directory
system("open .") # open current working directory
```

### fna
複数の.fnaファイルをNCBIから取得する:  
Retrieving .fna files from NCBI:  
```
setwd("~/projects/data/ncbi/eutils") # Set Working Directory
library(seqinr) # Load the SeqinR package

# Make a vector containing NCBI accessions
ACCESSIONs <- c("KM670336", "AP018710", "NZ_CP014764", "NZ_CP015073", "NZ_CP020602")

# create a function to retrieve several nucleotide sequences from NCBI
retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype="DNA", strip.desc=TRUE)[[1]]

# Retrieve the sequences and store them in list variable "seqs"
fna.seqs <- lapply(ACCESSIONs, retrieve_ncbi_fna)

# write the sequences to a FASTA-format file
write.fasta(sequences=fna.seqs, names=getAnnot(fna.seqs), file.out="mySequences.fna")

# Reading sequence data
seqs <- read.fasta(file="mySequences.fna", seqtype="DNA", strip.desc=TRUE)

# 配列の数とアノテーションを確認する:  
length(seqs) # get the number of elements
getAnnot(seqs) # get sequence annotations

# Apply a Function over a List
lapply(seqs, summary)
sapply(seqs, summary)

# for文でループ処理を行う。複数のヒートマップをファイル出力する:
# for loop to carry out the same command several times
pdf("Rplot_heatmap_rho.pdf") # create a PDF device called "Rplot_heatmap_rho.pdf"
par(family="mono", cex=0.9) # Set Graphical Parameters
for(k in 2:4){
  myrho <- sapply(seqs, rho, wordsize = k)
  heatmap(myrho, margins=c(7, 2), cexRow=1/k, cexCol=0.7, scale="none", col=rev(gray.colors(12)))
}
dev.off(which = dev.cur()) # close the device
```

### faa
複数の.faaファイルをNCBIから取得する:  
Retrieving .faa files from NCBI:  
```
setwd("~/projects/data/ncbi/eutils") # Set Working Directory
library(seqinr) # Load the SeqinR package

# Make a vector containing NCBI accessions
ACCESSIONs <- c("KM670336", "AP018710", "NZ_CP014764", "NZ_CP015073", "NZ_CP020602")

# create a function to retrieve several sequences from NCBI
retrieve_ncbi_faa <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_aa&retmode=text"), seqtype="AA", strip.desc=TRUE)

# Retrieve the sequences and store them in list variable "seqs"
#faa.seqs <- lapply(ACCESSIONs, retrieve_ncbi_faa)
faa.seqs <- list()
for(ACCESSION in ACCESSIONs) faa.seqs <- c(faa.seqs, retrieve_ncbi_faa(ACCESSION) )

# Inspecting data
length(faa.seqs) # get the number of elements
myAnnot <- unlist(getAnnot(faa.seqs)) # sequence annotations

# grepl returns a logical vector (match or not for each element of x)
pattern <- "gene=repA]|protein=replication initiator protein A]"
TF <- grepl(pattern = pattern, x = myAnnot, ignore.case = TRUE)
sum(TF)
myAnnot[TF]
sapply(faa.seqs[TF], length)

# sub and gsub perform replacement of the first and all matches respectively.
Annotation <- sub(pattern=".+\\|(\\S+) .+", replacement="\\1", myAnnot[TF])

# write out the sequences to a FASTA file
write.fasta(faa.seqs[TF], Annotation, file="myseq.faa")

# Reading sequence data
seqs <- read.fasta(file="myseq.faa", seqtype="AA", strip.desc=TRUE)

# setting font in plots
par(family="mono")

# ドットプロットで2つの配列を比較:
# Comparing two sequences using a dotplot
s1 <- seqs[[1]]
s2 <- seqs[[2]]
dotPlot(s1, s2)
nmbr <- 3; dotPlot(s1, s2, wsize = nmbr, wstep = nmbr, nmatch = nmbr, xlab = getName(s1), ylab = getName(s2))

# for文でループ処理を行う。複数のドットプロットをファイル出力する:
# for loop to carry out the same command several times
pdf("Rplot_dotPlot.pdf") # create a PDF device called "Rplot_dotPlot.pdf"
par(mfrow=c(2,2))
for (n1 in 1:length(seqs)) {
  for (n2 in n1:length(seqs)) {
    s1 <- seqs[[n1]]
    s2 <- seqs[[n2]]
    dotPlot(s1, s2, xlab=getName(s1), ylab=getName(s2))
  }
}
dev.off(which = dev.cur()) # close the device

# open current working directory
system("open .")
```

[Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)  
多重配列アライメントと系統樹
```
# Read an XStringSet object from a file
library(Biostrings)
mySequences <- readAAStringSet(file = "myseq.faa")

# Multiple Sequence Alignment using ClustalW
library(msa)
myAlignment <- msa(mySequences, "ClustalW")

# write an XStringSet object to a file
writeXStringSet(unmasked(myAlignment), file = "myaln.fasta")

# read the FASTA-format alignment into R
myaln <- read.alignment(file = "myaln.fasta", format = "fasta")

# calculate the genetic distances between the protein sequences
mydist <- dist.alignment(myaln)
mydist

# setting font in plots
par(family="mono")

# 無根系統樹の構築
# Building an unrooted tree
# construct a phylogenetic tree with the neighbor joining algorithm
library(ape) # install.packages("ape")
mytree <- nj(mydist)
plot.phylo(mytree, type = "unrooted")

# 有根系統樹の構築
# Building a rooted phylogenetic tree
library(phangorn) # install.packages("phangorn")
mytree <- midpoint(mytree) # midpoint rooting
plot.phylo(ladderize(mytree, right = FALSE), main = "Neighbor-Joining midpoint rooted tree", cex=0.9)

# Newick形式ファイルとして保存する
# Saving a tree as a Newick-format tree file
write.tree(mytree, file="mytree.newick")

# open current working directory
system("open .")
```

----------


## [Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#annotation-of-coding-sequences)
[DDBJ タンパク質コード配列; CDS feature について](https://www.ddbj.nig.ac.jp/ddbj/cds.html) |
[DDBJ Protein Coding Sequence; CDS feature](https://www.ddbj.nig.ac.jp/ddbj/cds-e.html)

### [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)
Rの起動

タンパク質コード配列（CDS）のデータをNCBIから取得する:  
Retrieving Protein Coding Sequence (CDS) data from NCBI:  
```
# Set Working Directory
WorkingDirectory <- "~/projects/data/ncbi/eutils" # assign a value to a variable
system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
setwd(WorkingDirectory); getwd() # Set and Get Working Directory

library("seqinr") # Loading seqinr package

# Accession Numbers of Sequence Data
ACCESSION <- "AP018710" # https://www.ncbi.nlm.nih.gov/nuccore/AP018710 plasmid pSN1216-29

## CDS nucleotide FASTA
ffn.seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype="DNA", strip.desc=TRUE)

# get the number of elements
length(ffn.seqs)

# Writing sequence data out as a FASTA file
write.fasta(sequences=ffn.seqs, names=getAnnot(ffn.seqs), file.out=paste0(ACCESSION,".ffn"))
```

[applyファミリー | R で同じ処理を”並列的”に実行する関数](https://stats.biopapyrus.jp/r/basic/apply.html)

DNA配列の長さ、GC含量、アノテーションのデータフレームを作成する:  

```
# Apply a Function over a List
Length <- sapply(ffn.seqs, length) # Length of a DNA sequence
GCcontent <- sapply(ffn.seqs, GC) # Global G+C content
GCpos1 <- sapply(ffn.seqs, GCpos, pos=1) # G+C in the 1st position of the codon bases
GCpos2 <- sapply(ffn.seqs, GCpos, pos=2) # G+C in the 2nd position of the codon bases
GCpos3 <- sapply(ffn.seqs, GCpos, pos=3) # G+C in the 3rd position of the codon bases

# data frame
df <- data.frame(Length, GCcontent, GCpos1, GCpos2, GCpos3)
head(df)
```

`summary()`関数でデータフレームの列を要約する。  
CDSの要約統計量（最小値、中央値、最大値など）を求める:  

    # Generic function for Object Summaries
    summary(df)

    # setting font in plots
    par(family="mono")

    # Generic function for plotting of R objects
    plot(df)

    # histograms and correlations for a data matrix
    #install.packages("psych")
    library(psych)
    pairs.panels(df)

- [Since bacterial genomes have little non-coding DNA, and the first two positions within codons are constrained by protein-coding requirements, most of the variation is due to the third position of codons [(8) and Figure 2].](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC549432/)
- [コドン選択は主としてコドンの3文字目の選択に対応しています。ロイシン(Leu)とアルギニン(Arg)とセリン(Ser)については1文字目にも選択の余地がありますが、コドン2文字目の変化は必ずアミノ酸の変化をもたらします。従って、ゲノムのG+C%は、コドン1･2文字目に比べて、3文字目で最も顕著に観察されています。](https://www.nig.ac.jp/museum/evolution/04_c.html)
- [これまでに、コドン1文字目のG+C含量（GC1）やコドン2文字目のG+C含量（GC2）と比較して、コドン3文字目のG+C含量（GC3）は、コドンバイアスに及ぼす寄与が最も大きいことが報告されている。](http://www.iab.keio.ac.jp/research/highlight/papers/200904131400.html)

```
df$Annotation <- unlist(getAnnot(ffn.seqs)) # get sequence annotations
df$location <- sub(pattern=".+\\[location=(.+)\\] \\[gbkey=.+", replacement="\\1", df$Annotation)
df$protein <- sub(pattern=".+\\[protein=(.+)\\] \\[protein_id=.+", replacement="\\1", df$Annotation)
rownames(df) <- NULL

# Return the First or Last Part of an Object
head(df, n = 1)
tail(df, n = 2)

# Exporting Data
write.table(df, file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names=NA)
write.csv(df, file="table.csv", quote=TRUE, row.names=TRUE)

# open current working directory
system("open .")
```

遺伝暗号 [Genetic code](https://en.wikipedia.org/wiki/Genetic_code) | [Genetic Codes - NCBI](https://www.ncbi.nlm.nih.gov/Taxonomy/Utils/wprintgc.cgi)

    library("seqinr") # Loading seqinr package
    tablecode() # to plot genetic code as in textbooks

----------

### codon usage
**コドン使用**

- [Sharp et al. (2010) "Forces that influence the evolution of codon bias."](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2871821/)
  - [Table 1.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2871821/table/RSTB20090305TB1/?report=objectonly)
Codon usage in E. coli. Codon usage is compared between a set of 40 highly expressed genes (high; see Sharp et al. 2005) and the genome as a whole (all); the data are relative synonymous codon usage values (the ratio of the observed number to that expected if all codons for an amino acid were used equally). Nineteen codons occurring at significantly higher frequencies (see Henry & Sharp 2007) in the high dataset are shown in bold. The data are for E. coli strain K-12 MG1655 (accession number U00096).
- [tRNADB-CE : tRNA gene database curated manually by experts](http://trna.ie.niigata-u.ac.jp/cgi-bin/trnadb/whole_spe_list_inc.cgi?STYPE=B&DTYPE=CMP)
  - Anticodon table [Escherichia coli K-12](http://trna.ie.niigata-u.ac.jp/cgi-bin/trnadb/whole_anticodon.cgi?GID=|U00096&DTYPE=CMP&VTYPE=1)

大腸菌ゲノムにおける全遺伝子群と高発現遺伝子群のコドン使用頻度を計算する。

- [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2019giga/CaseStudy.md#ncbi-genome-list)
  - [Escherichia coli str. K-12 substr. MG1655](https://www.ncbi.nlm.nih.gov/genome/167?genome_assembly_id=161521)

| Type | RefSeq | INSDC |
|:-----|:-------|:------|
| Chr | NC_000913.3 | U00096.3 |

配列データをNCBIから取得する:  
Retrieving sequence data from NCBI:  
```
library("seqinr") # Loading seqinr package

# Accession Numbers of Sequence Data
ACCESSION <- "NC_000913" # Escherichia coli str. K-12 substr. MG1655

## CDS nucleotide FASTA
ffn.seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype="DNA", strip.desc=TRUE)

# get the number of elements
length(ffn.seqs)
```

- [リストをベクトルに変換するunlist()関数](https://ito-hi.blog.so-net.ne.jp/2011-07-12)

`unlist()`関数は、リストの要素を端からベクトルとして結合して 1 つのベクトルとしてまとめる。
CDSの結合(concatenate)データのコドン使用頻度`("eff", "freq", "rscu")`を計算し、カンマ区切りファイルとして出力する:  
```
# Compute codon usage for a set of highly expressed genes (high) and the genome as a whole (all), 
# and export data as a CSV file to be read by spreadsheets:

# 全遺伝子群(all)のコドン使用頻度
# Codon usage for the collection of all genes
df.uco.all <- uco(unlist(ffn.seqs), as.data.frame=TRUE)
write.csv(df.uco.all[order(df.uco.all$AA),], file="table.uco.all.csv", quote=TRUE, row.names=FALSE)

# 高発現遺伝子群(high)のコドン使用頻度
# Codon usage for the collection of highly expressed genes encoding ribosomal proteins
pattern <- "ribosomal subunit protein"
TF <- grepl(pattern = pattern, x = getAnnot(ffn.seqs), ignore.case = TRUE)
sum(TF) # unlist(getAnnot(ffn.seqs[TF]))
df.uco.high <- uco(unlist(ffn.seqs[TF]), as.data.frame=TRUE)
write.csv(df.uco.high[order(df.uco.high$AA),], file="table.uco.high.csv", quote=TRUE, row.names=FALSE)

# open current working directory
system("open .")
```

[`getTrans`](https://www.rdocumentation.org/packages/seqinr/versions/3.4-5/topics/getTrans)
関数を用いて、核酸配列をタンパク質に翻訳する:  

    # Translate nucleic acid sequences into proteins
    myTrans <- getTrans(ffn.seqs)
    myTrans[[1]]

----------

### amino acid usage

https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#amino-acid-usage

----------
