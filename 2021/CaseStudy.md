**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2021)**  
[SFC Online Learning System (SOL)](https://sol.sfc.keio.ac.jp/)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題1 「Introduction to R」
- [MEGA](#mega)
- [assignment 2](#assignment-2) 課題2 「Installing R packages」
- [INSDC](#insdc)
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題5 「dotplot」
- [assignment 6](#assignment-6) 課題6 「Pairwise Sequence Alignment」
- [assignment 9](#assignment-9) 課題9 「Multiple Alignment and Phylogenetic trees」
- [assignment 10](#assignment-10) 課題10 「draft report」
- [assignment 13](#assignment-13) 課題13 「final report」

----------
## assignment 0
**選抜課題**

本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

----------
## assignment 1
**課題1 「Introduction to R」**

次のURLからRスクリプトをダウンロードして下さい。  
Please download R scripts (**my_datasciencedojo_r.R**, **my_darumalab.R**) from the following URL.  
https://github.com/haruosuz/r4bioinfo/raw/master/scripts/my_basic_r.zip

Watch the following videos and write your comments or questions.
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)
  - **my_basic_r/my_datasciencedojo_r.R**

[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

以下の動画を見て、疑問点を報告する。
- [Rプログラミングと統計](https://tomoecon.github.io/R_for_graduate_thesis/Rbasics.html)
  - **my_basic_r/my_darumalab.R**


[回答例]
```
「Rプログラミングと統計 p.3 ~ p.10 を見た。
疑問点は次の通りである。
1. 行列とデータフレームとリストの違いが理解できなかった。
2. ファクターと文字列データの違いは？
```

----------
### R_assignOps

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_assignOps

----------
### R_data.frame

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_dataframe

----------
### R_factor

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_factor

----------
### R_matrix

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_matrix

----------
### R_quit

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_quit

----------
### R_read.table

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_readtable

----------
### R_typeof

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_typeof

----------
### R_vector

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_vector

----------
### R/MEGA

8th Aug, 2017
https://www.researchgate.net/post/Does-anybody-have-a-pipeline-created-or-experience-of-taking-Phylogenetic-trees-from-MEGA-to-Rggtree
Does anybody have a pipeline created or experience of taking Phylogenetic trees from MEGA to R(ggtree)?

https://support.bioconductor.org/p/41863/
Packages reproducing phylogenetic tree from output of MEGA
|
You can save the tree from MEGA in newick format.
APE is an R package that reads newick format and has a lot of options
to
plot phylogenetic trees.

----------
## MEGA
MEGA: Molecular Evolutionary Genetics Analysis software

https://www.megasoftware.net/

Download MEGA X

| OS              |                 | Version         |
|:----------------|:----------------|:----------------|
| Windows / macOS | Graphical (GUI) | MEGA X (64-bit) |

Documentation
[Online Manual](https://www.megasoftware.net/web_help)
First Time User

[walkthrough tutorial](https://www.megasoftware.net/web_help_10/Introduction.htm)
Introduction

- [Mega Basics](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/MEGA_Basics.htm)
  - Opening (activating) a Data File for Analysis | Example 1.2: "Drosophila_Adh.meg" file
- [Aligning Sequences](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Aligning_Sequences.htm)
  - Opening an Alignment | Example 2.1: "hsp20.fas" file
  - Aligning Sequences by ClustalW | Example 2.2: "hsp20.fas" file
  - Aligning Sequences Using Muscle | Example 2.3: "Chloroplast_Martin.meg" file
  - Obtaining Sequence Data from the Internet (GenBank)
- [Estimating Evolutionary Distances](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Estimating_Evolutionary_Distances.htm)
  - Estimating Evolutionary Distances Using Pairwise Distance | Example 3.1: "Drosophila_Adh.meg" file
  - Compute the Proportion of Amino Acid Differences | Example 3.3: "Drosophila_Adh.meg" file
- [Building Trees from Sequence Data](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Building_Trees_From_Sequence_Data.htm)
  - Building a Neighbor-Joining (NJ) Tree | Example 4.1: "Crab_rRNA.meg" file
  - Printing the NJ Tree (For Windows users) | Example 4.2a:   
  - Printing the NJ Tree (For Mac users) | Example 4.2b:
- [Testing Tree Reliability](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Testing_Tree_Reliability.htm)
  - Bootstrap Testing for a Neighbor-Joining Tree | Example 5.1: "Chloroplast_Martin.meg" file

Site Links
[Videos](https://www.megasoftware.net/videos)
Instructional Videos

- Author: Barry Hall
  - [Choosing and Acquiring Sequences Part 1](https://youtu.be/raaOgtvMJWw) Choosing and Acquiring the Sequences for a Phylogenetic Tree
  - [Choosing and Acquiring Sequences Part 2](https://youtu.be/cVdmH7nNboE) Aligning Coding Sequences
  - [Reconstructing Ancestral Sequences](https://youtu.be/djju9WFMvn0)

### PTME5
[Barry G. Hall (2017) Phylogenetic Trees Made Easy: A How-To Manual (5th edition)](https://global.oup.com/ushe/product/phylogenetic-trees-made-easy-9781605357102?cc=jp&lang=en&#fragment-4)

[Student Resources](https://learninglink.oup.com/access/hall-5e-student-resources)
Click a link **PTME5e Companion Files** to download the package appropriate to your OS (Linux, Mac, Win).

----------
## assignment 2
**課題2 「Installing R packages」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

**my_setup_packages.R**

回答例:  
```
# Example answer:  

> # Print the versions of these packages:
> packageVersion("tidyverse")
[1] ‘1.3.0’
> packageVersion("seqinr")
[1] ‘4.2.5’
> packageVersion("zoo")
[1] ‘1.8.9’
> packageVersion("ape")
[1] ‘5.4.1’
> packageVersion("phangorn")
[1] ‘2.6.3’
> packageVersion("phytools")
[1] ‘0.7.70’
> packageVersion("msaR")
[1] ‘0.5.0’
> packageVersion("microseq")
[1] ‘2.1.4’
> 
> packageVersion("Biostrings")
[1] ‘2.58.0’
> packageVersion("msa")
[1] ‘1.22.0’
> packageVersion("DECIPHER")
[1] ‘2.18.1’

> # Print the version of R running:
> R.version.string
[1] "R version 4.0.3 (2020-10-10)"
> 
> # Print version information about R, the OS and attached or loaded packages.
> sessionInfo()
R version 4.0.3 (2020-10-10)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Catalina 10.15.7
```

----------
## INSDC

[International Nucleotide Sequence Database Collaboration](https://www.ddbj.nig.ac.jp/insdc-e.html)
[塩基配列データベース構築の国際協調](https://www.ddbj.nig.ac.jp/insdc.html)

<img src="https://www.ddbj.nig.ac.jp/assets/images/center/insdc_shoukai.gif" alt="https://www.ddbj.nig.ac.jp/about/insdc.html" width=25%>

- [RefSeq Frequently Asked Questions (FAQ) - RefSeq Help - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK50679/)
  - [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
  - [What causes the version number of a RefSeq record to change?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_causes_the_version_number)
  - [What updates to RefSeq records need a simple version number change and which require a new accession number?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_updates_to_refseq_records)
- VERSION
  - [DDBJ flat file format](https://www.ddbj.nig.ac.jp/ddbj/flat-file-e.html#VERSION)
This line consists of an accession number and a version number, like “AB123456.1”, in which the digit(s) after the period is a version number.
The data open to public for the first time is version number as “1”. The reason for adding VERSION is that since a released sequence sometimes revised by the submitter, the accession number alone cannot specify the sequence in question causing the user a trouble. The number is increased by one every time when a revised sequence is made public. And accession number will NOT be changed generally.
  - [DDBJ 公開形式 Flat file](https://www.ddbj.nig.ac.jp/ddbj/flat-file.html#VERSION)
アクセッション番号とバージョン番号で構成されています。
はじめて公開されたデータは、バージョン番号は “1” が記載されています。当該エントリの配列が訂正・更新された場合には、バージョン番号が更新されます。通常、配列が訂正・更新された場合にアクセッション番号が変更されることはありません。

----------
## NCBI Genome List
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for [Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2), the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), you would type just Organism name "SARS-CoV-2" in the search box and press "Search".
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2), you will see the number of hits to "SARS-CoV-2" in each of the NCBI databases: "Overview (1); Viruses (92)". When you click on "Viruses", it will show all the strains.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2), When you click on the **Organism Name** "Severe acute respiratory syndrome coronavirus 2", it will bring you to the record for this organism in the NCBI Genome database.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732), you will see the **Replicon Info** of the Organism. 
The NCBI [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the DNA sequences are "NC_045512" (**RefSeq**) and "MN908947" (**INSDC**), respectively.

- NCBIのウェブサイトからゲノム配列データを取得する。
  - ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。
例えば、[新型コロナウイルス感染症 (COVID-19)](https://ja.wikipedia.org/wiki/新型コロナウイルス感染症_%282019年%29)の原因となる[SARSコロナウイルス2](https://ja.wikipedia.org/wiki/SARSコロナウイルス2) "SARS-CoV-2" を検索する。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2)、検索ボックス下の「Overview (1); Viruses (92)」のうち、「Viruses」をクリックすると、SARS-CoV-2に属する株が表示される。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2)、列**Organism Name**の"Severe acute respiratory syndrome coronavirus 2"をクリックして開く。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に[アクセッション番号](https://www.ddbj.nig.ac.jp/acc_def.html)が示されている。
アクセッション番号は、"NC_045512" (**RefSeq**) と "MN908947" (**INSDC**) である。

NCBIからDNA配列を取得する:  
```
# Retrieving a DNA sequence from NCBI
library(seqinr)

ACCESSION <- "NC_045512" # SARS-CoV-2
#ACCESSION <- "NC_001477" # Dengue virus 1

filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
#filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")

# Retrieve the sequence and store it in list variable "seqs"
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]

# Get sequence annotations
getAnnot(seq1)
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 3
**課題3 「DNA Sequence Statistics (1)」**

**my_assignment_chapter1_dna1.R**

----------
## assignment 4
**課題4 「DNA Sequence Statistics (2)」**

**my_assignment_chapter2_dna2.R**

----------
## assignment 5
**課題5 「dotplot」**

**my_assignment_chapter4_align_dotplot.R**

----------
## assignment 6
**課題6 「Pairwise Sequence Alignment」**

**my_assignment_chapter4_align_pairwise.R**

----------
## assignment 9
**課題9 「Multiple Alignment and Phylogenetic trees」**

**my_assignment_chapter5_msa_tree.R**

PDF/HTML形式ファイルで提出して下さい。  
Please submit your assignment as a PDF or HTML document, created using the [Compile Report](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report) command.

----------
## assignment 10
**課題10 「draft report」**

Select, combine, and revise the previous assignments (e.g., results of analyzing DNA and protein sequence data) to create a draft report and submit it as a PDF/HTML format file.

これまでの課題（DNAやタンパク質の配列データを解析した結果など）を選択・結合・修正してレポートのドラフトを作成し、PDF/HTML形式ファイルで提出する。

----------
## assignment 13
**課題13 「final report」**

Submit your final report as a PDF/HTML document.

最終レポートをPDF/HTML形式ファイルで提出する。

- https://en.wikipedia.org/wiki/IMRAD
(Introduction, Methods, Results, and Discussion) is a common organizational structure (a document format).
- https://ja.wikipedia.org/wiki/IMRAD
は、文章構成の型式の名称の1つである。
  - Title（タイトル; T）
  - Introduction（導入; I） :What are you studying and why?(何を研究したのか？、何故それを研究したのか)
  - Methods（研究方法; M） :What did you do?（具体的には何をしたのか？）
  - Results（実験結果; R） :What did you find?（何がわかったのか?）
  - Discussion（考察; D） :What do your findings mean?(あなたが見つけたことは何を意味するのか？）
  - References（参考文献一覧）

----------

