**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2021)**  
[SFC Online Learning System (SOL)](https://sol.sfc.keio.ac.jp/)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題1 「Introduction to R」
- [assignment 2](#assignment-2) 課題2 「Installing R packages」
- [INSDC](#insdc)
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題5 「dotplot」
- [BLAST](#blast)
  - [UniProt BLAST](#uniprot-blast)
- [assignment 6](#assignment-6) 課題6 「Pairwise Sequence Alignment」
- [assignment 7](#assignment-7) 課題7 「Multiple Alignment and Phylogenetic trees」
- [assignment 8](#assignment-8) 課題8 「TBA」
- [assignment 9](#assignment-9) 課題9 「TBA」
- [assignment 10](#assignment-10) 課題10 「TBA」
- [assignment 11](#assignment-11) 課題11 「TBA」
- [assignment 12](#assignment-12) 課題12 「draft report」
- [assignment 13](#assignment-13) 課題13 「final report」

----------
## assignment 0
**選抜課題**

本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

----------
## assignment 1
**課題1 「Introduction to R」**

次のURLからRスクリプトをダウンロードして下さい。  
Please download R scripts (**my_datasciencedojo_r.R**, **my_darumalab.R**) from the following URL.  
https://github.com/haruosuz/r4bioinfo/raw/master/scripts/my_basic_r.zip

Watch the following videos and write your comments or questions.
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)
  - **my_basic_r/my_datasciencedojo_r.R**


[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

以下の動画を見て、疑問点を報告する。
- [Rプログラミングと統計](https://www.youtube.com/watch?v=jjkBsU4AChM&list=PLdNQOrt5fdN8P-vy1i6vep9OP4R1AZcEb)
  - **my_basic_r/my_darumalab.R**


[回答例]
```
「Rプログラミングと統計 p.3 ~ p.10 を見た。
疑問点は次の通りである。
1. 行列とデータフレームとリストの違いが理解できなかった。
2. ファクターと文字列データの違いは？
```

----------

課題「Introduction to R」の疑問点に関連する資料  
References related to comments/questions for assignment "Introduction to R".  

- https://github.com/haruosuz/DS4GD/blob/master/2020giga/CaseStudy.md#assignment-2
- https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#assignment-1


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
と聞いてきますので，作業スペース（現在の状態）を保存して終了するなら y（はい），保存しないで終了するなら n（いいえ），終了をキャンセルする（終了しない）なら c（キャンセル）と答えます。通常は n（いいえ）と答えます。y（はい）と答えた場合，作業スペースの内容がRの作業ディレクトリ（working directory）の .RData というファイルに保存され，次回の起動時に自動的に読み込まれます。大量のデータを扱った場合，.RData は非常に大きくなります。

----------
### R_vector

R-Tips [16. 種々のベクトル](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/16.html)
 論理型ベクトル
|
論理値を要素とするベクトルを論理型ベクトルと呼ぶ．正式名（TRUE，FALSE）でも略記名（T，F）でも指定できる．論理型ベクトルに対する論理演算子として，& (論理積) ， | (論理和) ，! (否定) ，xor (排他的論理和) があり，これらを用いると要素毎の演算を行なう．

----------
### R_factor

Data Science Dojo [Using Factors - Introduction to R Programming - Part 8 - YouTube](https://www.youtube.com/watch?v=a_N6Q0O5T3s&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=8)

[Bioinformatics Data Skills: Reproducible and Robust Research With Open Source Tools](https://www.oreilly.com/library/view/bioinformatics-data-skills/9781449367480/)
R Language Basics | 191

Factors and classes in R

Another kind of vector you’ll encounter are factors. Factors store categorical variables, such as a treatment group (e.g., “high,” “medium,” “low,” “control”), strand (forward or reverse), or chromosome (“chr1,” “chr2,” etc.).

[バイオインフォマティクスデータスキル ――オープンソースツールを使ったロバストで再現性のある研究](https://www.oreilly.co.jp/books/9784873118635/)
8.2 R 言語の基礎 ■ 205

8.2.3.2 R の因子とクラス 

他にも作業中に出会う可能性のあるベクトルに因子がある。因子はカテゴリーを表す変数を収めたベクトルである。たとえば処理群(「高」、「中」、「低」、「対照」など)、鎖(「正鎖」または「相補鎖」)、あるいは染色体(「chr1」、「chr2」など)である。

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
### R_data.frame

[R Language Definition](https://cran.r-project.org/doc/manuals/R-lang.html#Data-frame-objects)
2.3.2 Data frame objects
|
Data frames are the R structures which most closely mimic the SAS or SPSS data set, i.e. a “cases by variables” matrix of data.
A data frame is a list of vectors, factors, and/or matrices all having the same length (number of rows in the case of matrices). 

[バイオインフォマティクスデータスキル ――オープンソースツールを使ったロバストで再現性のある研究](https://www.oreilly.co.jp/books/9784873118635/)
216 ■ 8 章 R 言語入門

データフレームから単一の列にアクセスするとき、R のデフォルトの動作は、これを 1 つの列を持つ データフレームとしてではなく、ベクトルとして返す。次に実行されるコードがデータフレームを入力 として期待している場合は問題となる。この動作を無効にするには、ブラケット演算子を使って引数 drop を FALSE に設定する。
```
> d[, "start", drop=FALSE]
```

[Bioinformatics Data Skills: Reproducible and Robust Research With Open Source Tools](https://www.oreilly.com/library/view/bioinformatics-data-skills/9781449367480/)
202 | Chapter 8: A Rapid Introduction to the R Language

When accessing a single column from a dataframe, R’s default behavior is to return this as a vector—not a dataframe with one column. Sometimes this can cause problems if downstream code expects to work with a dataframe. To disable this behavior, we set the argument drop to FALSE in the bracket operator:
```
> d[, "start", drop=FALSE]
```

----------
### R_typeof

[R Language Definition](https://cran.r-project.org/doc/manuals/R-lang.html#Objects)
2 Objects
|
R objects are often coerced to different types during computations. There are also many functions available to perform explicit coercion.

[Data Types and Structures – Programming with R](https://swcarpentry.github.io/r-novice-inflammation/13-supp-data-structures/)

[バイオインフォマティクスデータスキル ――オープンソースツールを使ったロバストで再現性のある研究](https://www.oreilly.co.jp/books/9784873118635/)
8.2 R 言語の基礎 ■ 205
|
R における型の強制変換
|
ベクトルのすべての要素は均一のデータ型でなければならないため、R は同じ型を持つよ うに要素の型変換を強制する。

[Bioinformatics Data Skills: Reproducible and Robust Research With Open Source Tools](https://www.oreilly.com/library/view/bioinformatics-data-skills/9781449367480/)
R Language Basics | 191
|
Type Coercion in R
|
Because all elements in a vector must have homogeneous data type, R will silently coerce elements so that they have the same type.

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
### R_read.table

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
### R_assignOps

[R: Assignment Operators](https://stat.ethz.ch/R-manual/R-devel/library/base/html/assignOps.html)
The operators <- and = assign into the environment in which they are evaluated. The operator <- can be used anywhere, whereas the operator = is only allowed at the top level (e.g., in the complete expression typed at the command prompt) or as one of the subexpressions in a braced list of expressions.

[What are the differences between "=" and "<-" assignment operators in R? - Stack Overflow](https://stackoverflow.com/questions/1741820/what-are-the-differences-between-and-assignment-operators-in-r)

2018年12月24日 [Rにおける代入演算子"<-"と"="の違い - Qiita](https://qiita.com/tonhosshi/items/426edd9bbed802bd8c33)

R-Tips [28. 演算子](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/28.html)
```
<<-	永続代入
<-，->	代入
=	代入
```

----------
### R/MEGA

8th Aug, 2017
https://www.researchgate.net/post/Does-anybody-have-a-pipeline-created-or-experience-of-taking-Phylogenetic-trees-from-MEGA-to-Rggtree
Does anybody have a pipeline created or experience of taking Phylogenetic trees from MEGA to R(ggtree)?

https://support.bioconductor.org/p/41863/
Packages reproducing phylogenetic tree from output of MEGA
|
You can save the tree from MEGA in newick format.
APE is an R package that reads newick format and has a lot of options
to
plot phylogenetic trees.


----------

----------
## assignment 2
**課題2 「Installing R packages」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

次のURLからRスクリプトをダウンロードして下さい。  
Please download the R script (**my_setup_packages.R**) from the following URL.  
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

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
## INSDC

[International Nucleotide Sequence Database Collaboration](https://www.ddbj.nig.ac.jp/insdc-e.html)
[塩基配列データベース構築の国際協調](https://www.ddbj.nig.ac.jp/insdc.html)

<img src="https://www.ddbj.nig.ac.jp/assets/images/center/insdc_shoukai.gif" alt="https://www.ddbj.nig.ac.jp/about/insdc.html" width=25%>

- [RefSeq Frequently Asked Questions (FAQ) - RefSeq Help - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK50679/)
  - [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
  - [What causes the version number of a RefSeq record to change?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_causes_the_version_number)
  - [What updates to RefSeq records need a simple version number change and which require a new accession number?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_updates_to_refseq_records)
- VERSION
  - [DDBJ flat file format](https://www.ddbj.nig.ac.jp/ddbj/flat-file-e.html#VERSION)
This line consists of an accession number and a version number, like “AB123456.1”, in which the digit(s) after the period is a version number.
The data open to public for the first time is version number as “1”. The reason for adding VERSION is that since a released sequence sometimes revised by the submitter, the accession number alone cannot specify the sequence in question causing the user a trouble. The number is increased by one every time when a revised sequence is made public. And accession number will NOT be changed generally.
  - [DDBJ 公開形式 Flat file](https://www.ddbj.nig.ac.jp/ddbj/flat-file.html#VERSION)
アクセッション番号とバージョン番号で構成されています。
はじめて公開されたデータは、バージョン番号は “1” が記載されています。当該エントリの配列が訂正・更新された場合には、バージョン番号が更新されます。通常、配列が訂正・更新された場合にアクセッション番号が変更されることはありません。

----------
## NCBI Genome List
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for [Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2), the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), you would type just Organism name "SARS-CoV-2" in the search box and press "Search".
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2), you will see the number of hits to "SARS-CoV-2" in each of the NCBI databases: "Overview (1); Viruses (92)". When you click on "Viruses", it will show all the strains.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2), When you click on the **Organism Name** "Severe acute respiratory syndrome coronavirus 2", it will bring you to the record for this organism in the NCBI Genome database.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732), you will see the **Replicon Info** of the Organism. 
The NCBI [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the DNA sequences are "NC_045512" (**RefSeq**) and "MN908947" (**INSDC**), respectively.

- NCBIのウェブサイトからゲノム配列データを取得する。
  - ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。
例えば、[新型コロナウイルス感染症 (COVID-19)](https://ja.wikipedia.org/wiki/新型コロナウイルス感染症_%282019年%29)の原因となる[SARSコロナウイルス2](https://ja.wikipedia.org/wiki/SARSコロナウイルス2) "SARS-CoV-2" を検索する。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2)、検索ボックス下の「Overview (1); Viruses (92)」のうち、「Viruses」をクリックすると、SARS-CoV-2に属する株が表示される。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2)、列**Organism Name**の"Severe acute respiratory syndrome coronavirus 2"をクリックして開く。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に[アクセッション番号](https://www.ddbj.nig.ac.jp/acc_def.html)が示されている。
アクセッション番号は、"NC_045512" (**RefSeq**) と "MN908947" (**INSDC**) である。

NCBIからDNA配列を取得する:  
```
# Retrieving a DNA sequence from NCBI
library(seqinr)

ACCESSION <- "NC_045512" # Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)
#ACCESSION <- "NC_001477" # Dengue virus 1

filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
#filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")

# Retrieve the sequence and store it in list variable "seqs"
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]

# Get sequence annotations
getAnnot(seq1)
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 3
**課題3 「DNA Sequence Statistics (1)」**

次のURLからRスクリプトをダウンロードして下さい。  
Please download the R script (**my_assignment_chapter1_dna1.R**) from the following URL.  
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 4
**課題4 「DNA Sequence Statistics (2)」**

Please download the R script (**my_assignment_chapter2_dna2.R**) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

PDF/HTML形式ファイルで提出して下さい。  
Please submit your assignment as a PDF or HTML document (**my_assignment_chapter1_dna1.html**), created using the [Compile Report](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report) command.

----------
## BLAST
[BLAST (Basic Local Alignment Search Tool)](https://ja.wikipedia.org/wiki/BLAST)

### [UniProt BLAST](https://www.uniprot.org/blast/)
- [How to use UniProt tools](https://www.ebi.ac.uk/training/online/course/uniprot-exploring-protein-sequence-and-functional/exploring-uniprotkb-entry/how-use-uniprot-t)
  - ['BLAST' sequence similarity searching](https://www.ebi.ac.uk/training/online/course/uniprot-exploring-protein-sequence-and-functional/how-use-uniprot-tools/blast-sequence-simila)

![](https://www.ebi.ac.uk/training/online/sites/ebi.ac.uk.training.online/files/user/2760/images/UniProt_tutorial/blast_1.png)

- [Severe acute respiratory syndrome coronavirus 2 (2019-nCoV) (SARS-CoV-2)](https://www.uniprot.org/taxonomy/2697049)
  - [Reviewed (16)](https://www.uniprot.org/uniprot/?query=reviewed:yes%20taxonomy:2697049) Swiss-Prot
    - [Spike glycoprotein](https://www.uniprot.org/uniprot/P0DTC2)
- Select the 'Blast' tab -> 'Default' or 'Advanced'
```
Target database: UniProtKB/Swiss-Prot
E-Threshold: 0.0001
Hits: 50
```
- Click the 'Run Blast' button.

----------
## assignment 5
**課題5 「dotplot」**

Please download the R script (**my_assignment_chapter4_align_dotplot.R**) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 6
**課題6 「Pairwise Sequence Alignment」**

Please download the R script (**my_assignment_chapter4_align_pairwise.R**) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 7
**課題7 「Multiple Alignment and Phylogenetic trees」**

Please download the R script (**my_assignment_chapter5_msa_tree.R**) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 8
**課題8 「TBA」**

----------
## assignment 9
**課題9 「TBA」**

----------
## assignment 10
**課題10 「TBA」**

----------
## assignment 11
**課題11 「TBA」**

----------
## assignment 12
**課題12 「draft report」**

Integrate and modify your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it as a PDF/HTML document.

これまでの課題（興味あるDNA/タンパク質の配列を解析した結果など）を統合・修正してレポートのドラフトを作成し、PDF/HTML形式ファイルで提出する。

https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html

----------
## assignment 13
**課題13 「final report」**

Submit your final report as a PDF/HTML document.

----------



