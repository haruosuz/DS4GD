# 2021

[2021年春学期](https://sol.sfc.keio.ac.jp/courses/2702)
生命動態のデータサイエンス [DS2] / DATA SCIENCE FOR GENOME DYNAMICS [DS2]
[生命動態のデータサイエンス [DS2] / DATA SCIENCE FOR GENOME DYNAMICS [DS2]](https://sol.sfc.keio.ac.jp/courses/2702)

## References
**参考文献**
- [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- [Sheri Sanders - Introduction to R for Biologists, Version 2, 2019, 96p.](https://ncgas.org/training/r_textbook_full.pdf)
- Hadley Wickham, Garrett Grolemund - R for Data Science, 2016, 520p. [https://r4ds.had.co.nz/] ; 黒川 利明 (訳), 大橋 真也 (技術監修). Rではじめるデータサイエンス, O'Reilly Japan, 2017年10月, 480p. https://www.oreilly.co.jp/books/9784873118147/
- Andrew Beckerman, Dylan Childs, and Owen Petchey - Getting Started with R: An Introduction for Biologists, 2nd Edition, Oxford University Press, 2017, 240p. http://r4all.org/books/ ; 富永大介 (翻訳). Rをはじめよう生命科学のためのRStudio入門, 羊土社, 2019年03月12日, 254p. https://www.yodosha.co.jp/yodobook/book/9784758120951/
- Emmanuel Paradis - Analysis of Phylogenetics and Evolution with R (Use R!), Springer; 2nd ed., 2011/11/5, 404p. https://link.springer.com/book/10.1007%2F978-1-4614-1743-9
- Barry G. Hall - Phylogenetic Trees Made Easy: A How-To Manual, 5th ed, Sinauer, 2017/12/15, 310p. https://www.redshelf.com/book/806872
- 藤博幸（編）. よくわかるバイオインフォマティクス入門, 講談社サイエンティフィク, 2018, 199p. https://www.kspub.co.jp/book/detail/5138212.html

----------

## Class Schedule & Materials
**講義日程と資料**

- [Calendar for Spring Semester 2021](https://www.sfc.keio.ac.jp/en/docs/0baa4ad6c126b7b898e927b0e22d84a54b15b53d.pdf)
- [2021年度 春学期授業カレンダー](https://www.sfc.keio.ac.jp/doc/1dbd15e1a5013ec7df1f658328033f5a78f0f0b7.pdf)
- 2020-04-13 No. 1 - イントロダクション [Introduction](#introduction)
  - [R/RStudio](#r-rstudio)
- 2020-04-20 No. 2 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#how-to-install-r-and-a-brief-introduction-to-r)
  - 顧みられない熱帯病 [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
- 2020-04-27 No. 3 - DNA配列解析(1) [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
  - [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2020giga/CaseStudy.md#ncbi-genome-list)
- 2020-05-04 No. 4 - DNA配列解析(2) [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-2)
  - *みどりの日【国民の休日】[National holiday](https://www8.cao.go.jp/chosei/shukujitsu/gaiyou.html)*
- 2020-05-11 No. 5 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
  - タンパク質データベース Protein sequence database [UniProt](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#uniprot)
  - ドットプロット [dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)
  - [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/2020giga/CaseStudy.md#blast)
- 2020-05-18 No. 6 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
  - グローバル・アライメント [Pairwise global alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
  - ローカル・アラインメント [Pairwise local alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-local-alignment-of-protein-sequences-using-the-smith-waterman-algorithm)
- 2020-05-25 No. 7 - 中間発表 [interim report](#interim-report)
- 2020-06-01 No. 8 - 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
- 2020-06-08 No. 9 - [Guest Speaker](#guest-speaker)
- 2020-06-15 No. 10 - [Guest Speaker](#guest-speaker)
- 2020-06-22 No. 11 - [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2020giga/CaseStudy.md)
  - [my_script2report.R](https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip)
  - [Chunk options](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#chunk-options)
- 2020-06-29 No. 12 - [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2020giga/CaseStudy.md)
- 2020-07-06 No. 13 - 最終回
  - 最終発表 [final presentation](#final-presentation)
- 2020-07-13 - レポート提出期限 Deadline for [final report](#final-report)

----------
## final presentation
**最終発表**

Presentation time: 10 minutes will be allocated for each presentation (including Q&A).
Report your main findings on analyses of objects (DNA, protein, and other textual sequences, etc.) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global sequence alignment, and local sequence alignment), multiple sequence alignment, and phylogenetic trees, etc.

発表時間：1人あたり最大10分（質疑応答を含む）。
興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）の解析結果を報告する。解析の例として、配列の統計（長さ、GC含量、塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル配列アライメント、ローカル配列アライメント）、多重配列アライメント、系統樹などが含まれる。

----------
## Introduction

### [Bioinformatics](http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about)

### [Bioinformatician](https://www.biostars.org/p/223069/)

### [Bioinformatics research](https://github.com/haruosuz/books/blob/master/bbs/README.md#13-principal-applications-of-bioinformatics)

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

----------
### R RStudio
- Oct 10, 2020 [R for Ecologists (lesson 1) Installing R and RStudio](https://www.youtube.com/watch?v=YKvkXKeGoa8)
- Jan 24, 2020 [R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners](https://www.youtube.com/watch?v=YBAWVNWiZlU)
- 2018-04-08 [統計解析ソフト「R」の使い方 〜Rの導入・パッケージの導入・作図・統計解析の基本編〜](https://doi.org/10.7875/togotv.2018.098)
- 2017-05-12 [RStudioでRを直感的に使おう MacOS版 2017](https://doi.org/10.7875/togotv.2017.043)

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

