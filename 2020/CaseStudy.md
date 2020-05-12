**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2020)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「Introduction to R」
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題No.5 「Guest Speaker (1)」
- [assignment 6](#assignment-6) 課題No.6 「Guest Speaker (2)」
- [assignment 7](#assignment-7) 課題No.7 「Guest Speaker (3)」
- [assignment 8](#assignment-8) 課題No.8 「dotplot」
- [assignment 9](#assignment-9) 課題No.9 「Pairwise Sequence Alignment」
- [assignment 10](#assignment-10) 課題No.10 「Multiple Alignment and Phylogenetic Trees」
- [assignment 11](#assignment-11) 課題No.11 「presentation slides」
- [Installing R packages](#installing-r-packages)
- [assignment 12](#assignment-12) 課題No.12

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

http://takenaka-akio.org/doc/r_auto/list.html
リストにオブジェクトをしまう
ベクトルは、同じ型のデータをまとめて並べたデータ構造です。 これに対し、リストはどのような型のデータでもしまえるデータ構造です。 ベクトルでもリスト自身でもデータフレームでも統計解析関数が返す複雑なオブジェクトでも、なんでも格納できます。 自動化した処理の結果をいくつもまとめておいて、最後にまとめて処理したいなどという場合にも便利でしょう。 なお、データフレームもリストの一種です。
リストの要素の指定
リストの要素は、[　] や [[ ]] に要素の位置を与えて指定できます。 [　]を使った場合は「指定した要素を含むリスト」、 [[ ]]を使った場合は「要素そのもの」を指すことに注意が必要です。

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

----------
https://dotinstall.com/lessons/basic_r/28111
#11 データフレームを扱ってみよう | R言語入門 - プログラミングならドットインストール

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

パッケージの呼び出し:  
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
例えば、[ハンセン病（Leprosy）](https://ja.wikipedia.org/wiki/ハンセン病)の原因細菌[*Mycobacterium leprae*（らい菌）](https://ja.wikipedia.org/wiki/らい菌)を検索する。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Mycobacterium%20leprae)、検索ボックス下の「Overview(1); Prokaryotes(6)」のうち、「Prokaryotes」をクリックすると、*Mycobacterium leprae*に属する菌株**Strain**が表示される。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Mycobacterium%20leprae)、列**Organism Name**の"Mycobacterium leprae TN"株をクリックして開く。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/903?genome_assembly_id=169891)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に[アクセッション番号](https://www.ddbj.nig.ac.jp/acc_def.html)が示されている。
アクセッション番号は、"NC_002677.1" (RefSeq) と "AL450380.1" (INSDC) 。

- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for the bacterial species *Mycobacterium leprae*, you would type just Organism name "Mycobacterium leprae" in the search box and press "Search".
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
filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
#filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 3
**課題No.3 「DNA Sequence Statistics (1)」**

[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. What are the last twenty nucleotides of the genome sequence?

    tail(seq1, 20)

Q2. What is the length in nucleotides of the genome sequence?

    length(seq1)

Q3. How many of each of the four nucleotides A, C, T and G, and any other symbols, are there in the genome sequence?

    table(seq1)

DDBJ [配列の記載に用いる略号](http://www.ddbj.nig.ac.jp/sub/code-j.html)  
DDBJ [Codes Used in Sequence Description](https://www.ddbj.nig.ac.jp/ddbj/code-e.html)

Q4. What is the GC content of the genome sequence, when (i) all non-A/C/T/G nucleotides are included, (ii) non-A/C/T/G nucleotides are discarded?

	help("GC")
    GC(seq1)
    GC(seq1, exact=FALSE)
    GC(seq1, exact=TRUE)

Q5. How many of each of the four nucleotides A, C, T and G are there in the complement of the genome sequence?

![http://revertra.webcrow.jp/DNA/index.php](http://revertra.webcrow.jp/DNA/dnaseq.png)

	#help.search("complement")
	#help("comp")
    table(comp(seq1))

Q6. How many occurrences of the DNA words CC, CG and GC occur in the genome sequence?

    count(seq=seq1, wordsize=2)

Q7. How many occurrences of the DNA words CC, CG and GC occur in the (i) first 1000 and (ii) last 1000 nucleotides of the genome sequence?
How can you check that the subsequence that you have looked at is 1000 nucleotides long?

    count(seq=head(seq1, 1000), wordsize=2)
    count(seq=tail(seq1, 1000), wordsize=2)

----------
## assignment 4
**課題No.4 「DNA Sequence Statistics (2)」**

[Exercises on DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

[53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
フォント・ファミリーを指定する

    # setting font in plots
    par(family="mono")

Q1. Draw a sliding window plot of GC content in the genome, using a window size of 200 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# write a function to make a sliding window plot:
    slidingwindowplotGC <- function(windowsize, inputseq)
    {
      require("zoo") # this function requires the 'zoo' R package # install.packages('zoo')
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = GC)
      plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")
    }

	# make a sliding window plot with a window size of 200 nucleotides:
    slidingwindowplotGC(windowsize = 200, inputseq = seq1)

Q2. Draw a sliding window plot of GC content in the genome sequence using a window size of 2000 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# make a sliding window plot of GC content using a window size of 2000 nucleotides:
    slidingwindowplotGC(windowsize = 2000, inputseq = seq1)

Q3. Write a function to calculate the AT content of a DNA sequence (ie. the fraction of the nucleotides in the sequence that are As or Ts). What is the AT content of the genome?

	# Here is a function to calculate the AT content of a genome sequence:
    AT <- function(x){ library("seqinr"); 1 - GC(x) }

    # use the function to calculate the AT content of the genome:
    AT(seq1)

    # AT = 1 - GC, ie. (AT + GC = 1):
    GC(seq1)
    AT(seq1) + GC(seq1)

Q4. Write a function to draw a sliding window plot of AT content.

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

Q5. Is the 3-nucleotide word GAC over-represented or under-represented in the genome sequence?

	# calculate Rho for words of length 3 in the genome
	rho(sequence = seq1, wordsize=3)

    # rho > 1: over-represented
    # rho < 1: under-represented

----------
## assignment 5
**課題No.5 「Guest Speaker (1)」**

----------
## assignment 6
**課題No.6 「Guest Speaker (2)」**

----------
## assignment 7
**課題No.7 「Guest Speaker (3)」**

----------
### Elongation Factor
翻訳伸長因子
[EF-Tu](https://ja.wikipedia.org/wiki/EF-Tu)
[EF-G](https://ja.wikipedia.org/wiki/EF-G)

[重複遺伝子EF-Tu/1aとEF-G/2に基づく超生物界の複合系統樹](https://www.brh.co.jp/research/formerlab/miyata/2005/post_000008.html)

----------
## assignment 8
**課題No.8 「dotplot」**

ドットプロットで2つの配列を比較
[Comparing two sequences using a dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)

Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Download FASTA-format files of two protein sequences from UniProt.

```
library(seqinr)
seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q9CD83.fasta")[[1]]
seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/A0PQ23.fasta")[[1]]
length(seq1)
getAnnot(seq1)

# setting font in plots
par(family="mono")
```

Q2. Create a dotplot for two sequences.
```
dotPlot(seq1, seq2, wsize = 1, wstep = 1, nmatch = 1)
dotPlot(seq1, seq2, wsize = 2, wstep = 2, nmatch = 2)
dotPlot(seq1, seq2, wsize = 3, wstep = 3, nmatch = 3)
```

Q3. Create a self-similarity dot-plot; i.e. Comparing the sequence against itself.
```
dotPlot(seq1, seq1, wsize = 1, wstep = 1, nmatch = 1)

dotPlot(seq2, seq2, wsize = 1, wstep = 1, nmatch = 1)
```

https://github.com/haruosuz/bioinfo/blob/master/references/README.bioinfo.tools.md#dotplot

----------
## assignment 9
**課題No.9 「Pairwise Sequence Alignment」**

[Exercises on Sequence Alignment](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Download FASTA-format files of two protein sequences of interest from UniProt.

    library("seqinr")
    seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q9CD83.fasta")[[1]]
    seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/A0PQ23.fasta")[[1]]
    seq1string <- toupper(c2s(seq1)) # convert the sequence to a string and to uppercase
    seq2string <- toupper(c2s(seq2)) # convert the sequence to a string and to uppercase

Q2. What is the alignment score for the optimal global alignment between the two proteins, when you use the BLOSUM50 scoring matrix?
(set gapOpening = -9.5 and gapExtension = -0.5)

	library("Biostrings") # load the Biostrings package
	data(BLOSUM50) # load the BLOSUM50 scoring matrix
    myglobalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
                      gapOpening = -9.5, gapExtension = -0.5) # align the two sequences
	myglobalAlign

Q3. Use the writePairwiseAlignments() function to view the optimal global alignment.

    writePairwiseAlignments(myglobalAlign)

Q4. What global alignment score do you get for the two proteins, when you use the BLOSUM62 alignment matrix?

	data(BLOSUM62) # load the BLOSUM62 scoring matrix
    myglobalAlign2 <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM62",
                       gapOpening = -9.5, gapExtension = -0.5) # align the two sequences
	myglobalAlign2

Q5. What is the alignment score for the optimal local alignment between the two proteins?

    mylocalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
                     gapOpening = -9.5, gapExtension = -0.5, type="local")
	mylocalAlign

----------
## assignment 10
**課題No.10 「Multiple Alignment and Phylogenetic Trees」**

- [Exercises on Multiple Alignment and Phylogenetic Trees](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter5.html#exercises)
  - [Answers to the exercises on Multiple Alignment and Phylogenetic Trees](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html#multiple-alignment-and-phylogenetic-trees)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

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
# setting font in plots
par(family="mono")

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
**課題No.11 「presentation slides」**

Submit your presentation slides for your final presentation Tuesday 2020-07-21.  
**Ten** minutes will be allocated for each presentation, including presentation and discussion.

Report your main findings on analyses of objects (DNA, protein, and other textual sequences, etc.) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global sequence alignment, and local sequence alignment), multiple sequence alignment, and phylogenetic trees, etc.

2020-07-21 (火) 最終発表のスライドを提出する。  
発表時間：1人あたり最大**10**分

興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）の解析結果を報告する。解析の例として、配列の統計（長さ、GC含量、塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル配列アライメント、ローカル配列アライメント）、多重配列アライメント、系統樹などが含まれる。

----------

----------

----------

----------

----------



----------




