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
- [assignment 9](#assignment-9) 課題9 「Guest speaker 2024-06-11」
- [assignment 11](#assignment-11) 課題11 「Guest speaker 2024-06-25」
- [assignment 12](#assignment-12) 課題12 「Multiple Alignment and Phylogenetic trees」
- [final assignment](#final-assignment) 最終課題 「final report」

----------
## assignment 0
**選抜課題**

Describe the objects (DNA, RNA, protein, and other textual sequences, etc.) in which you would like to apply sequence analysis methods.

[Example answer]
I would like to use one of the following sequence data:
- Coronavirus spike protein https://en.wikipedia.org/wiki/Coronavirus_spike_protein
- Elongation factor https://en.wikipedia.org/wiki/Elongation_factor
- membrane-associated guanylate kinases (MAGUK) | https://pubmed.ncbi.nlm.nih.gov/20359327/ BMC Evol Biol. 2010 Apr 1:10:93. Evolution of the MAGUK protein gene family in premetazoan lineages
- Single-stranded (ss) DNA viruses | https://pubmed.ncbi.nlm.nih.gov/31366885/ Nat Commun. 2019 Jul 31;10(1):3425. Multiple origins of prokaryotic and eukaryotic single-stranded DNA viruses from bacterial and archaeal plasmids

配列解析を適用したいオブジェクト（DNA、RNA、タンパク質、その他のテキスト配列など）を教えてください。

[回答例]
以下のいずれかの配列データを使用したい。
- コロナウイルスのスパイクタンパク質 https://ja.wikipedia.org/wiki/スパイクタンパク質
- 翻訳伸長因子 Elongation Factor https://ja.wikipedia.org/wiki/EF-G https://ja.wikipedia.org/wiki/EF-Tu
- membrane-associated guanylate kinases (MAGUK) | https://pubmed.ncbi.nlm.nih.gov/20359327/ BMC Evol Biol. 2010 Apr 1:10:93. Evolution of the MAGUK protein gene family in premetazoan lineages
- 一本鎖DNAウイルス Single-stranded (ss) DNA viruses | https://pubmed.ncbi.nlm.nih.gov/31366885/ Nat Commun. 2019 Jul 31;10(1):3425. Multiple origins of prokaryotic and eukaryotic single-stranded DNA viruses from bacterial and archaeal plasmids

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

課題「Introduction to R」に対するコメントや疑問点に関連する資料  
References related to comments or questions for assignment "Introduction to R".  

https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#assignment-1

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

[BLAST](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#blast)  
Identify multiple (>3) homologous sequences that are to be included on phylogenetic trees.  
系統樹に含める複数（4つ以上）の相同配列を同定する。  

Copy the downloaded file ("uniprotkb_YYYY_MM_DD.fasta") and give it a different name ("myAA.fasta").  
ダウンロードしたファイル（"uniprotkb_YYYY_MM_DD.fasta"）をコピーして別の名前（"myAA.fasta"）を付ける。  
```
cp uniprotkb_YYYY_MM_DD.fasta myAA.fasta

cp uniprotkb_2024_05_21.fasta myAA.fasta
```

**my_tree_aa/my_tree_aa.R**
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
**課題9 「Guest speaker 2024-06-11」**

本日の特別講演に関するコメントや質問など記載して提出する。  
Please write and submit any comments, questions, or anything else related to today's special lecture.  

----------
## assignment 11
**課題11 「Guest speaker 2024-06-25」**

本日の特別講演に関するコメントや質問など記載して提出する。  
Please write and submit any comments, questions, or anything else related to today's special lecture.  

----------
## assignment 12
**課題12 「Multiple Alignment and Phylogenetic trees」**

**my_assignment_chapter5_msa_tree.R**

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip

圧縮ファイルを解凍し、ディレクトリに移動する。  
unzip the compressed file and change to the directory.  
```
unzip scripts_ds4gd.zip
cd scripts_ds4gd/
```

[RStudioでRスクリプトを開き、編集し、保存する。  
Open, edit, and save the R script in RStudio.  ](https://r4ds.had.co.nz/workflow-scripts.html)

[**Compile Report**コマンドでHTML形式のレポートを作成する。  
Create report in format using the **Compile Report** command.  ](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#compile-report)

[.htmlファイルを課題として K-LMS にて提出する。  
Submit the .html file as your assignment in K-LMS.  ](https://lms.keio.jp/)  

編集したファイルは別のディレクトリに保存・バックアップすることをおすすめします。  
Please save and backup your edited files in a separate directory. 

----------
## final assignment
**最終課題 「final report」**

これまでの課題を選択・結合・編集して最終レポートを作成する。  
Select, combine, and edit the previous assignments to create a final report.  

----------

