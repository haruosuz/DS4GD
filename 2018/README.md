Keio SFC 2018 Spring Tuesday 3rd Period
[λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)  
SFC 2018年度 春学期 火曜日３時限

# DS4GD
DATA SCIENCE FOR GENOME DYNAMICS / GENOME INFORMATICS [Syllabus](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2018_41550&ks=B3206&key=6b3c5f655e3d9919cab8bb18e8ee7eea&lang=en)  
生命動態のデータサイエンス/生命情報解析 [シラバス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2018_41550&ks=B3206)  

## References
参考文献
- [Conrad Bessant; Darren Oakley; Ian Shadforth - Building Bioinformatics Solutions 2nd edition, Oxford University Press, 2014, 368p.](https://github.com/haruosuz/books/tree/master/bbs) 
- [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- [Wim P. Krijnen (2009) "Applied Statistics for Bioinformatics using R"](https://github.com/haruosuz/r4bioinfo/tree/master/R_Wim_Krijnen)

## Class Schedule & Materials
講義日程と資料
- ケーススタディ [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2017giga/CaseStudy.md)
- 2018-04-10 No. 1 - イントロダクション [Introduction](#Introduction)
- 2018-04-17 No. 2 - 生物学的データ [Biological data](https://github.com/haruosuz/books/tree/master/bbs#chapter-1-introduction)
- 2018-04-24 No. 3 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#how-to-install-r-and-a-brief-introduction-to-r)
- 2018-05-01 木曜代替日
- 2018-05-08 No. 4 - DNA配列解析1 [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)
- 2018-05-15 No. 5 - DNA配列解析2 [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)
- 2018-05-22 No. 6 - Case Study [NCBI assembly summary](https://github.com/haruosuz/DS4GD/blob/master/2017giga/CaseStudy.md#ncbi-assembly-summary)
- 2018-05-29 No. 7 - 中間発表 interim report
- 2018-06-05 No. 8 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
- 2018-06-12 No. 9 - 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#multiple-alignment-and-phylogenetic-trees)
- 2018-06-19 No. 10 - クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md)
- 2018-06-26 No. 11 - ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)
- 2017-07-03 No. 12 - [Guest Speaker](#guest-speaker)
- 2017-07-10 No. 13 - [Guest Speaker](#guest-speaker)
- 2017-07-17 No. 14 - 最終発表 Oral presentation
- 2017-07-24 レポート提出期限 Deadline for final report

----------

## Introduction

### [Bioinformatics](https://github.com/haruosuz/books/tree/master/bbs#11-from-data-to-knowledge-the-aim-of-bioinformatics)
 
![http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about](http://blog.thegrandlocus.com/img/bioinformatic_word_cloud.png)

### [Bioinformatician](http://blog.fejes.ca/?p=2418)

![http://blog.fejes.ca/?p=2418](http://blog.fejes.ca/wp-content/uploads/2014/01/bioinformatics_chart1.png)

### [Bioinformatics Research](https://github.com/haruosuz/books/tree/master/bbs#13-principal-applications-of-bioinformatics)

![http://www.metabolomics.bbsrc.ac.uk/background.htm](http://www.metabolomics.bbsrc.ac.uk/background_files/image038.gif)

**Microbiome of the Built Environment (MoBE)**

![https://www.biomedcentral.com/collections/builtenvironment](https://resource-cms.springer.com/springer-cms/rest/v1/content/6629006/data/v1)

- [MetaSUB: Metagenomics & Metadesign of Subways & Urban Biomes](https://github.com/haruosuz/metasub) 都市環境の生物群集

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

![http://www.quizbiology.com/2013/05/bioinformatics-mcq-quiz.html](http://lh5.ggpht.com/-RVDAcMLXpPQ/UaLVfpoguLI/AAAAAAAAGdw/n8DEk4aPAIg/Bioinformatics%252520Resources%25255B11%25255D.png)

#### [Nucleotide](http://www.ddbj.nig.ac.jp/sub/code-e.html#nucleotide)
[SILVA rRNA database](https://www.arb-silva.de)

![http://www.arb-silva.de/documentation/sina-tutorial/](http://www.arb-silva.de/fileadmin/graphics_general/main/tutorial_aligner/aligner_basic01.png)

#### [Amino Acids](http://www.ddbj.nig.ac.jp/sub/code-e.html#amino)
[UniProt](https://ja.wikipedia.org/wiki/Swiss-Prot)

![https://ja.wikipedia.org/wiki/シーケンスアラインメント](https://upload.wikimedia.org/wikipedia/commons/8/86/Zinc-finger-seq-alignment2.png)

----------

## Step
[λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)
iMac Retina 5k 27inch

### Unix
![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

	bash

	wget https://github.com/haruosuz/DS4GD/raw/master/2017/examples_2016.tar.gz

### R
R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#how-to-install-r-and-a-brief-introduction-to-r)

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

	demo(graphics)

	quit()

### R packages

Install packages [`seqinr`](https://cran.r-project.org/web/packages/seqinr/index.html), [`ape`](https://cran.r-project.org/web/packages/ape/index.html):  

    install.packages("seqinr")
    install.packages("ape")

Install Bioconductor packages [`Biostrings`](http://bioconductor.org/packages/release/bioc/html/Biostrings.html), [`msa`](https://bioconductor.org/packages/release/bioc/html/msa.html):  

    source("https://bioconductor.org/biocLite.R")
    biocLite("Biostrings")
    biocLite("msa")

Loading Packages:

    library(seqinr)
    library(ape)
    library(Biostrings)
    library(msa)

Print version information:

    > sessionInfo()

    R version 3.3.3 (2017-03-06)
    Platform: x86_64-apple-darwin13.4.0 (64-bit)
    Running under: OS X Mavericks 10.9.5

    other attached packages:
    msa_1.6.0
    Biostrings_2.42.1
    ape_4.1
    seqinr_3.3-6       

----------

On Jun 4, 2016, at 18:14, CNS-STAFF <cns-staff@sfc.keio.ac.jp wrote:

湘南藤沢ITCの高橋と申します。

今まで通り Biostrings_2.38.4 は利用可能です。
ホームディレクトリにBiostringsをインストールされていない方は
以下の手順でインストールしていただければお使いいただけます。

1) R.app を起動する
2) Biostrings をホームディレクトリにインストールする

	source("http://bioconductor.org/biocLite.R")
	biocLite("Biostrings")

 ※ インストール時に Old packages をアップデートするか
    聞かれますが n を選択してください。

      Update all/some/none? [a/s/n]: < n を入力する。

3) Biostrings をロードする

 library("Biostrings")

なお、既にインストール済みの方はそのままお使いいただけます。

以上、よろしくお願いいたします。

----------
