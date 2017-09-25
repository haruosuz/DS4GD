SFC 2017年度 秋学期 火曜日３時限  
Keio SFC 2017 Fall Tuesday 3rd Period
[λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)

# DS4GD
生命動態のデータサイエンス/生命情報解析(GIGA) [シラバス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2017_25381&ks=B3206)  
DATA SCIENCE FOR GENOME DYNAMICS / GENOME INFORMATICS (GIGA) [Syllabus](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2017_25381&ks=B3206&key=15dca30252717a3a92bfaf7cc0fc596c&lang=en)  

## References
参考文献
- [Conrad Bessant; Darren Oakley; Ian Shadforth - Building Bioinformatics Solutions 2nd edition, Oxford University Press, 2014, 368p.](https://github.com/haruosuz/books/tree/master/bbs) 
- [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://a-little-book-of-r-for-bioinformatics.readthedocs.org/en/latest/)

## Class Schedule & Materials
講義日程と資料

- 2017-09-26 No. 1 - イントロダクション[ Introduction ](#Introduction)
- 2017-10-03 No. 2 - 生物学的データ[ Biological data ](https://github.com/haruosuz/books/tree/master/bbs#chapter-1-introduction)
- 2017-10-10 No. 3 - R言語入門[ Introduction to R ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#how-to-install-r-and-a-brief-introduction-to-r)
- 2017-10-17 No. 4 - DNA配列解析1[ DNA Sequence Statistics (1) ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)
- 2017-10-24 No. 5 - DNA配列解析2[ DNA Sequence Statistics (2) ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)
- 2017-10-31 No. 6 - DNA配列解析3[ DNA Sequence Statistics (3) ]
- 2017-11-07 No. 7 - 中間発表[ interim report ]
- 2017-11-14 No. 8 - タンパク質配列解析[ Protein sequence analysis ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
- 2017-11-21 (前半科目試験日)
- 2017-11-28 No. 9 - ペアワイズ配列アラインメント[ Pairwise Sequence Alignment ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
- 2017-12-05 No. 10 - 多重配列アライメント[ Multiple Sequence Alignment ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#multiple-alignment-and-phylogenetic-trees)
- 2017-12-12 No. 11 - 系統解析[ Phylogenetic Analysis ](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#multiple-alignment-and-phylogenetic-trees)
- 2017-12-19 No. 12 - クラスター分析[ Cluster Analysis ](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md)
- 2017-12-26 No. 13 - ヒートマップ[ Heat Map ](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)
- 2018-01-16 No. 14 - 最終発表[ Oral presentation ]

----------

## Introduction

### [Bioinformatics](https://github.com/haruosuz/books/tree/master/bbs#11-from-data-to-knowledge-the-aim-of-bioinformatics)
[bioinformatics | バイオインフォマティクス | 生物情報科学](http://bi.biopapyrus.net)  

![http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about](http://blog.thegrandlocus.com/img/bioinformatic_word_cloud.png)

## Bioinformatician

![http://blog.fejes.ca/?p=2418](http://blog.fejes.ca/wp-content/uploads/2014/01/bioinformatics_chart1.png)

### [Bioinformatics Research](https://github.com/haruosuz/books/tree/master/bbs#13-principal-applications-of-bioinformatics)

![http://www.metabolomics.bbsrc.ac.uk/background.htm](http://www.metabolomics.bbsrc.ac.uk/background_files/image038.gif)

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

![http://www.quizbiology.com/2013/05/bioinformatics-mcq-quiz.html](http://lh5.ggpht.com/-RVDAcMLXpPQ/UaLVfpoguLI/AAAAAAAAGdw/n8DEk4aPAIg/Bioinformatics%252520Resources%25255B11%25255D.png)

#### [Nucleotide](http://www.ddbj.nig.ac.jp/sub/code-e.html#nucleotide)
[塩基](http://www.ddbj.nig.ac.jp/sub/code-j.html#nucleotide)

[SILVA rRNA database](https://www.arb-silva.de)

![http://www.arb-silva.de/documentation/sina-tutorial/](http://www.arb-silva.de/fileadmin/graphics_general/main/tutorial_aligner/aligner_basic01.png)

#### [Amino Acids](http://www.ddbj.nig.ac.jp/sub/code-e.html#amino)
[アミノ酸](http://www.ddbj.nig.ac.jp/sub/code-j.html#amino)配列

[UniProt](https://ja.wikipedia.org/wiki/Swiss-Prot)

----------

## Step
[λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)
iMac Retina 5k 27inch

### Unix
![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

	bash

	wget https://github.com/haruosuz/DS4GD/raw/master/2017/examples_2016.tar.gz

### R
[Introduction to R](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#how-to-install-r-and-a-brief-introduction-to-r)

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

Loading Packages

    library(seqinr)
    library(ape)
    library(Biostrings)
    library(msa)

Print version information

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
