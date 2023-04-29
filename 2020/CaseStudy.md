**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2020)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [BLAST](#blast)
  - [UniProt BLAST](#uniprot-blast)
  - [NCBI BLAST](#ncbi-blast)
    - [blastp](#blastp)
    - [tblastn](#tblastn)
  - [Query Sequences](#query-sequences)
- [Chunk options](#chunk-options)
- [Compile Report](#compile-report)
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「Introduction to R」
[](#)
[R_DSD_10](#r_dsd_10)
[R_assignOps](#r_assignOps)
[R_built-in](#r_built-in)
[R_data.frame](#r_dataframe)
[R_factor](#r_factor)
[R_indexing](#r_indexing)
[R_list](#r_list)
[R_matrix](#r_matrix)
[R_object](#r_object)
[R_operator](#r_operator)
[R_options](#r_options)
[R_plot](#r_plot)
[R_quit](#r_quit)
[R_quotes](#r_quotes)
[R_read.table](#r_readtable)
[R_typeof](#r_typeof)
[R_vector](#r_vector)
[](#)
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [assignment 8](#assignment-8) 課題No.8 「dotplot」
- [assignment 9](#assignment-9) 課題No.9 「Pairwise Sequence Alignment」
- [assignment 10](#assignment-10) 課題No.10 「Multiple Alignment and Phylogenetic Trees」
- [assignment 11](#assignment-11) 課題No.11 「draft report」
- [Class Survey](#class-survey) 授業調査

----------
## BLAST
BLAST (Basic Local Alignment Search Tool)

### UniProt BLAST
https://www.uniprot.org/blast/

![https://www.ebi.ac.uk/training/online/courses/uniprot-exploring-protein-sequence-and-functional-info/how-to-use-uniprot-tools-clone/](https://www.ebi.ac.uk/training/online/courses/uniprot-exploring-protein-sequence-and-functional-info/wp-content/uploads/sites/100/2022/07/Screenshot-2022-07-22-at-14.33.12.png)

[BLAST sequence similarity searching](https://www.ebi.ac.uk/training/online/courses/uniprot-exploring-protein-sequence-and-functional-info/how-to-use-uniprot-tools-clone/blast-sequence-similarity-searching/)

- Select the **BLAST** tab of the toolbar at the top of the page.
- Enter either *UniProt IDs* or *Protein or nucleotide sequence(s) in FASTA format.
- [Optional settings](https://www.uniprot.org/help/sequence-searches)
  - Target database: UniProtKB Swiss-Prot
  - E-Threshold: 0.0001
  - Hits: 50
- Click the **Run BLAST** button.

### [NCBI BLAST](https://blast.ncbi.nlm.nih.gov/)

#### blastp
[Protein BLAST: search protein databases using a protein query](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastp&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)

- Query the NCBI Protein database by searching on the words [**ebgC Bacteroides**](https://www.ncbi.nlm.nih.gov/protein/?term=ebgC%20Bacteroides).
- Test the homology between
*Escherichia coli* EbgC protein (accession number [NP_417548.1](https://www.ncbi.nlm.nih.gov/protein/NP_417548.1))
and *Bacteroides* EbgC protein (accession number [EFI39110.1](https://www.ncbi.nlm.nih.gov/protein/EFI39110.1))
using [Protein BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastp&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome).
  - Checking the **Align two or more sequences** box will display two text boxes for entering queries.
  - Enter the accession number **NP_417548.1** into the upper search box.
  - Enter the accession number **EFI39110.1** into the lower search box.
  - Click on **+ Algorithm parameters**, change **Expect threshold** from 0.05 to 10, and then click the **BLAST** button.
  - The result shows an E value of 1.8 (above the limit of 1e-3 for homologs). Thus, despite having the same name, the *Bacteroides* EbgC sequences are not homologs of the *Escherichia coli* EbgC sequence.

##### References
- Barry Hall (2017) [Phylogenetic Trees Made Easy: A How-To Manual (5th edition)](https://github.com/haruosuz/DS4GD/blob/master/2021/CaseStudy.md#ptme5)
(p.48) Other Ways to Find Sequences of Interest (Beware! The Risks Are High)
- [Blast 2 sequences: aligning two protein or nucleotide sequences](https://academic.oup.com/femsle/article/174/2/247/502616)

#### tblastn
[tblastn: search translated nucleotide databases using a protein query](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=tblastn&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)

- **Enter Query Sequence** into the form field:
```
>tr|A0PQ23|A0PQ23_MYCUA Chorismate pyruvate-lyase OS=Mycobacterium ulcerans (strain Agy99) OX=362242 GN=MUL_2003 PE=4 SV=1
MLAVLPEKREMTECHLSDEEIRKLNRDLRILIATNGTLTRILNVLANDEIVVEIVKQQIQ
DAAPEMDGCDHSSIGRVLRRDIVLKGRRSGIPFVAAESFIAIDLLPPEIVASLLETHRPI
GEVMAASCIETFKEEAKVWAGESPAWLELDRRRNLPPKVVGRQYRVIAEGRPVIIITEYF
LRSVFEDNSREEPIRHQRSVGTSARSGRSICT
```
- Click on **Algorithm parameters**, and select/change values as follows:
  - Max target sequences: 5000
  - Expect threshold: 1e-20
- Click on **BLAST** button to execute.

### Query Sequences

https://rest.uniprot.org/uniprotkb/Q9CD83.fasta
```
>sp|Q9CD83|PHBS_MYCLE Chorismate pyruvate-lyase OS=Mycobacterium leprae (strain TN) OX=272631 GN=ML0133 PE=3 SV=1
MTNRTLSREEIRKLDRDLRILVATNGTLTRVLNVVANEEIVVDIINQQLLDVAPKIPELE
NLKIGRILQRDILLKGQKSGILFVAAESLIVIDLLPTAITTYLTKTHHPIGEIMAASRIE
TYKEDAQVWIGDLPCWLADYGYWDLPKRAVGRRYRIIAGGQPVIITTEYFLRSVFQDTPR
EELDRCQYSNDIDTRSGDRFVLHGRVFKNL
```

https://rest.uniprot.org/uniprotkb/A0PQ23.fasta
```
>tr|A0PQ23|A0PQ23_MYCUA Chorismate pyruvate-lyase OS=Mycobacterium ulcerans (strain Agy99) OX=362242 GN=MUL_2003 PE=4 SV=1
MLAVLPEKREMTECHLSDEEIRKLNRDLRILIATNGTLTRILNVLANDEIVVEIVKQQIQ
DAAPEMDGCDHSSIGRVLRRDIVLKGRRSGIPFVAAESFIAIDLLPPEIVASLLETHRPI
GEVMAASCIETFKEEAKVWAGESPAWLELDRRRNLPPKVVGRQYRVIAEGRPVIIITEYF
LRSVFEDNSREEPIRHQRSVGTSARSGRSICT
```

----------
----------
## Chunk options

https://rmarkdown.rstudio.com/lesson-3.html
Chunk Options
- include = FALSE prevents code and results from appearing in the finished file. R Markdown still runs the code in the chunk, and the results can be used by other chunks.
- echo = FALSE prevents code, but not the results from appearing in the finished file. This is a useful way to embed figures.
- message = FALSE prevents messages that are generated by code from appearing in the finished file.

https://r4ds.had.co.nz/
R for Data Science
- https://r4ds.had.co.nz/r-markdown.html
  - https://r4ds.had.co.nz/r-markdown.html#code-chunks
    - https://r4ds.had.co.nz/r-markdown.html#chunk-options

2021/05/15
https://rpubs.com/ktgrstsh/755893
R Markdown 入門 (Tokyo.R #91)
コードチャンク

2017年2月17日
https://kazutan.github.io/kazutanR/Rmd_intro.html
R Markdown入門 | Rチャンク(chunk)の基本 | Rチャンク オプション
- echo(コード部の表示・非表示)
- eval(コード部の評価・非評価)
- include(レポートに組み込むか否か)

----------
----------
## Compile Report

https://rmarkdown.rstudio.com/articles_report_from_r_script.html
Compiling Reports from R Scripts
|
If you are using RStudio then you can also create a report using the Compile Report command (Ctrl+Shift+K).

13 April 2020
http://www.dry-lab.org/blog/2020/easy-report-from-r-script.html
An easy way to transform your R script into a nice report – Blog of Andrés Aravena
|
clicking the Compile Report button

![http://www.dry-lab.org/blog/2020/easy-report-from-r-script.html](http://www.dry-lab.org/images/cmb2/R_compile_report.png)

Jan 17, 2017
https://www.youtube.com/watch?v=4xwaH9CR2TY
How to Compile a Report in RStudio - YouTube


2018/05/11
https://www.kyoritsu-pub.co.jp/book/b10003938.html
再現可能性のすゝめ
―RStudioによるデータ解析とレポート作成―
ためし読み
https://www.yondemill.jp/contents/53229?view=1
目次 | 4.8　Rスクリプトからレポート生成

![https://www.kyoritsu-pub.co.jp/book/b10003938.html](https://hondana-image.s3.amazonaws.com/book/image/10003938/normal_300fa3ec-db93-4420-a5ce-042046371dc0.jpg)

メディアセンター (https://www.lib.keio.ac.jp/sfc/) よりご利用いただけます。オンライン閲覧の場合、閲覧後は毎回右上の「閲覧終了」ボタンをクリックして、ほかの方に利用をお譲りください。
[再現可能性のすゝめ ―RStudioによるデータ解析とレポート作成―（Wonderful R 3）
東京: 共立出版, 2018.5.
2018.5
Wonderful R / 市川太祐 [ほか] 編

Maruzen eBook Library
](https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma9926579997904034)







https://kohske.github.io/R/rstudio/
Rstudioで楽々ドキュメント生成 | Rスクリプトからノートブックの作成

https://rpubs.com/kohske/595
Rスクリプトからレポート生成

2016年12月05日に更新
https://qiita.com/wakuteka/items/86b0ea5ef8428229babd
3. Compile Report

![https://qiita.com/wakuteka/items/86b0ea5ef8428229babd](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F12353%2Fdc0b5da6-c3fe-08b0-e0b4-0a8186f6f453.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&w=1400&fit=max&s=8ff668aa377d1baa3b329e36cf09ff30)

----------
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
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)
  - [my_datasciencedojo_r.R](https://github.com/haruosuz/r4bioinfo/blob/master/scripts/my_datasciencedojo_r.R)

[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

以下の動画レッスンを見て、疑問点を報告する。
- [R言語入門 (全13回) - プログラミングならドットインストール](http://dotinstall.com/lessons/basic_r)
  - [my_dotinstall_basic_r.R](https://github.com/haruosuz/r4bioinfo/blob/master/scripts/my_dotinstall_basic_r.R)


[回答例]
```
「R言語入門 (全13回)」の動画レッスン番号 #03 ~ #13 を見た。
疑問点は次の通りである。
1. 行列とデータフレームとリストの違いが理解できなかった。
2. 文字型ベクトルと因子型ベクトルの違いは？
```

----------

https://akiyoko.hatenablog.jp/entry/2014/11/07/042801
Windows で R（統計解析ツール）を使う - 
R の使い方を手っ取り早く理解するためにまず、ドットインストールの「R言語入門」（全13回）の動画をひと通り全部見てみました。
動画時間は全部で 35分ほど。
手を動かすのも合わせて、一時間ほどでチェックし終えることができました。

January 2017
https://r4ds.had.co.nz/
R for Data Science

https://www.r-project.org/help.html
R: Getting Help with R

----------

https://support.rstudio.com/hc/en-us/articles/200549016-Customizing-the-RStudio-IDE
Pane Layout

https://r4ds.had.co.nz/workflow-scripts.html
The script editor is a great place to put code you care about. Keep experimenting in the console, but once you have written code that works and does what you want, put it in the script editor.

https://www.uvm.edu/~rsingle/other/R-intro.pdf
Introductory Guide to R
|
1.4 R commands. Case sensitivity.
Technically R is a function language with a very simple syntax. It is case sensitive, so A and a are different variables.
|
2.2 Vectors and Assignments
It is useful to know that R discriminates, for the names of the objects, the upper-case characters from the lower-case
ones (i.e., it is case-sensitive), so that x and X can be used to name distinct objects (even under Windows).
```
a <- 1; A <- 10
ls()
A
a
```

----------
### R_DSD_10

Data Science Dojo [Control Statements: For Loop, If, Else - Introduction to R Programming - Part 10](https://www.youtube.com/watch?v=QEzWBLb9xa4&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=11)

```
> income$average.income
[1]  85000 112000  60000  68000  78000  82000  90000  72000  82000

> income.level
[1] "low-med" "high"    "low-med" "low-med" "low-med" "low-med" "high"    "low-med"
[9] "low-med"
```

The dollar sign `$` is used to specify a single variable (`average.income`) within a data frame (`income`).
`average.income` and `income.level` are variable/object names where lowercase words were separated with `.`.

References:
- https://r4ds.had.co.nz/workflow-basics.html#whats-in-a-name
Object names must start with a letter, and can only contain letters, numbers, `_` and `.`.
- https://www.r-bloggers.com/dataframes-and-the-tidyverse/
To specify a single variable within a data frame or tibble, use the dollar sign `$`. R has another way of doing this, using column numbers, but using the dollar sign will make it much easier to understand your code if someone else needs to use it, or if you come back to look at it months after writing it.

----------
### R_assignOps

[R: Assignment Operators](https://stat.ethz.ch/R-manual/R-devel/library/base/html/assignOps.html)
The operators <- and = assign into the environment in which they are evaluated. The operator <- can be used anywhere, whereas the operator = is only allowed at the top level (e.g., in the complete expression typed at the command prompt) or as one of the subexpressions in a braced list of expressions.

[What are the differences between "=" and "<-" assignment operators in R? - Stack Overflow](https://stackoverflow.com/questions/1741820/what-are-the-differences-between-and-assignment-operators-in-r)

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/28.html
28. 演算子
```
<<-	永続代入
<-，->	代入
=	代入
```

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/32.html
32. ローカル変数と永続代入<<-

----------
### R_built-in

https://www.statmethods.net/management/functions.html
Quick-R: Built-in Functions

https://study.com/academy/lesson/built-in-functions-in-r-programming.html
Built-In Functions in R Programming | Study.com

https://www.javatpoint.com/r-built-in-functions
R Built-in Functions - javatpoint

https://cran.r-project.org/doc/manuals/r-release/R-intro.html#Accessing-builtin-datasets
7.3 Accessing builtin datasets

----------
### R_data.frame

Data Science Dojo [Data Frames - Introduction to R Programming - Part 6](https://www.youtube.com/watch?v=ORbcLfYbvxs&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=6)

2022-03-10
https://cran.r-project.org/doc/manuals/R-lang.html#Data-frame-objects
2.3.2 Data frame objects
|
Data frames are the R structures which most closely mimic the SAS or SPSS data set, i.e. a “cases by variables” matrix of data.
A data frame is a list of vectors, factors, and/or matrices all having the same length (number of rows in the case of matrices). 

2020/03/21
https://www.cyberer.net/2020/03/r-lists-and-data-frames.html#toc_headline_8
CYBERer.NET: R - 入門本編 6章 リストとデータフレーム
|
「データフレーム」は関係データベースのテーブルのようなデータ構造だ。クラス data.frame を持つリストであるが、ただのリストに比べてコンポーネントになり得るオブジェクトにいくつかの制限が設けられている。

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
216 ■ 8 章 R 言語入門
|
データフレームから単一の列にアクセスするとき、R のデフォルトの動作は、これを 1 つの列を持つ データフレームとしてではなく、ベクトルとして返す。次に実行されるコードがデータフレームを入力 として期待している場合は問題となる。この動作を無効にするには、ブラケット演算子を使って引数 drop を FALSE に設定する。
```
> d[, "start", drop=FALSE]
```

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
202 | Chapter 8: A Rapid Introduction to the R Language
|
When accessing a single column from a dataframe, R’s default behavior is to return this as a vector—not a dataframe with one column. Sometimes this can cause problems if downstream code expects to work with a dataframe. To disable this behavior, we set the argument drop to FALSE in the bracket operator:
```
> d[, "start", drop=FALSE]
```

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html
39. データフレーム事始
|
データフレームとは data.frame クラスを持つリストのことであり，数値ベクトルや文字ベクトル，因子ベクトル（文字型ベクトル）などの異なる型のデータをまとめて1 つの変数として持っている．外見は行列と同じ 2 次元配列であるが，データフレームの各行・列はラベルを必ず持ち，ラベルによる操作が可能である点が普通の行列と異なる．しかも各列の要素の型はバラバラでも構わないので，ベクトルやリストで持っているデータをデータフレームに変換することで統計解析がやりやすくなる．

----------
### R_factor

Data Science Dojo [Using Factors - Introduction to R Programming - Part 8](https://www.youtube.com/watch?v=a_N6Q0O5T3s&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=8)

http://www.okadajp.org/RWiki/?因子Tips大全

https://r4ds.had.co.nz/data-import.html#readr-factors
11.3.3 Factors
|
R uses factors to represent categorical variables that have a known set of possible values. 

https://r4ds.had.co.nz/factors.html
15 Factors
|
In R, factors are used to work with categorical variables, variables that have a fixed and known set of possible values. They are also useful when you want to display character vectors in a non-alphabetical order.
Historically, factors were much easier to work with than characters. As a result, many of the functions in base R automatically convert characters to factors. 

https://r4ds.had.co.nz/vectors.html#factors-1
20.7.1 Factors
|
Factors are designed to represent categorical data that can take a fixed set of possible values. Factors are built on top of integers, and have a levels attribute:

http://monashbioinformaticsplatform.github.io/2015-09-28-rbioinformatics-intro-r/01-supp-factors.html
Factors are used to represent categorical data. Factors can be ordered or unordered and are an important class for statistical analysis and for plotting.
Factors are stored as integers, and have labels associated with these unique integers. While factors look (and often behave) like character vectors, they are actually integers under the hood, and you need to be careful when treating them like strings.

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 191
|
Factors and classes in R
|
Another kind of vector you’ll encounter are factors. Factors store categorical variables, such as a treatment group (e.g., “high,” “medium,” “low,” “control”), strand (forward or reverse), or chromosome (“chr1,” “chr2,” etc.).

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 205
|
8.2.3.2 R の因子とクラス 
|
他にも作業中に出会う可能性のあるベクトルに因子がある。因子はカテゴリーを表す変数を収めたベクトルである。たとえば処理群(「高」、「中」、「低」、「対照」など)、鎖(「正鎖」または「相補鎖」)、あるいは染色体(「chr1」、「chr2」など)である。

https://www.cyberer.net/2020/08/r-ordered-and-unordered-factors.html
CYBERer.NET: R - 入門本編 4章 順序付き因子と順序無し因子
|
因子 (factor) は、質的変数を R で表現する方法である。質的変数には、順序尺度と名義尺度があるが、R ではそれぞれに対して順序付き因子と順序無し因子が対応する。因子ではない数値ベクトルは、量的変数 (間隔尺度や比例尺度) とみなされる。R では順序無し因子、順序付き因子、因子ではない数値ベクトルは、モデル構築において異なる取り扱い (各尺度として適切な取り扱い) がされるようになっている。

2011/06/21 12:28
https://sites.google.com/site/webtextofr/edit
7. ベクトルデータの操作 - 統計ソフトRの使い方
|
データのタイプ（型）
|
Rには大きく４つのタイプのデータがあります．それは，(1)　数値型，(2) 文字列型，(3) 因子型，(4) 論理値型です．
|
因子型データは，例えば男性を”1”，女性を”2”として入力されたデータです．実際に入力する際には，まず数値として普通にベクトルを作ったあとで，関数as.factor( )を使うことによって，因子型に変換します．こうして作った”1”, “2”はもはや数値としての意味を持ちません．単に「男」「女」を表す記号となったわけです．
|
いわゆるカテゴリカルデータ（質的データ）は，Rでは因子型データとして扱います．

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/16.html
16. 種々のベクトル
|
順序つき因子ベクトルと順序無し因子ベクトル
|
関数 factor() を用いることで，カテゴリーを要素としたベクトルを作成することが出来る．関数 levels() でグループ化されているかを確認することが出来，関数 str() でオブジェクトの要約値を表示することが出来る．
結果を見ると，要素の順序が勝手に入れ替わっていることが分かる．明示的に順序を指定する場合は，引数 levels に順序を指定すれば良い．
関数 factor() では因子間に大小関係は無かったが，関数 ordered() で順序付きの因子ベクトルが作成出来る．

2020-04-24
https://stat.ethz.ch/pipermail/r-announce/2020/000653.html
R 4.0.0 is released

https://stat.ethz.ch/R-manual/R-devel/doc/html/NEWS.html
CHANGES IN R 4.0.0
|
R now uses a ‘⁠stringsAsFactors = FALSE⁠’ default, and hence by default no longer converts strings to factors in calls to data.frame() and read.table().

----------
### R_indexing

https://cran.r-project.org/doc/manuals/R-lang.html#Indexing
3.4 Indexing
|
R contains several constructs which allow access to individual elements or subsets through indexing operations. 

http://www.intro2r.info/unit2/subsetting-and-indexing.html
Subsetting and Indexing
|
Subsetting in R is fast and incredibly powerful.
There are three subsetting operators: [, [[, $.

une 27th, 2020
https://www.datacamp.com/community/tutorials/subsets-in-r
R Subsetting: How to Subset & Select DataFrame Rows & Columns in R - DataCamp

https://www.r-bloggers.com/2017/02/dataframes-and-the-tidyverse/
To specify a single variable within a data frame or tibble, use the dollar sign $. R has another way of doing this, using column numbers, but using the dollar sign will make it much easier to understand your code if someone else needs to use it, or if you come back to look at it months after writing it.

https://r4ds.had.co.nz/transform.html#select
5 Data transformation
|
5.4 Select columns with select()

https://r4ds.had.co.nz/tibbles.html#subsetting
10 Tibbles
|
10.3.2 Subsetting
|
So far all the tools you’ve learned have worked with complete data frames. If you want to pull out a single variable, you need some new tools, $ and [[. [[ can extract by name or position; $ only extracts by name but is a little less typing.

2013-11-19
https://stats.idre.ucla.edu/r/modules/subsetting-data/
Subsetting Data | R Learning Modules

https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/installr.html#a-brief-introduction-to-r
index

----------
### R_list

http://www.okadajp.org/RWiki/?リストTips大全

https://jennybc.github.io/purrr-tutorial/bk00_vectors-and-lists.html
A list is actually still a vector in R, but it’s not an atomic vector.

2018年4月16日
https://blog.sgnet.co.jp/2018/04/r-vectorlist.html
[R] vectorとlistの関係
|
ただし、ただ"vector"と言った場合は"atomic vector"、"list"と言った場合は"generic vector"を指しているみたい。

2012-09-21
http://takenaka-akio.org/doc/r_auto/list.html
リストにオブジェクトをしまう
|
ベクトルは、同じ型のデータをまとめて並べたデータ構造です。 これに対し、リストはどのような型のデータでもしまえるデータ構造です。 ベクトルでもリスト自身でもデータフレームでも統計解析関数が返す複雑なオブジェクトでも、なんでも格納できます。 自動化した処理の結果をいくつもまとめておいて、最後にまとめて処理したいなどという場合にも便利でしょう。 なお、データフレームもリストの一種です。
リストの要素の指定
リストの要素は、[　] や [[ ]] に要素の位置を与えて指定できます。 [　]を使った場合は「指定した要素を含むリスト」、 [[ ]]を使った場合は「要素そのもの」を指すことに注意が必要です。
[　] や [[ ]]、$ による要素の指定方法は、 データフレームの場合と同様ですね。 これはデータフレーム自体がリスト（の一種）なので当然です（ is.list(data.frame()) は TRUE を返す）。

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html
23. リスト
|
R にはデータの種類としてベクトルや行列，配列などが用意されている（ 1 や 'a' も長さ 1 のベクトル）が，リストはこれら異なる構造のデータを集めて 1 個のオブジェクトにしたものである．異なった型のベクトルを 1 個のリストにまとめてもよいし，リストの要素としてリストを用いても構わない．
```
コマンド	機能
x[1]	x の第 1 成分を取り出す（中身はリスト）
x[[1]]	x の第 1 成分を取り出す（中身はリスト中の要素）
```
 リスト要素へのアクセス
上記のように，[[ と ]] の間に要素の番号を指定することによって，リストの要素を取り出すことが出来る．[ と ] の間に要素の番号を指定することでもリストの要素を取り出すことは出来るが，この場合はベクトルとしてアクセスを行っていることになる．よって，要素を取り出したいのではなくてリストの一部分を抽出する場合は，ベクトルの場合と同様，[ と ] を使えばよい．ただし返り値はリストとなる．

----------
### R_matrix

R-Tips [20. 行列計算](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/20.html)
 行列の積は %*% 演算子によって求める点に注意．行列に対して * 演算子を用いると要素毎の積を計算してしまう．

[行列 | R による行列の演算](https://stats.biopapyrus.jp/r/basic/matrix.html)
行列の計算

[Rでのデータの演算と操作](https://www.cis.doshisha.ac.jp/mjin/R/03.html)
3．行列の演算
(2)行列の乗算
　行列の乗算には、算術演算のように対応する行列の要素の間に乗算を行う演算と線形代数で定義されている積演算がある。
Rでは、コマンド％*％で行列の積演算を行う。
(3)単位行列と逆行列

----------
### R_object

[A brief introduction to R](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/installr.html#a-brief-introduction-to-r)
All variables (scalars, vectors, matrices, etc.) created by R are called objects.

[05. オブジェクトと代入（付値）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/05.html)
R が作ったり操作した実体はオブジェクト（object）と呼ばれる．変数，数の配列，文字列関数，データ，関数その他全てがそれにあたる．

----------
### R_operator

https://cran.r-project.org/doc/manuals/R-lang.html#Operators
3.1.4 Operators

https://www.ucl.ac.uk/~uctqiax/PUBLG100/2015/faq/operators.html
Operators in R | Introduction to Quantitative Methods

|Operator|Description|
|:---------|:---------|
|( )|Round brackets (also known as "parenthesis") are used primarily when calling a function in R.|
|[ ]|The square brackets are used for indexing into a vector, matrix, array, list or dataframe.|

https://www.statmethods.net/management/operators.html
Quick-R: Operators
|
Arithmetic Operators
|
Logical Operators
```
# An example
x <- c(1:10)
x[(x>8) | (x<5)]
```

https://stat.ethz.ch/R-manual/R-devel/library/base/html/Logic.html
Logical Operators


http://cse.naro.affrc.go.jp/takezawa/r-tips/r/28.html
28. 演算子
|
演算子一覧
|
$ と [[ ]] は主にリストの要素にアクセスする場合（例：mylist$element , mylist[[1]] ）に用いられ，[ ] は主にベクトルの要素にアクセスする場合（例 ： x[2] ）に用いられる．

|演算子|機能|
|:---------|:---------|
|$|リストの要素にアクセスする場合|
|[ ，[[|データの一部分，要素，（ [ → ベクトルの要素にアクセス，[[  → リストの要素にアクセス）|


http://cse.naro.affrc.go.jp/takezawa/r-tips/r/42.html
42. データへのアクセス方法
|
このデータフレーム x にアクセスする方法を紹介する．

|コマンド|機能|
|:---------|:---------|
|x$列名，x["列名"]，x[["列名"]]|列データ（例えば SEX や WEIGHT ）にアクセスする．|

----------
### R_options

https://stat.ethz.ch/R-manual/R-devel/library/base/html/options.html
R: Options Settings

https://www.burns-stat.com/the-options-mechanism-in-r/
The digits option controls how many digits are printed (by default):
The default value is 7.  We can change it:

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 179
|
Significant Digits, print(), and Options in R
|
By default, R will print seven significant digits

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 193
|
有効桁、print()、R のオプション
|
デフォルトでは、R は 7 桁の有効桁を表示する

```
sqrt(3.5)
print(sqrt(3.5), digits=10)
getOption('digits')
options(digits=9)
help(options)
```

----------
### R_plot

https://dotinstall.com/lessons/basic_r/28113
#13 グラフを描いてみよう | R言語入門 - プログラミングならドットインストール

R-Tips [67. 相関係数と無相関検定](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/67.html)
```
 cor(x, y, method="spearman")          # 単なる相関係数
 cor.test(x, y, method="pearson")      # 無相関かどうかの検定
```

----------
### R_quit

奥村 晴彦
Last modified: 2019-04-22 14:21:33
https://oku.edu.mie-u.ac.jp/~okumura/stat/first.html
Rの初歩
|
終了のしかた
|
終了するには，［閉じる］ボタンをクリックします。または，Rのコンソールに
`> q()`
と打ち込むのが伝統的な方法です。q はquit（終わる）の頭文字です。すると，標準的な設定では，
`作業スペースを保存しますか？`
または
`Save workspace image? [y/n/c]:`
と聞いてきますので，作業スペース（現在の状態）を保存して終了するなら y（はい），保存しないで終了するなら n（いいえ），終了をキャンセルする（終了しない）なら c（キャンセル）と答えます。通常は n（いいえ）と答えます。

----------
### R_quotes

https://stat.ethz.ch/R-manual/R-devel/library/base/html/Quotes.html
Single and double quotes delimit character constants. They can be used interchangeably but double quotes are preferred (and character constants are printed using double quotes), so single quotes are normally only used to delimit character constants containing double quotes.

https://stackoverflow.com/questions/20572436/are-double-and-single-quotes-always-interchangeable-in-r
Are double "" and single '' quotes (always) interchangeable in R? - Stack Overflow

----------
### R_read.table

https://stat.ethz.ch/R-manual/R-devel/library/utils/html/read.table.html
Data Input

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
Working with and Visualizing Data in R | 195
|
Large Genomics Data into R: colClasses, Compression, and More
|
data.table package
fread() function

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.3 R でのデータの扱いとその可視化 ■ 209
|
大規模なゲノムデータを R に読み込む: colClasses とデータ圧縮
|
data.table パッケージ
fread() 関数

```
> d <- read.csv("Dataset_S1.txt")
```

https://heavywatal.github.io/rstats/readr.html
readr: 高速で柔軟なテーブル読み込み - Heavy Watal

2020.02.01
https://stats.biopapyrus.jp/r/tidyverse/readr.html
readr | readr パッケージによるデータの読み込みと書き出し、文字列パース


Data Science Dojo [Read and Write Data - Introduction to R Programming - Part 5](https://www.youtube.com/watch?v=vbVRhr8qexQ&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=6)
https://youtu.be/vbVRhr8qexQ?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&t=105

https://r4ds.had.co.nz/workflow-projects.html#paths-and-directories
8.3 Paths and directories
|
Paths and directories are a little complicated because there are two basic styles of paths: Mac/Linux and Windows.

https://so-zou.jp/robot/tech/numerical-analysis/r/file/#no3
パスの区切り
```
Windowsではパスの区切りにバックスラッシュ (\) を用いますが、それをそのまま文字定数に含めると

> a <-read.table("dir\sample.txt")
エラー:  ""dir\s" で始まる文字列の中で '\s' は文字列で認識されないエスケープです

のようなエラーとなります。よってバックスラッシュをバックスラッシュでエスケープして (\\) と記述するか、スラッシュ (/) に置き換えます。
```

2018/09/28
https://opur.club/post/2018/09/28/about-paths/
Path（パス）
|
Mac や Linux と共通の表記になりますので，スラッシュを使用することを推奨します。
```
C:/Users/username/Documents/rclub.R
```


https://darumalab.github.io/bootcamp/2017-07-14-import/
R言語 データの読み込み- R Importing Data
|
日本語のファイルを読み込む時にエラーが発生する場合
```
dat1 <- read.table(file = file.choose(), header = TRUE, sep = ",", 
    fileEncoding = "CP932")
```

2021-01-25
[第23章 Rのエンコーディング問題 | Rで計量政治学入門](https://shohei-doi.github.io/quant_polisci/encoding-r.html)
23.1 なぜ文字化けが起こるのか
|
23.1.1 エンコーディング
|
実用上、日本語で文字化けが起こる問題の大半は
WindowsではShift-JISあるいはCP932で、
LinuxやMacなどのUNIX系ではUTF-8で
エンコーディングしていることに起因しています。

2018-01-25 [RでCSVファイルの入出力（CP932文字コード指定など） | kitamix](https://kitamix.net/archives/save-cdv-file-in-r/1096)

2015-08-23
[文字化けこわい、こわくない？ - cucumber flesh](https://uribo.hatenablog.com/entry/2015/08/23/004222)
日本語エンコーディング表形式のファイル
|
WindowsとMac（UNIX）でエンコードが異なるので注意が必要。大抵の場合、ファイルの出処がWindowsならcp932（いわゆるSJIS）、MacならUTF8を引数fileEncodingで指定すれば大丈夫。

----------
### R_typeof

[R Language Definition](https://cran.r-project.org/doc/manuals/R-lang.html#Objects)
2 Objects
|
R objects are often coerced to different types during computations. There are also many functions available to perform explicit coercion.

[Data Types and Structures – Programming with R](https://swcarpentry.github.io/r-novice-inflammation/13-supp-data-structures/)


https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 191
|
Type Coercion in R
|
Because all elements in a vector must have homogeneous data type, R will silently coerce elements so that they have the same type.

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 205
|
R における型の強制変換
|
ベクトルのすべての要素は均一のデータ型でなければならないため、R は同じ型を持つよ うに要素の型変換を強制する。

[R の強制型変換と NA の取り扱い - 株式会社ホクソエムのブログ](https://blog.hoxo-m.com/entry/2017/04/24/000000)
強制型変換
R のベクトルは、1つだけしか型を持つことができません。1
したがって、異なる型の要素を結合してベクトルを作成しようとすると、型を統一するために、型の自動変換が行われます。これが強制型変換です。
強制型変換にはルールがあります。結合しようとする要素の型の中で、最も柔軟性の高い型に変換されます。
型の柔軟性は次の通りです。
```
logical < integer < double < complex < character
(論理値型 < 整数型 < 倍精度小数点型 < 複素数型 < 文字列型)
```

----------
### R_vector

Data Science Dojo [Working with Vectors - Introduction to R Programming - Part 7](https://www.youtube.com/watch?v=h6Mrzjrkycs&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=7)

https://r4ds.had.co.nz/vectors.html
20 Vectors | R for Data Science

2017.06.13
https://stats.biopapyrus.jp/r/basic/vector.html
ベクトル | R のベクトル操作と演算
|
R のベクトルは、数学のベクトルとほぼ同じ概念である。数学では 1 つのベクトルに複数の要素を含めると同様に、R では 1 つのベクトルに複数の値を代入できる。

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/16.html
16. 種々のベクトル
|
論理型ベクトル
|
論理値を要素とするベクトルを論理型ベクトルと呼ぶ．正式名（TRUE，FALSE）でも略記名（T，F）でも指定できる．論理型ベクトルに対する論理演算子として，& (論理積) ， | (論理和) ，! (否定) ，xor (排他的論理和) があり，これらを用いると要素毎の演算を行なう．

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/14.html
14. ベクトル計算
|
ベクトルを集合と見立てて集合演算を行うことも出来る．
```
union(x, y)	和集合
intersect(x, y)	積集合
setdiff(x, y)	差集合
```

----------
## assignment 2
**課題No.2 「Installing R packages」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

Rパッケージのインストール:  
```
# Installing the R packages:
install.packages("seqinr")
install.packages("zoo")
install.packages("ape")
install.packages("phangorn")
install.packages("tidyverse")
```

Bioconductorパッケージのインストール:  
```
# Installing the Bioconductor packages:
if (!requireNamespace("BiocManager", quietly = TRUE))
  install.packages("BiocManager")

BiocManager::install("Biostrings")
BiocManager::install("msa")
BiocManager::install("DECIPHER")
```

[Update all/some/none? [a/s/n]: と聞かれることもありますが基本はnでいいです。](http://www.iu.a.u-tokyo.ac.jp/~kadota/bioinfo_ngs_sokushu_2014/R_install.pdf)
[At any point (especially if you’ve used R/Bioconductor in the past), R may ask you if you want to update any old packages by asking Update all/some/none? [a/s/n]:. If you see this, type](http://bioconnector.github.io/bims8382/setup-r.html)
`n`

Rパッケージのバージョンを確認:  
```
# Print the versions of these packages:
packageVersion("seqinr")
packageVersion("zoo")
packageVersion("ape")
packageVersion("phangorn")
packageVersion("tidyverse")

packageVersion("Biostrings")
packageVersion("msa")
packageVersion("DECIPHER")
```

Rパッケージの呼び出し:  
```
# Load the packages into R:
library(seqinr)
library(zoo)
library(ape)
library(phangorn)
library(tidyverse)

suppressMessages(library(Biostrings))
library(msa)
library(DECIPHER)
```

Rのバージョンを確認:  
```
# Print the version of R running:
R.version.string

# Print version information about R, the OS and attached or loaded packages.
sessionInfo()
```

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
[NCBI](https://integbio.jp/dbcatalog/record/nbdc00584)
[国立生物工学情報センター](https://ja.wikipedia.org/wiki/国立生物工学情報センター)
の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

- NCBIのウェブサイトからゲノム配列データを取得する。
  - ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。
例えば、[ハンセン病（Leprosy）](https://ja.wikipedia.org/wiki/ハンセン病)の原因となる細菌 [らい菌](https://ja.wikipedia.org/wiki/らい菌) "Mycobacterium leprae" を検索する。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Mycobacterium%20leprae)、検索ボックス下の「Overview(1); Prokaryotes(6)」のうち、「Prokaryotes」をクリックすると、*Mycobacterium leprae*に属する菌株**Strain**が表示される。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Mycobacterium%20leprae)、列**Organism Name**の"Mycobacterium leprae TN"株をクリックして開く。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/903?genome_assembly_id=169891)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に[アクセッション番号](https://www.ddbj.nig.ac.jp/acc_def.html)が示されている。
アクセッション番号は、"NC_002677.1" (RefSeq) と "AL450380.1" (INSDC) 。

- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for [*Mycobacterium leprae*](https://en.wikipedia.org/wiki/Mycobacterium_leprae), a bacterium that causes leprosy, you would type just Organism name "Mycobacterium leprae" in the search box and press "Search".
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Mycobacterium%20leprae), you will see the number of hits to "Mycobacterium leprae" in each of the NCBI databases: "Overview(1); Prokaryotes(6)". When you click on "Prokaryotes", it will show all the strains belonging to the species.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Mycobacterium%20leprae), When you click on the Organism Name "Mycobacterium leprae TN", it will bring you to the record for this organism in the NCBI Genome database.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/903?genome_assembly_id=169891), you will see the "Summary", "Publications", and "Replicon Info" of the Organism. 
The NCBI [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the DNA sequences are "NC_002677.1" (RefSeq) and "AL450380.1" (INSDC), respectively.

NCBIからDNA配列を取得する:  
```
# Retrieving a DNA sequence from NCBI
library(seqinr)
ACCESSION <- "NC_001477" # Dengue virus 1
#ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
#ACCESSION <- "NC_001318" # Borreliella burgdorferi B31 chromosome
filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
#filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 3
**課題No.3 「DNA Sequence Statistics (1)」**

[Exercises](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises) |
[Answers to the exercises on DNA Sequence Statistics (1)](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#dna-sequence-statistics-1)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.
You can submit your assignment as a PDF/HTML document, created from R script, R Markdown, Jupyter Notebook, etc..

Q1. What are the last twenty nucleotides of the genome sequence?

    tail(seq1, 20)

Q2. What is the length in nucleotides of the genome sequence?

    length(seq1)

Q3. How many of each of the four nucleotides A, C, T and G, and any other symbols, are there in the genome sequence?

    table(seq1)

[Codes Used in Sequence Description](https://www.ddbj.nig.ac.jp/ddbj/code-e.html)
[配列の記載に用いる略号](https://www.ddbj.nig.ac.jp/ddbj/code.html)

Q4. What is the GC content of the genome sequence, when (i) all non-A/C/T/G nucleotides are included, (ii) non-A/C/T/G nucleotides are discarded?

	help("GC")
    GC(seq1)
    GC(seq1, exact=FALSE)
    GC(seq1, exact=TRUE)

Q5. How many of each of the four nucleotides A, C, T and G are there in the complement of the genome sequence?

	#help.search("complement")
	#help("comp")
    table(comp(seq1))

- Mar 14, 2018 [Practice writing the complementary strand of DNA and mRNA during transcription - YouTube](https://www.youtube.com/watch?v=9qyi6xgOjEk)

<img alt="" src="https://i.ytimg.com/vi/9qyi6xgOjEk/maxresdefault.jpg" width=35%>

Q6. How many occurrences of the DNA words CC, CG and GC occur in the genome sequence?

    count(seq=seq1, wordsize=2)

Q7. How many occurrences of the DNA words CC, CG and GC occur in the (i) first 1000 and (ii) last 1000 nucleotides of the genome sequence?
How can you check that the subsequence that you have looked at is 1000 nucleotides long?

    count(seq=head(seq1, 1000), wordsize=2)
    count(seq=tail(seq1, 1000), wordsize=2)

----------
----------
## assignment 4
**課題No.4 「DNA Sequence Statistics (2)」**

[Exercises](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises) |
[Answers to the exercises on DNA Sequence Statistics (2)](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#dna-sequence-statistics-2)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Draw a sliding window plot of GC content in the genome sequence, using different window sizes; e.g. 200 and 2000 nucleotides. 
Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# write a function to make a sliding window plot:
    slidingwindowplotGC <- function(windowsize, inputseq)
    {
      # this function requires the 'zoo' R package #install.packages("zoo")
      require("zoo")
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = GC)
      plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")
    }

	# make a sliding window plot with a window size of 200 nucleotides:
    slidingwindowplotGC(windowsize = 200, inputseq = seq1)

	# make a sliding window plot of GC content using a window size of 2000 nucleotides:
    slidingwindowplotGC(windowsize = 2000, inputseq = seq1)

Q2. Write a function to calculate the AT content of a DNA sequence (ie. the fraction of the nucleotides in the sequence that are As or Ts). What is the AT content of the genome?

	# Here is a function to calculate the AT content of a genome sequence:
    AT <- function(x){ library("seqinr"); 1 - GC(x) }

    # use the function to calculate the AT content of the genome:
    AT(seq1)

    # AT = 1 - GC, ie. (AT + GC = 1):
    GC(seq1)
    AT(seq1) + GC(seq1)

Q3. Write a function to draw a sliding window plot of AT content.

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

Q4. Is the 3-nucleotide word GAC over-represented or under-represented in the genome sequence?

	# calculate Rho for words of length 3 in the genome
	rho(sequence = seq1, wordsize=3)

    # rho > 1: over-represented
    # rho < 1: under-represented

[Sliding windowでゲノムの局所的な塩基組成（GC content, GC skew）を解析する](https://github.com/haruosuz/DS4GD/blob/master/2018giga/CaseStudy.md#dna-sequence-statistics-2)

----------
## assignment 8
**課題No.8 「dotplot」**

ドットプロットで2つの配列を比較
[Comparing two sequences using a dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)

Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Download FASTA-format files of two protein sequences from UniProt.
```
library(seqinr)
seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q9CD83.fasta")[[1]]; length(seq1); getAnnot(seq1)
seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/A0PQ23.fasta")[[1]]; length(seq2); getAnnot(seq2)
```

Q2. Create a dotplot for two sequences.
```
par(mfrow=c(2,2))
dotPlot(seq1, seq2)
dotPlot(seq1, seq2, wsize = 2, wstep = 2, nmatch = 2)
```

Q3. Create a self-similarity dot-plot; i.e. Comparing the sequence against itself.
```
dotPlot(seq1, seq1)
dotPlot(seq2, seq2)
```

https://github.com/haruosuz/bioinfo/blob/master/references/README.bioinfo.tools.md#dotplot

----------
## assignment 9
**課題No.9 「Pairwise Sequence Alignment」**

[Exercises](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises) |
[Answers to the exercises on Sequence Alignment](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#sequence-alignment)

Answer the following questions. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Download FASTA-format files of two protein sequences of interest from UniProt.
```
library(seqinr)
seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q9CD83.fasta")[[1]]; length(seq1); getAnnot(seq1)
seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/A0PQ23.fasta")[[1]]; length(seq2); getAnnot(seq2)
s1 <- toupper(c2s(seq1)) # convert the sequence to a string and to uppercase
s2 <- toupper(c2s(seq2)) # convert the sequence to a string and to uppercase
```

Q2. What is the alignment score for the optimal global alignment between the two proteins, when you use the BLOSUM50 scoring matrix?
(set gapOpening = -9.5 and gapExtension = -0.5)

	library("Biostrings") # load the Biostrings package
	data(BLOSUM50) # load the BLOSUM50 scoring matrix
    myglobalAlign <- pairwiseAlignment(s1, s2, substitutionMatrix = "BLOSUM50",
                      gapOpening = -9.5, gapExtension = -0.5) # align the two sequences
	myglobalAlign

Q3. Use the writePairwiseAlignments() function to view the optimal global alignment.

    writePairwiseAlignments(myglobalAlign)

Q4. What global alignment score do you get for the two proteins, when you use the BLOSUM62 alignment matrix?

	data(BLOSUM62) # load the BLOSUM62 scoring matrix
    myglobalAlign2 <- pairwiseAlignment(s1, s2, substitutionMatrix = "BLOSUM62",
                       gapOpening = -9.5, gapExtension = -0.5) # align the two sequences
	myglobalAlign2
    writePairwiseAlignments(myglobalAlign2)

Q5. What is the alignment score for the optimal local alignment between the two proteins?

    mylocalAlign <- pairwiseAlignment(s1, s2, substitutionMatrix = "BLOSUM50",
                     gapOpening = -9.5, gapExtension = -0.5, type="local")
	mylocalAlign
    writePairwiseAlignments(mylocalAlign)

----------
## assignment 10
**課題No.10 「Multiple Alignment and Phylogenetic Trees」**

[Exercises](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter5.html#exercises) |
[Answers to the exercises on Multiple Alignment and Phylogenetic Trees](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#multiple-alignment-and-phylogenetic-trees)

Answer the following questions. For each question, please record your answer, and what you typed into R to get this answer.

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
myAlignment
#print(myAlignment, show="complete")

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
## assignment 11
**課題No.11 「draft report」**

Integrate and modify your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it as a PDF/HTML document.

これまでの課題（興味あるDNA/タンパク質の配列を解析した結果など）を統合・修正してレポートのドラフトを作成し、PDF/HTML形式ファイルで提出する。

----------
## Class Survey
**授業調査**

We are writing to inform you that the period for students to fill out the “Semester-End General Class Survey” for Spring semester classes has begun.

■Schedule (2020 Spring semester)

Survey Period 	               Thurseday, July 9, 10 a.m.～ Friday, July 26, 11 p.m.

Questions regarding classes can be accessed by clicking on【授業調査】(Class Survey) after logging on to SFC-SFS
(https://vu.sfc.keio.ac.jp//sfc-sfs/).

春学期の授業について「学期終わりの全体調査」の学生作業期間を開始いたしましたので、お知らせします。

■　実施期間（2020年度春学期）

　調査実施期間（学生作業期間）7月 9日（木）10時～7月26日（日）23時

授業に関する設問については、SFC-SFSにログイン後、「授業調査」の
リンクからご確認いただけます。
https://vu.sfc.keio.ac.jp//sfc-sfs/

----------
