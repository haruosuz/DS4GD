# 2023-04

2023 Spring
[生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2]](https://sol.sfc.keio.ac.jp/courses/8517)

----------

## Class Schedule & Materials
**講義日程と資料**

- [授業カレンダー](https://www.sfc.keio.ac.jp/faculty/calendars/class_calendar.html) | 
[Class Calendar](https://www.sfc.keio.ac.jp/en/faculty/calendars/class_calendar.html)
  - [2023年度 SFC授業カレンダー（2022.12.27更新）](https://www.sfc.keio.ac.jp/doc/2023_classcalendars_jp.pdf) | 
[SFC Calendars for 2023（Update December 27, 2022）](https://www.sfc.keio.ac.jp/en/docs/2023_classcalendars_en.pdf)
- 
- 2023-04-11 No. 1 - イントロダクション Introduction
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
  - ゲノムリスト [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2021/CaseStudy.md#ncbi-genome-list)
  - [References](#references)
  - [R RStudio](#r-rstudio)
  - 課題1 [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-1)
- 2023-04-18 No. 2 - R言語入門 | Introduction to R
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_chapter_installr.R
  - 課題2 [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-2)
- 2023-04-25 No. 3 - DNA配列解析(1) DNA Sequence Statistics (1)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_chapter1_dna1.R
  - 課題3 [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-3)
- 2023-05-02 No. 4 - DNA配列解析(2) DNA Sequence Statistics (2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_chapter2_dna2.R
  - 課題4 [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-4)
- 2023-05-09 No. 5 - タンパク質配列データベース UniProt | ドットプロット Dotplot
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_chapter4_align.R
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast)
  - 課題5 [assignment 5](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-5)
- 2023-05-16 No. 6 - ペアワイズ配列アラインメント Pairwise Sequence Alignment
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_chapter4_align.R
  - 課題6 [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-6)
- 2023-05-23 No. 7 - 系統と生命の樹 [Phylogeny and the Tree of Life](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_ds4gd_tree.R
  - 課題7 [assignment 7](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-7)
- 2023-05-30 No. 8 - 系統樹の見方 [How to read a phylogenetic tree](https://artic.network/how-to-read-a-tree.html)
  - 中間発表 [midterm presentation](#midterm-presentation)
  - 課題8 [assignment 8](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-8)
- 6/2 6/3 金 土 Fri. Sat. - 補講/試験 Makeup Class Day/Exam
- 2023-06-06 No. 9 - [よくわかるバイオインフォマティクス入門](https://www.kspub.co.jp/book/detail/5138212.html) 1章　配列解析 | 2章　分子進化 | 6章　ゲノム解析
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_sliding_window_gcskew.R | my_ds4gd_model.R  
- 2023-06-13 No. 10 - Newick tree format
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_ds4gd_newick.R
- 2023-06-20 No. 11 - 多重整列と系統樹 | Multiple Alignment and Phylogenetic trees
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_chapter5_msa_tree.R
  - 課題11 [assignment 11](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#assignment-11)
- 2023-06-27 No. 12 - 系統樹に根をつける方法 [How to root a phylogenetic tree](http://cabbagesofdoom.blogspot.com/2012/06/how-to-root-phylogenetic-tree.html)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2023-04/scripts_ds4gd.zip) my_script2report.R | my_ds4gd_report_2023-06-27.R namespace
- 2023-07-04 No. 13 - TBA
- 2023-07-11 No. 14 - 最終回 final class
  - 最終発表 [final presentation](#final-presentation)
  - 最終課題 [final assignment](https://github.com/haruosuz/DS4GD/blob/master/2023-04/CaseStudy.md#final-assignment)

----------
## midterm presentation
**中間発表**

Presentation time is 1 minute. Report an object of interest (DNA, protein, other textual sequences, etc.).

発表時間は1分。興味のある対象（DNA、タンパク質、その他のテキスト配列など）を報告する。

----------
## final presentation
**口頭発表**

発表時間：1人あたり最大5分（質疑応答を含む）。
興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）の解析結果を報告する。解析の例として、配列の統計（長さ、GC含量、塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、大域アラインメント、局所アラインメント）、多重整列、系統樹などが含まれる。

Presentation time: 5 minutes will be allocated for each presentation (including Q&A).
Report your main findings on analyses of objects (DNA, protein, and other textual sequences, etc.) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global alignment, and local alignment), multiple sequence alignment, and phylogenetic trees, etc.

----------
## References
**参考文献**

- CAMPBELL BIOLOGY, 11th edition ; キャンベル生物学 原書11版, 丸善出版, (2018/3/20), 1704p. https://www.maruzen-publishing.co.jp/info/index.php?action=detail&news_no=19283
  - 26章 系統と生命の樹 [Phylogeny and the Tree of Life](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
- 藤博幸（編） - よくわかるバイオインフォマティクス入門, 講談社サイエンティフィク, 2018, 199p. https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/fb8nrm/alma9926580096704034
- Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p. https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan
  - 顧みられない熱帯病 [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)
- 
- Andrew Rambaut - "How to read a phylogenetic tree", 2018-07-30 https://artic.network/how-to-read-a-tree.html
- 2012-06-07 The Cabbages of Doom: How to root a phylogenetic tree http://cabbagesofdoom.blogspot.com/2012/06/how-to-root-phylogenetic-tree.html

----------
## R RStudio
- [RStudio Cloud](https://github.com/haruosuz/r4bioinfo/blob/master/references/RStudioCloud.md)
  - 2021-03-18 | 04:00 | "RStudio Cloud を使ってウェブブラウザ上でR(Studio)を利用する" https://doi.org/10.7875/togotv.2021.022
- 2021/02/16 | 5:23 | R Programming - DDS | "How to download and install R and RStudio" https://youtu.be/TFGYlKvQEQ4
- 2020-01-25 | 5:17 | Pydemy | "R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners" https://youtu.be/YBAWVNWiZlU
- 2020-10-11 | 6:00 | R for Ecology | "R for Ecologists (lesson 1) Installing R and RStudio" https://youtu.be/YKvkXKeGoa8
- 2018-04-08 | 5:18 | "統計解析ソフト「R」の使い方 〜Rの導入・パッケージの導入・作図・統計解析の基本編〜" https://doi.org/10.7875/togotv.2018.098
- 2017-05-12 | 7:42 | "RStudioでRを直感的に使おう MacOS版 2017" https://doi.org/10.7875/togotv.2017.043
- 2014-02-21 | 11:06 | "RStudioでRを直感的に使おう" https://doi.org/10.7875/togotv.2014.008

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

