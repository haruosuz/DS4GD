**[DATA SCIENCE FOR GENOME DYNAMICS (GIGA)](https://github.com/haruosuz/DS4GD/tree/master/2020giga)**  
[SFC Online Learning System (SOL)](https://sol.sfc.keio.ac.jp/)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- assignment 1 課題1 class cancelled
- [assignment 2](#assignment-2) 課題2 「Introduction to R」
- [assignment 3](#assignment-3) 課題3 「Installing R packages」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 4](#assignment-4) 課題4 「DNA Sequence Statistics (1)」
- [assignment 5](#assignment-5) 課題5 「DNA Sequence Statistics (2)」
- [assignment 6](#assignment-6) 課題6 「dotplot」
- [assignment 7](#assignment-7) 課題7 「Pairwise Sequence Alignment」
- [assignment 8](#assignment-8) 課題8 「Multiple Alignment and Phylogenetic trees」
- [2020-12-08](#2020-12-08)
- [assignment 9](#assignment-9) 課題9 「draft report」
- [assignment 10](#assignment-10) 課題10 「final report」

----------
## assignment 0
**選抜課題**

【ASSIGNMENT】
Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

【課題内容】
本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

----------
## assignment 2
**課題2 「Introduction to R」**

Watch the following videos and write your comments or questions.
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

以下の動画を見て、疑問点を報告する。
- [Rプログラミングと統計](https://www.youtube.com/watch?v=jjkBsU4AChM&list=PLdNQOrt5fdN8P-vy1i6vep9OP4R1AZcEb)


[回答例]
```
「Rプログラミングと統計 p.3 ~ p.10 を見た。
疑問点は次の通りである。
1. 行列とデータフレームとリストの違いは？
2. NAとNaNの違いが理解できなかった。
```

[Download R scripts](https://github.com/haruosuz/r4bioinfo/raw/master/scripts/my_basic_r.zip)

----------
### R_factor

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_factor

----------
### R_object

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_object

----------
### R_vector

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_vector

----------
## assignment 3
**課題3 「Installing R packages」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

Please download the R script (*my_setup_packages.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

回答例:  
```
# Example answer:  

> # Print the versions of these packages:
> packageVersion("seqinr")
[1] ‘3.6.1’
> packageVersion("zoo")
[1] ‘1.8.7’
> packageVersion("ape")
[1] ‘5.3’
> packageVersion("phangorn")
[1] ‘2.5.5’
> packageVersion("tidyverse")
[1] ‘1.3.0’
> 
> packageVersion("Biostrings")
[1] ‘2.56.0’
> packageVersion("msa")
[1] ‘1.20.0’
> packageVersion("DECIPHER")
[1] ‘2.16.0’

> # Print the version of R running:
> R.version.string
[1] "R version 4.0.0 (2020-04-24)"
> 
> # Print version information about R, the OS and attached or loaded packages.
> sessionInfo()
R version 4.0.0 (2020-04-24)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Mojave 10.14.6
```

----------
## NCBI Genome List
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

- NCBIのウェブサイトからゲノム配列データを取得する。
  - ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。
例えば、[新型コロナウイルス感染症 (COVID-19)](https://ja.wikipedia.org/wiki/新型コロナウイルス感染症_%282019年%29)の原因となる[SARSコロナウイルス2](https://ja.wikipedia.org/wiki/SARSコロナウイルス2) "SARS-CoV-2" を検索する。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2)、検索ボックス下の「Overview (1); Viruses (92)」のうち、「Viruses」をクリックすると、SARS-CoV-2に属する株が表示される。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2)、列**Organism Name**の"Severe acute respiratory syndrome coronavirus 2"をクリックして開く。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に[アクセッション番号](https://www.ddbj.nig.ac.jp/acc_def.html)が示されている。
アクセッション番号は、"NC_045512.2" (RefSeq) と "MN908947.3" (INSDC) である。

- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for [Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2), the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), you would type just Organism name "SARS-CoV-2" in the search box and press "Search".
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2), you will see the number of hits to "SARS-CoV-2" in each of the NCBI databases: "Overview (1); Viruses (92)". When you click on "Viruses", it will show all the strains.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2), When you click on the Organism Name "Severe acute respiratory syndrome coronavirus 2", it will bring you to the record for this organism in the NCBI Genome database.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732), you will see the "Replicon Info" of the Organism. 
The NCBI [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the DNA sequences are "NC_045512.2" (RefSeq) and "MN908947.3" (INSDC), respectively.

NCBIからDNA配列を取得する:  
```
# Retrieving a DNA sequence from NCBI
library(seqinr)
ACCESSION <- "NC_045512" # Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)
filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")
#filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 4
**課題4 「DNA Sequence Statistics (1)」**

Please download the R script (*my_assignment_chapter1_dna1.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 5
**課題5 「DNA Sequence Statistics (2)」**

Please download the R script (*my_assignment_chapter2_dna2.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

You can submit your assignment as a HTML document (*my_assignment_chapter2_dna2.html*), created using the [Compile Report](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report) command.

----------
## assignment 6
**課題6 「dotplot」**

Please download the R script (*my_assignment_chapter4_align_dotplot.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 7
**課題7 「Pairwise Sequence Alignment」**

Please download the R script (*my_assignment_chapter4_align_pairwise.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 8
**課題8 「Multiple Alignment and Phylogenetic trees」**

Please download the R script (*my_assignment_chapter5_msa_tree.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## [2020-12-08](https://github.com/haruosuz/DS4GD/blob/master/2020giga/README.md#2020-12-08)

R code

```
# ----------
# 1.  Let’s calculate Ka/Ks ratio
# ----------

#First, install and load the following packages!!! 

# Install the R packages:
options(repos="https://cran.ism.ac.jp/")
install.packages("seqinr")
install.packages("reshape")
install.packages("ggplot2")
install.packages("dplyr")
install.packages("pheatmap")

# Load the packages into R:
library(seqinr)
library(reshape)
library(ggplot2)
library(dplyr)
library(pheatmap)

# First, read alignment from system file in seqinr
s <- read.alignment(file = system.file("sequences/test.phylip", package = "seqinr"), format = "phylip")

#Check alignment
s
s$seq[1]

#Calculate Ka and Ks values using kaks function
result <- kaks(s) 

# ----------
# 1-1. Try to plot ka/ks data
# ----------

# Calculate Ka/Ks ratio
kaks <- as.matrix(result$ka/result$ks)

# Make a plot
pheatmap(kaks)

# ----------
# 1-2. Try to plot ka and ks for comparison
# ----------

# Store each ka and ks data from results you made
ka <- as.matrix(result$ka)
ks <- as.matrix(result$ks)

#Make an own function to get lower triangle of the Ka/Ks matrix table
get_lower <-function(k){
  k[upper.tri(k+1)] <- NA
  return(k+1)
}

# Extract values which are required for analysis
ka <- get_lower(ka)
ks <- get_lower(ks)

# ----------
# How to interpret the result?
# ----------

# Reshape table ()
kam <- melt(ka)
ksm <- melt(ks)

# For students who finished the above step, try this command to replace zero to ‘NA’.
kam <- kam %>% replace(.==0, NA)
ksm <- ksm %>% replace(.==0, NA)


# Change col names for plotting…
colnames (kam) <- c("Species1", "Species2", "Ka")
colnames (ksm) <- c("Species1", "Species2", "Ks")

# Merge kam and ksm using two redundant keys
# Final dataset containing ka and ks values
final <- merge (kam, ksm, by=c("Species1", "Species2"))

# Plot ka and ks values using ggplot2 package
p <- ggplot(final, aes(x=Ks, y=Ka, color=Species1, shape=Species2)) + geom_point(size=5) +  theme_bw() 

#Check plot
p

#Make custum plot…if you are interested in
p + geom_abline(slope = 1,intercept = 0, color = "red") + 
geom_text(aes(5,5,label = 'slope 1', vjust = -1), color="red") +
geom_abline(slope = 2, intercept = 0, color = "blue") + 
geom_text(aes(2.5,5,label = 'slope 2', vjust = -1), color="blue")
```

Case study: Ebola virus

NCBI Virus Variation Resource
<https://www.ncbi.nlm.nih.gov/genome/viruses/variation/>

```
# Download File from the Internet
url <- "https://raw.githubusercontent.com/haruosuz/DS4GD/master/2020giga/guest-speaker/2020-12-08/EBOV.L.28nt.fas"
filename <- basename(url) # filename <- "EBOV.L.28nt.fas"
if(!file.exists(filename)) download.file(url = url, destfile = filename)

# ----------
# Ka/Ks ratio calculation using Ebola virus
# ----------

#Read alignment of RNA polymerase L gene
s <- read.alignment(file = "EBOV.L.28nt.fas", format = "fasta")

#Calculate Ka and Ks values using kaks function
result <- kaks(s)  #You can directly calculate ka/ks ratio using this 

#Calculate Ka/Ks
kaks <- as.matrix(result$ka/result$ks)
kaks[is.infinite(kaks)] <- NA
pheatmap(kaks)

```

----------
## assignment 9
**課題9 「draft report」**

Integrate and modify your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it as a PDF/HTML document.

これまでの課題（興味あるDNA/タンパク質の配列を解析した結果など）を統合・修正してレポートのドラフトを作成し、PDF/HTML形式ファイルで提出する。

https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html

----------
## assignment 10
**課題10 「final report」**

Submit your final report as a PDF/HTML document.

----------

