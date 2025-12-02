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
- [assignment 7](#assignment-7) 課題7 「Pairwise Sequence Alignment」
- [assignment 8](#assignment-8) 課題8 「Midterm report」
- [assignment 11](#assignment-11) 課題11 「Choosing and Acquiring Sequences」
- [assignment 12](#assignment-12) 課題12 「Multiple Alignment and Phylogenetic trees」
- [assignment final](#assignment-final) 最終課題 「Final report」

----------
## assignment 0
**選抜課題**

Describe the objects (DNA, RNA, protein, and other textual sequences, etc.) in which you would like to apply sequence analysis methods.

[Example answer]
I would like to use one of the following sequence data:
- Ribosomal protein https://en.wikipedia.org/wiki/Ribosomal_protein
- Elongation factor https://en.wikipedia.org/wiki/Elongation_factor
- RNA-dependent RNA polymerase (RdRp) or RNA replicase https://en.wikipedia.org/wiki/RNA-dependent_RNA_polymerase
- RNA polymerase (RNAP), or DNA-directed/dependent RNA polymerase https://en.wikipedia.org/wiki/RNA_polymerase
- Coronavirus spike protein https://en.wikipedia.org/wiki/Coronavirus_spike_protein

配列解析を適用したいオブジェクト（DNA、RNA、タンパク質、その他のテキスト配列など）を教えてください。

[回答例]
以下のいずれかの配列データを使用したい。
- リボソームタンパク質 https://ja.wikipedia.org/wiki/リボソーム
- 翻訳伸長因子 https://ja.wikipedia.org/wiki/EF-G https://ja.wikipedia.org/wiki/EF-Tu
- RNA依存性RNAポリメラーゼ (RdRp)、またはRNA複製酵素 https://ja.wikipedia.org/wiki/RNA依存性RNAポリメラーゼ
- DNA依存性RNAポリメラーゼ https://ja.wikipedia.org/wiki/RNAポリメラーゼ
- コロナウイルスのスパイクタンパク質 https://ja.wikipedia.org/wiki/スパイクタンパク質

----------
## assignment 1
**課題1 「Introduction to R」**

[Submit it via K-LMS.  
K-LMS にて提出する。](https://lms.keio.jp/)  

Watch the videos about R, and write your comments or questions.  
Rに関する動画を見て、コメントや疑問点を書く。  

[Example answer]  
```
#' I watched the videos Part 2 to Part 11 of  
#' [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx).  
#' 
#' My questions are as follows:  
#' - What is the difference between Data Frames and Lists in R?  
#' - What is the difference between factor and character vectors?  

```


[回答例]
```
#' 次の動画の Part 2 から Part 11 を見た。  
#' [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)  
#' 
#' 疑問点は次の通りである。  
#' - 行列とデータフレームとリストの違いが理解できなかった。  
#' - ファクターと文字列データの違いは？  

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

**my_assignment_1_dna1.R**

----------
## assignment 4
**課題4 「DNA Sequence Statistics (2)」**

**my_assignment_2_dna2.R**

----------
## assignment 7
**課題7 「Pairwise Sequence Alignment」**

**my_assignment_4_align.R**

----------
## assignment 8
**課題8 「Midterm report」**

**my_ds4gd_report.R**

これまでの課題を統合して、中間レポートを作成する。  
Integrate the previous assignments to create a midterm report.  

レポートは、以下のスクリプトからコードをコピーし、それを自分のスクリプトに貼り付けて編集することで作成します。  
The report will be created by copying the code from the script below, pasting it into your script, and editing it.  
```
my_assignment_1_dna1.R
my_assignment_2_dna2.R
my_assignment_4_align.R
```

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2025-10/scripts_ds4gd.zip

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
## assignment 11
**課題11 「Choosing and Acquiring Sequences」**

[BLAST](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#blast)  
Identify multiple (>3) homologous sequences that are to be included on phylogenetic trees.  
系統樹に含める複数（4つ以上）の相同配列を同定する。  

Copy the downloaded file (e.g., `uniprotkb_2025_06_23.fasta`) and give it a different name (`myAA.fasta`).  
ダウンロードしたファイル（例：`uniprotkb_2025_06_23.fasta`）をコピーして別の名前（`myAA.fasta`）を付ける。  
```
cp uniprotkb_2025_06_23.fasta myAA.fasta
```

Change the author name and replace the FASTA file.  
以下のスクリプトの著者名を変更し、FASTA ファイルを差し替えてください。  
`scripts_ds4gd/my_tree_aa/my_tree_aa.R`
```
#' author: '@Haruo_Suzuki'
```
```
file.fasta <- "myAA.fasta" # FASTA file of protein (amino acid) sequences
```

The R script will generate the following output files:  
- `myAA_filtered.fasta`: Sequences filtered based on length criteria.
- `myAlign.fasta`: Aligned sequences.
- `myAlignTrim.fasta`: Aligned sequences trimmed (gaps removed).
- `myTree.pdf`: Phylogenetic tree in PDF format.
- `myTree.tre`: Phylogenetic tree in Newick format.
- `myTable.tsv`: Sequence information, including length and annotations.

----------
## assignment 12
**課題12 「Multiple Alignment and Phylogenetic trees」**

**my_assignment_5_msa_tree.R**

----------
## assignment final
**最終課題 「Final report」**

**my_ds4gd_report.R**

これまでの課題を統合して、最終レポートを作成する。  
Integrate the previous assignments to create a final report.  

レポートは、以下のスクリプトからコードをコピーし、それを自分のスクリプトに貼り付けて編集することで作成します。  
The report will be created by copying the code from the script below, pasting it into your script, and editing it.  
```
my_assignment_1_dna1.R
my_assignment_2_dna2.R
my_assignment_4_align.R
my_assignment_5_msa_tree.R
```

----------



