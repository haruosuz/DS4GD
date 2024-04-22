**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2021)**  
[SFC Online Learning System (SOL)](https://sol.sfc.keio.ac.jp/)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題1 「Introduction to R」
- [INSDC](#insdc)
- [NCBI Genome List](#ncbi-genome-list)
- [MEGA](#mega)
- [assignment 2](#assignment-2) 課題2 「Installing R packages」
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

課題「Introduction to R」に対するコメントや疑問点に関連する資料  
References related to comments or questions for assignment "Introduction to R".  

https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#assignment-1

### R_assignOps
### R_data.frame
### R_factor
### R_matrix
### R_quit
### R_read.table
### R_typeof
### R_vector

----------

https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#insdc

## INSDC
## NCBI Genome List

----------

https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#mega

## MEGA
### PTME5
### R/MEGA

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

