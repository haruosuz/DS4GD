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
- [assignment 8](#assignment-8) 課題8 「midterm report」
- [assignment 11](#assignment-11) 課題11 「Multiple Alignment and Phylogenetic trees」
- [final assignment](#final-assignment) 最終課題 「final report」

----------
## assignment 0
**選抜課題**

この授業で解析したい配列（DNA、RNA、タンパク質など）を教えてください。

[回答例]
- リボソームタンパク質 https://ja.wikipedia.org/wiki/リボソームタンパク質SA
- 細菌の翻訳伸長因子 elongation factor https://ja.wikipedia.org/wiki/EF-G https://ja.wikipedia.org/wiki/EF-Tu 
- スパイクタンパク質 https://ja.wikipedia.org/wiki/スパイクタンパク質
- 一本鎖DNA結合タンパク質 https://ja.wikipedia.org/wiki/一本鎖DNA結合タンパク質
- フォークヘッドボックスタンパク質 / FOXタンパク質 https://ja.wikipedia.org/wiki/フォークヘッドボックスタンパク質

Please describe sequences of interest (DNA, RNA, protein, etc.) that you would like to analyze in this class.

[Example answer]
- Ribosomal protein https://en.wikipedia.org/wiki/Ribosomal_protein
- Elongation factor https://en.wikipedia.org/wiki/Elongation_factor
- Coronavirus spike protein https://en.wikipedia.org/wiki/Coronavirus_spike_protein
- Single-strand DNA-binding protein https://en.wikipedia.org/wiki/Single-strand_DNA-binding_protein
- FOX (forkhead box) proteins https://en.wikipedia.org/wiki/FOX_proteins

----------
## assignment 1
**課題1 「Introduction to R」**

https://github.com/haruosuz/DS4GD/blob/master/2023-04/README.md#r-rstudio

**my_datasciencedojo_r.R**

- 2019/08/27 [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

Watch the videos about R, and write your comments or questions.  
Rに関する動画を見て、コメントや疑問点を書く。  

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
[1] ‘4.2.30’
> packageVersion("zoo")
[1] ‘1.8.11’
> packageVersion("ape")
[1] ‘5.7.1’
> packageVersion("phangorn")
[1] ‘2.11.1’
> packageVersion("phytools")
[1] ‘1.5.1’
> packageVersion("geiger")
[1] ‘2.0.11’
> packageVersion("ggseqlogo")
[1] ‘0.1’
> packageVersion("microseq")
[1] ‘2.1.5’

> packageVersion("Biostrings")
[1] ‘2.66.0’
> packageVersion("msa")
[1] ‘1.30.1’
> packageVersion("DECIPHER")
[1] ‘2.26.0’


> # Print version information about R, the OS and attached or loaded packages.
> sessionInfo()
R version 4.2.3 (2023-03-15)
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

**my_assignment_chapter4_align_pairwise.R**

----------
## assignment 7
**課題7 「Choosing and Acquiring Sequences」**

[BLAST](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast)  
BLASTを用いて、系統樹に含める複数（4つ以上）の相同配列を同定する。  
BLAST is used to identify multiple (>3) homologous sequences that are to be included on phylogenetic trees.  

**my_ds4gd_tree.R**
```
file.fasta <- "myAA.fasta" # Replace this FASTA file with your own data.
```

Running the script **my_ds4gd_tree.R** will generate the following output files:
- myAlign.fasta: Aligned sequences.
- myAlignTrim.fasta: Trimmed aligned sequences.
- myTree.tre: Phylogenetic tree.
- myTable.tsv: Sequence information, including length and annotations.

----------
## assignment 8
**課題8 「midterm report」**

これまでの課題を選択・結合・編集して中間報告書を作成する。  
Select, combine, and edit the previous assignments to create a midterm report.  

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip

圧縮ファイル **scripts_ds4gd.zip** を解凍・展開する。  
Please unzip/extract the compressed file **scripts_ds4gd.zip**.  

ディレクトリ **scripts_ds4gd/** 内で作業する。 
Work within the directory **scripts_ds4gd/**.  

**my_ds4gd_midterm_report.R**

[RStudioでRスクリプトを開く。  
Open an R script in RStudio.  ](https://r4ds.had.co.nz/workflow-scripts.html)

Rスクリプトを編集し、変更を加えた後、保存する。  
Edit the R script, make any necessary changes, and then save it.  

[**Compile Report**コマンドでHTML形式のレポートを作成する。  
Create report in format using the **Compile Report** command.  ](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report)

[.htmlファイルを課題としてSOLにて提出する。  
Submit the .html file as your assignment in SOL.  ](https://sol.sfc.keio.ac.jp/)  

編集したファイルは別のディレクトリに保存・バックアップすることをおすすめします。  
Please save and backup your edited files in a separate directory.  

----------
## assignment 11
**課題11 「Multiple Alignment and Phylogenetic trees」**

**my_assignment_chapter5_msa_tree.R**

----------
## final assignment
**最終課題 「final report」**

[SOL](https://sol.sfc.keio.ac.jp/) にて最終レポートを提出する。  
Submit a final report in [SOL](https://sol.sfc.keio.ac.jp/).  

----------




