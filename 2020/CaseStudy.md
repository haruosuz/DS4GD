**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2020)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「Introduction to R」
- [Compile Report](#compile-report)
- [Chunk options](#chunk-options)
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages」
- [NCBI Taxonomy](#ncbi-taxonomy)
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [BLAST](#blast)
  - [NCBI BLAST](#ncbi-blast)
  - [UniProt BLAST](#uniprot-blast)
- [assignment 8](#assignment-8) 課題No.8 「dotplot」
- [assignment 9](#assignment-9) 課題No.9 「Pairwise Sequence Alignment」
- [assignment 10](#assignment-10) 課題No.10 「Multiple Alignment and Phylogenetic Trees」
- [assignment 11](#assignment-11) 課題No.11 「draft report」
- [Class Survey](#class-survey) 授業調査

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
[Control Statements: For Loop, If, Else - Introduction to R Programming - Part 10](https://www.youtube.com/watch?v=QEzWBLb9xa4&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=10)

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
Object names must start with a letter, and can only contain letters, numbers, _ and ..
- https://www.r-bloggers.com/dataframes-and-the-tidyverse/
To specify a single variable within a data frame or tibble, use the dollar sign $. R has another way of doing this, using column numbers, but using the dollar sign will make it much easier to understand your code if someone else needs to use it, or if you come back to look at it months after writing it.

----------
https://akiyoko.hatenablog.jp/entry/2014/11/07/042801
Windows で R（統計解析ツール）を使う - 
R の使い方を手っ取り早く理解するためにまず、ドットインストールの「R言語入門」（全13回）の動画をひと通り全部見てみました。
動画時間は全部で 35分ほど。
手を動かすのも合わせて、一時間ほどでチェックし終えることができました。

----------
https://dotinstall.com/lessons/basic_r/28106
#06 ベクトルの演算をしてみよう | R言語入門 - プログラミングならドットインストール

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/14.html
14. ベクトル計算
ベクトルを集合と見立てて集合演算を行うことも出来る．
```
union(x, y)	和集合
intersect(x, y)	積集合
setdiff(x, y)	差集合
```

----------
https://dotinstall.com/lessons/basic_r/28107
#07 因子ベクトルを使ってみよう | R言語入門 - プログラミングならドットインストール

http://www.okadajp.org/RWiki/?因子Tips大全

https://sites.google.com/site/webtextofr/edit
7. ベクトルデータの操作 - 統計ソフトRの使い方
Rには大きく４つのタイプのデータがあります．それは，(1)　数値型，(2) 文字列型，(3) 因子型，(4) 論理値型です．
因子型データは，例えば男性を”1”，女性を”2”として入力されたデータです．
いわゆるカテゴリカルデータ（質的データ）は，Rでは因子型データとして扱います．

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/16.html
16. 種々のベクトル
文字型ベクトル
順序つき因子ベクトルと順序無し因子ベクトル
関数 factor() を用いることで，カテゴリーを要素としたベクトルを作成することが出来る．関数 levels() でグループ化されているかを確認することが出来，関数 str() でオブジェクトの要約値を表示することが出来る．
結果を見ると，要素の順序が勝手に入れ替わっていることが分かる．明示的に順序を指定する場合は，引数 levels に順序を指定すれば良い．
関数 factor() では因子間に大小関係は無かったが，関数 ordered() で順序付きの因子ベクトルが作成出来る．

https://sites.google.com/site/leihcrev/r/ordered-and-unordered-factors
入門本編 4章 順序付き因子と順序無し因子
「因子 (factor)」とは、ベクトルの一種で、同じ要素数を持つ別のベクトルの要素のカテゴリ化を行うもの。「順序付き因子 (ordered factor)」と「順序無し因子 (unordered factor)」がある。主にモデル式で効果を発揮する。
順序付き因子を適用したデータは、尺度水準が順序尺度であることを示す。順序無し因子を適用すれば名義尺度にあたる。因子を付加していない数値ベクトルは、間隔尺度以上の高水準の尺度ということになる。順序付き因子と順序無し因子は、モデルへの当てはめなどで異なった振舞いを示す。

----------
https://dotinstall.com/lessons/basic_r/28110
#10 リストを扱ってみよう | R言語入門 - プログラミングならドットインストール

http://www.okadajp.org/RWiki/?リストTips大全

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html
23. リスト
R にはデータの種類としてベクトルや行列，配列などが用意されている（ 1 や 'a' も長さ 1 のベクトル）が，リストはこれら異なる構造のデータを集めて 1 個のオブジェクトにしたものである．異なった型のベクトルを 1 個のリストにまとめてもよいし，リストの要素としてリストを用いても構わない．
```
コマンド	機能
x[1]	x の第 1 成分を取り出す（中身はリスト）
x[[1]]	x の第 1 成分を取り出す（中身はリスト中の要素）
```
 リスト要素へのアクセス
上記のように，[[ と ]] の間に要素の番号を指定することによって，リストの要素を取り出すことが出来る．[ と ] の間に要素の番号を指定することでもリストの要素を取り出すことは出来るが，この場合はベクトルとしてアクセスを行っていることになる．よって，要素を取り出したいのではなくてリストの一部分を抽出する場合は，ベクトルの場合と同様，[ と ] を使えばよい．ただし返り値はリストとなる．

http://takenaka-akio.org/doc/r_auto/list.html
リストにオブジェクトをしまう
ベクトルは、同じ型のデータをまとめて並べたデータ構造です。 これに対し、リストはどのような型のデータでもしまえるデータ構造です。 ベクトルでもリスト自身でもデータフレームでも統計解析関数が返す複雑なオブジェクトでも、なんでも格納できます。 自動化した処理の結果をいくつもまとめておいて、最後にまとめて処理したいなどという場合にも便利でしょう。 なお、データフレームもリストの一種です。
リストの要素の指定
リストの要素は、[　] や [[ ]] に要素の位置を与えて指定できます。 [　]を使った場合は「指定した要素を含むリスト」、 [[ ]]を使った場合は「要素そのもの」を指すことに注意が必要です。
[　] や [[ ]]、$ による要素の指定方法は、 データフレームの場合と同様ですね。 これはデータフレーム自体がリスト（の一種）なので当然です（ is.list(data.frame()) は TRUE を返す）。

----------
https://dotinstall.com/lessons/basic_r/28111
#11 データフレームを扱ってみよう | R言語入門 - プログラミングならドットインストール

https://www.cyberer.net/2020/03/r-lists-and-data-frames.html#toc_headline_8
「データフレーム」は関係データベースのテーブルのようなデータ構造だ。クラス data.frame を持つリストであるが、ただのリストに比べてコンポーネントになり得るオブジェクトにいくつかの制限が設けられている。

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html
39. データフレーム事始
データフレームとは data.frame クラスを持つリストのことであり，数値ベクトルや文字ベクトル，因子ベクトル（文字型ベクトル）などの異なる型のデータをまとめて1 つの変数として持っている．外見は行列と同じ 2 次元配列であるが，データフレームの各行・列はラベルを必ず持ち，ラベルによる操作が可能である点が普通の行列と異なる．しかも各列の要素の型はバラバラでも構わないので，ベクトルやリストで持っているデータをデータフレームに変換することで統計解析がやりやすくなる．

----------
https://dotinstall.com/lessons/basic_r/28113
#13 グラフを描いてみよう | R言語入門 - プログラミングならドットインストール

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/67.html
67. 相関係数と無相関検定
```
 cor(x, y, method="spearman")          # 単なる相関係数
 cor.test(x, y, method="pearson")      # 無相関かどうかの検定
```

----------
----------
## Compile Report

https://rmarkdown.rstudio.com/articles_report_from_r_script.html
Compiling Reports from R Scripts

If you are using RStudio then you can also create a report using the Compile Report command (Ctrl+Shift+K).

Jan 17, 2017
https://www.youtube.com/watch?v=4xwaH9CR2TY
How to Compile a Report in RStudio - YouTube

2016年12月05日に更新
https://qiita.com/wakuteka/items/86b0ea5ef8428229babd
3. Compile Report

![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F12353%2Fdc0b5da6-c3fe-08b0-e0b4-0a8186f6f453.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&w=1400&fit=max&s=8ff668aa377d1baa3b329e36cf09ff30)

[再現可能性のすゝめ ―RStudioによるデータ解析とレポート作成― / 高橋 康介　著](http://www.kyoritsu-pub.co.jp/bookdetail/9784320112438) |
[4.8 R スクリプトからレポート生成](https://www.kyoritsu-pub.co.jp/app/file/goods_contents/3028.pdf)

![](https://www.kyoritsu-pub.co.jp/app/img/item/9784320112438.jpg)

メディアセンター (https://www.lib.keio.ac.jp/sfc/) よりご利用いただけます。オンライン閲覧の場合、閲覧後は毎回右上の「閲覧終了」ボタンをクリックして、ほかの方に利用をお譲りください。

- [Rstudioで楽々ドキュメント生成](https://kohske.github.io/R/rstudio/) Rスクリプトからノートブックの作成
- [Rスクリプトからレポート生成](https://rpubs.com/kohske/595)

----------
----------
## Chunk options

https://r4ds.had.co.nz/
R for Data Science
- https://r4ds.had.co.nz/r-markdown.html
  - https://r4ds.had.co.nz/r-markdown.html#code-chunks
    - https://r4ds.had.co.nz/r-markdown.html#chunk-options

https://rmarkdown.rstudio.com/lesson-3.html
Chunk Options
- include = FALSE prevents code and results from appearing in the finished file. R Markdown still runs the code in the chunk, and the results can be used by other chunks.
- echo = FALSE prevents code, but not the results from appearing in the finished file. This is a useful way to embed figures.
- message = FALSE prevents messages that are generated by code from appearing in the finished file.

https://kazutan.github.io/kazutanR/Rmd_intro.html
R Markdown入門 | Rチャンク(chunk)の基本 | Rチャンク オプション
- echo(コード部の表示・非表示)
- eval(コード部の評価・非評価)
- include(レポートに組み込むか否か)

https://rstudio.com/wp-content/uploads/2016/11/Rmarkdown-cheatsheet-2.0_ja.pdf
- echo - 出力ドキュメントにコードを表示する
(デフォルト=TRUE) 
- eval - チャンク内でコードを実行する
(デフォルト=TRUE)
- include - 実行後チャンクをドキュメントに含
めるかの設定 (デフォルト = TRUE)
- message - message()関数で出力される文字を
表示するかの設定 (デフォルト = TRUE)

----------
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
## [NCBI Taxonomy](https://www.ncbi.nlm.nih.gov/taxonomy) 
[NCBI Entrezデータベースに少なくとも1件以上登録されている全ての生物種と上位分類名を収集したデータベース](https://integbio.jp/dbcatalog/record/nbdc00700)  

- NCBI Taxonomy Browserを使って、生物分類と配列情報を関連させて調べる 2017 https://doi.org/10.7875/togotv.2017.092
- TogoWS RESTサービスを使い倒す 2011 https://doi.org/10.7875/togotv.2011.058
  - 統合ウェブサービスの概要と目的 http://togows.dbcls.jp/site/ja/index.html
  - TogoWS REST service http://togows.dbcls.jp/site/en/rest.html
    - http://togows.dbcls.jp/entry/nucleotide/J00231/taxonomy

NCBIからTaxonomyを取得する:  
```
# Make a vector containing NCBI accessions
ACCESSIONs <- c("NC_007322", "NC_007414", "AP018710")

# create a function to retrieve NCBI taxonomy
get_taxonomy <- function(ACCESSION) read.table(file=paste0("http://togows.dbcls.jp/entry/nucleotide/",ACCESSION,"/taxonomy"), sep=";")

# Retrieve NCBI taxonomy and store them in list variable "taxonomy"
taxonomy <- sapply(ACCESSIONs, get_taxonomy)
taxonomy
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

DDBJ [Codes Used in Sequence Description](https://www.ddbj.nig.ac.jp/ddbj/code-e.html)
[配列の記載に用いる略号](http://www.ddbj.nig.ac.jp/sub/code-j.html)

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
## BLAST
[BLAST (Basic Local Alignment Search Tool)](https://ja.wikipedia.org/wiki/BLAST)

### [NCBI BLAST](https://blast.ncbi.nlm.nih.gov/)
- [Protein BLAST: search protein databases using a protein query](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastp&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)
  - Checking the **Align two or more sequences** box will display two text boxes for entering queries.
  - Enter the E. coli EbgC protein accession number [NP_417548.1](https://www.ncbi.nlm.nih.gov/protein/NP_417548.1) into the upper search box
  - Enter the [Bacteroides EbgC protein](https://www.ncbi.nlm.nih.gov/protein/?term=ebgC%20Bacteroides) accession number [EFI39110.1](https://www.ncbi.nlm.nih.gov/protein/EFI39110.1) into the lower search box
  - Click the **BLAST** button
  - The result shows an E value of 1.8 (above the limit of 1e-3 for homologs). Thus, despite having the same name, the Bacteroides EbgC sequences are not homologs of the E. coli EbgC sequence and do not belong on the tree.

Reference:
Hall (2017) [Phylogenetic Trees Made Easy: A How-To Manual (5th edition)](https://www.kinokuniya.co.jp/f/dsg-02-9781605357102)
(p.48) Other Ways to Find Sequences of Interest (Beware! The Risks Are High)

### [UniProt BLAST](https://www.uniprot.org/blast/)
- [How to use UniProt tools](https://www.ebi.ac.uk/training/online/course/uniprot-exploring-protein-sequence-and-functional/exploring-uniprotkb-entry/how-use-uniprot-t)
  - ['BLAST' sequence similarity searching](https://www.ebi.ac.uk/training/online/course/uniprot-exploring-protein-sequence-and-functional/how-use-uniprot-tools/blast-sequence-simila)

![](https://www.ebi.ac.uk/training/online/sites/ebi.ac.uk.training.online/files/user/2760/images/UniProt_tutorial/blast_1.png)

- https://www.uniprot.org/uniprot/Q9CD83
- Select the 'Blast' tab -> 'Advanced'
```
Target database: UniProtKB/Swiss-Prot
E-Threshold: 0.0001
Hits: 50
```
- Click the 'Run Blast' button.

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

[Exercises on Sequence Alignment](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises) |
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

[Exercises on Multiple Alignment and Phylogenetic Trees](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter5.html#exercises) |
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
