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
- [assignment 9](#assignment-9) 課題9 「Multiple Alignment and Phylogenetic trees」
- [final assignment](#final-assignment) 最終課題 「final report」

----------
## assignment 0
**選抜課題**

Please describe sequences of interest (DNA, RNA, protein, etc.) that you would like to analyze in this class.

[Example answer]
- Ribosomal protein https://en.wikipedia.org/wiki/Ribosomal_protein
- Elongation factor https://en.wikipedia.org/wiki/Elongation_factor
- Coronavirus spike protein https://en.wikipedia.org/wiki/Coronavirus_spike_protein
- Single-strand DNA-binding protein https://en.wikipedia.org/wiki/Single-strand_DNA-binding_protein
- FOX (forkhead box) proteins https://en.wikipedia.org/wiki/FOX_proteins

この授業で解析したい配列（DNA、RNA、タンパク質など）を教えてください。

[回答例]
- リボソームタンパク質 https://ja.wikipedia.org/wiki/リボソームタンパク質SA
- 細菌の翻訳伸長因子 elongation factor https://ja.wikipedia.org/wiki/EF-G https://ja.wikipedia.org/wiki/EF-Tu 
- スパイクタンパク質 https://ja.wikipedia.org/wiki/スパイクタンパク質
- 一本鎖DNA結合タンパク質 https://ja.wikipedia.org/wiki/一本鎖DNA結合タンパク質
- フォークヘッドボックスタンパク質 / FOXタンパク質 https://ja.wikipedia.org/wiki/フォークヘッドボックスタンパク質

----------
## assignment 1
**課題1 「Introduction to R」**

**my_datasciencedojo_r.R**

- 2019/08/27 [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

Watch the videos about R, and write your comments or questions.  
Rに関する動画を見て、コメントや疑問点を書く。  

[Example answer]  
```
#' 
#' I watched the videos Part 2 to Part 11 of  
#' [Introduction to R Programming - Data Science Dojo].  
#' 
#' My questions are as follows:  
#' - What is the difference between Data Frames and Lists in R?  
#' - What is the difference between factor and character vectors?  
#' 
```


[回答例]
```
#' 
#' 次の動画の Part 2 から Part 11 を見た。  
#' [Introduction to R Programming - Data Science Dojo]  
#' 
#' 疑問点は次の通りである。  
#' - 行列とデータフレームとリストの違いが理解できなかった。  
#' - ファクターと文字列データの違いは？  
#' 
```

----------
## assignment 2
**課題2 「Installing R packages」**

**my_setup_packages.R** 


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
Identify multiple (>3) homologous sequences that are to be included on phylogenetic trees.  
系統樹に含める複数（4つ以上）の相同配列を同定する。  

**my_ds4gd_tree.R**
```
file.fasta <- "myAA.fasta" # Replace this FASTA file with your own data.
```

The R script will generate the following output files:
- `myAA_filtered.fasta`: Sequences filtered based on length criteria.
- `myAlign.fasta`: Aligned sequences.
- `myAlignTrim.fasta`: Aligned sequences trimmed (gaps removed).
- `myTree.pdf`: Phylogenetic tree in PDF format.
- `myTree.tre`: Phylogenetic tree in Newick format.
- `myTable.tsv`: Sequence information, including length and annotations.

----------
## assignment 8
**課題8 「midterm report」**

これまでの課題を選択・結合・編集して中間レポートを作成する。  
Select, combine, and edit the previous assignments to create a midterm report.  

**my_ds4gd_report.R**

----------
## assignment 9
**課題9 「Multiple Alignment and Phylogenetic trees」**

**my_assignment_chapter5_msa_tree.R**

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2023-10/scripts_ds4gd.zip

圧縮ファイルを解凍し、ディレクトリに移動する。  
unzip the compressed file and change to the directory.  
```
unzip scripts_ds4gd.zip
cd scripts_ds4gd/
```

[RStudioでRスクリプトを開き、編集し、保存する。  
Open, edit, and save the R script in RStudio.  ](https://r4ds.had.co.nz/workflow-scripts.html)

[**Compile Report**コマンドでHTML形式のレポートを作成する。  
Create report in format using the **Compile Report** command.  ](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report)

[.htmlファイルを課題としてSOLにて提出する。  
Submit the .html file as your assignment in SOL.  ](https://sol.sfc.keio.ac.jp/)  

編集したファイルは別のディレクトリに保存・バックアップすることをおすすめします。  
Please save and backup your edited files in a separate directory. 

----------
## final assignment
**最終課題 「final report」**

これまでの課題を選択・結合・編集して最終レポートを作成する。  
Select, combine, and edit the previous assignments to create a final report.  

**my_ds4gd_report.R**

----------


