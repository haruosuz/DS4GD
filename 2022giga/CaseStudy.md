[生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2] ](https://github.com/haruosuz/DS4GD)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題1 「Introduction to R」
- [assignment 2](#assignment-2) 課題2 「Installing R packages」
- [assignment 3](#assignment-3) 課題3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題5 「Dotplot」
- [assignment 6](#assignment-6) 課題6 「Pairwise Sequence Alignment」
- [assignment 7](#assignment-7) 課題7 「Choosing and Acquiring Sequences」
- [assignment 8](#assignment-8) 課題8 「Interim report」
- [assignment 12](#assignment-12) 課題12 「Multiple Alignment and Phylogenetic trees」
- [final assignment](#final-assignment) 最終課題 「Final report」

----------
## assignment 0
**選抜課題**

本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

----------
## assignment 1
**課題1 「Introduction to R」**

**my_datasciencedojo_r.R**

Watch the videos about R, and write your comments or questions.  
Rに関する動画を見て、コメントや疑問点を書く。  
- 2019/08/27 [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

[Example answer]  
```
I watched the videos Part 2 to Part 11 of [Introduction to R Programming - Data Science Dojo].

My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```


[回答例]
```
次の動画の Part 2 から Part 11 を見た。
[Introduction to R Programming - Data Science Dojo]

疑問点は次の通りである。
1. 行列とデータフレームとリストの違いが理解できなかった。
2. ファクターと文字列データの違いは？
```

----------

課題「Introduction to R」のコメント/疑問点に関連する資料  
References related to comments/questions for assignment "Introduction to R".  

- https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#assignment-1

----------
## assignment 2
**課題2 「Installing R packages」**

**my_setup_packages.R**

[回答例]  
[Example answer]  
```
> # Print the versions of these packages:
> packageVersion("tidyverse")
[1] ‘1.3.2’
> packageVersion("seqinr")
[1] ‘4.2.16’
> packageVersion("zoo")
[1] ‘1.8.11’
> packageVersion("ape")
[1] ‘5.6.2’
> packageVersion("phangorn")
[1] ‘2.10.0’
> packageVersion("phytools")
[1] ‘1.2.0’
> packageVersion("ggseqlogo")
[1] ‘0.1’
> packageVersion("microseq")
[1] ‘2.1.5’

> packageVersion("Biostrings")
[1] ‘2.62.0’
> packageVersion("msa")
[1] ‘1.26.0’
> packageVersion("DECIPHER")
[1] ‘2.22.0’

> # Print version information about R, the OS and attached or loaded packages.
> sessionInfo()
R version 4.1.3 (2022-03-10)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Monterey 12.5.1

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
**課題5 「Dotplot」**

**my_assignment_chapter4_align_dotplot.R**

----------
## assignment 6
**課題6 「Pairwise Sequence Alignment」**

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip
**my_assignment_chapter4_align_pairwise.R**

RStudioでRスクリプトを開く。**Compile Report**コマンドでPDFまたはHTML形式のレポートを作成する。そのレポートを課題として提出する。  
Open an R script in RStudio. Create report in PDF or HTML format using the **Compile Report** command. Submit the report as your assignment.  

[**Compile Report**](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report)

----------
## assignment 7
**課題7 「Choosing and Acquiring Sequences」**

[BLAST](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast) を用いて、系統樹に含める複数（4つ以上）の相同配列を同定する。  
Use [BLAST](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast) to identify multiple (>3) homologous sequences that are to be included on phylogenetic trees.  

**my_ds4gd_tree.R**

Edit the following R code (`database` `ACCESSIONs`):
```
database <- "ncbi_protein"
  ACCESSIONs <- c("NP_001393", "WP_011012522", "WP_001040724", "NP_001952", "WP_011013157", "NP_387993")
```
or
```
database <- "uniprot"
  ACCESSIONs <- c("P68104", "Q8U152", "P33166", "P13639", "P61877", "P80868")
```

Running the script **my_ds4gd_tree.R** will generate the following output files.
- myAA.fasta: unaligned sequences
- myAlign.fasta: aligned sequences
- myAlignTrim.fasta: trimmed aligned sequences
- myTree.tre: phylogenetic tree

----------
## assignment 8
**課題8 「Interim report」**

これまでの課題を選択・結合・編集して中間報告書を作成する。  
Select, combine, and edit the previous assignments to create an interim report.  

**my_interim_report.R**

----------
## assignment 12
**課題12 「Multiple Alignment and Phylogenetic trees」**

**my_assignment_chapter5_msa_tree.R**

----------
## final assignment
**最終課題 「Final report」**

[SOL](https://sol.sfc.keio.ac.jp/) にて最終レポートを提出する。  
Submit a final report in [SOL](https://sol.sfc.keio.ac.jp/).  

----------


