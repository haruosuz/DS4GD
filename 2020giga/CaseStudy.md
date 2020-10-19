**[DATA SCIENCE FOR GENOME DYNAMICS (GIGA)](https://github.com/haruosuz/DS4GD/tree/master/2020giga)**  
[SFC Online Learning System (SOL)](https://sol.sfc.keio.ac.jp/)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- assignment 1 課題No.1 class cancelled
- [assignment 2](#assignment-2) 課題No.2 「Introduction to R」
- [Compile Report](#compile-report)
- [assignment 3](#assignment-3) 課題No.3 「Installing R packages」

----------
## assignment 0
**選抜課題**

【ASSIGNMENT】
Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

【課題内容】
本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

----------
## assignment 2
**課題No.2 「Introduction to R」**

Watch the following videos and write your comments or questions.
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

以下の動画を見て、疑問点を報告する。
- [Rプログラミングと統計](https://www.youtube.com/watch?v=jjkBsU4AChM&list=PLdNQOrt5fdN8P-vy1i6vep9OP4R1AZcEb)


[回答例]
```
「Rプログラミングと統計 p.3 ~ p.10 を見た。
疑問点は次の通りである。
1. 行列とデータフレームとリストの違いは？
2. NAとNaNの違いが理解できなかった。
```

[Download R scripts](https://github.com/haruosuz/r4bioinfo/raw/master/scripts/my_basic_r.zip)

----------
### R_object

https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/installr.html#a-brief-introduction-to-r
All variables (scalars, vectors, matrices, etc.) created by R are called objects.

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/05.html
05. オブジェクトと代入（付値）
R が作ったり操作した実体はオブジェクト（object）と呼ばれる．変数，数の配列，文字列関数，データ，関数その他全てがそれにあたる．

----------
### R_vector

2017.06.13
https://stats.biopapyrus.jp/r/basic/vector.html
ベクトル | R のベクトル操作と演算
R のベクトルは、数学のベクトルとほぼ同じ概念である。数学では 1 つのベクトルに複数の要素を含めると同様に、R では 1 つのベクトルに複数の値を代入できる。

http://cse.naro.affrc.go.jp/takezawa/r-tips/r.html
R-Tips
 ベクトル篇

----------
### R_factor

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
## assignment 3
**課題No.3 「Installing R packages」**

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
----------

