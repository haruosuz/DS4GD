# 2024-10

生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2]  
[K-LMS](https://lms.keio.jp/courses/102414)  
[Syllabus](https://syllabus.sfc.keio.ac.jp/courses/2024_25381)

----------

## Class Schedule & Materials
**講義日程と資料**

- [授業カレンダー](https://www.sfc.keio.ac.jp/contact/class_calendar.html) | Class Calendar
  - [2024年度 SFC授業カレンダー（2024.8.5更新）](https://www.sfc.keio.ac.jp/doc/2024_classcalendars_jp.pdf) | https://www.sfc.keio.ac.jp/en/docs/2024_classcalendars_en.pdf
- [References](#references)
- 2024-10-01 No. 1 - イントロダクション Introduction
  - [R RStudio](#r-rstudio)
  - 課題1 [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-1)
- 2024-10-08 No. 2 - R言語入門 Introduction to R
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter_installr.R
  - 課題2 [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-2) my_setup_packages.R
- 2024-10-15 No. 3 - DNA配列解析(1) DNA Sequence Statistics (1)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter1_dna1.R | my_test1_dna.R
  - 課題3 [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-3) my_assignment_chapter1_dna1.R
  - [NCBI Datasets](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-datasets)
- 2024-10-22 No. 4 - DNA配列解析(2) DNA Sequence Statistics (2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter2_dna2.R | my_test2_kmer.R
  - 課題4 [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-4) my_assignment_chapter2_dna2.R
- 2024-10-29 No. 5 - タンパク質配列データベース UniProt | ドットプロット Dotplot
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter4_align.R | my_test3_dotplot.R
  - 課題5 [assignment 5](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-5) my_assignment_chapter4_align_dotplot.R
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#blast)
- 2024-11-05 No. 6 - ペアワイズ配列アラインメント Pairwise Sequence Alignment
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter4_align.R
  - 課題6 [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-6) my_assignment_chapter4_align_pairwise.R
- 2024-11-12 No. 7 - TBA - Newick tree format | Model
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_ds4gd_newick.R | my_ds4gd_model.R
  - 課題7 [assignment 7](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-7) my_tree_aa.R
- 三田祭期間 Mita Festival（2024-11-19 ～ 2024-11-25）
- 2024-12-03 No. 8 - TBA
  - 課題8 [assignment 8](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-8) my_ds4gd_report.R
- 2024-12-10 No. 9 - TBA
- 2024-12-17 No. 10 - TBA
- 2024-12-24 No. 11 - TBA
- 湘南藤沢キャンパス一斉休業 Office closed（12/28～1/4）
- 2025-01-07 No. 12 - 多重整列と系統樹 Multiple Alignment and Phylogenetic trees
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter5_msa_tree.R
  - 課題12 [assignment 12](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-12) my_assignment_chapter5_msa_tree.R
- 2025-01-14 No. 13 - Text formatting with Markdown
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_script2report/my_script2report.R
  - [Chunk options](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#chunk-options)
  - 相同性のテスト [Test the homology](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-blast)
  - 有根系統樹と無根系統樹 (Rooted and Unrooted Phylogenetic Trees) | 外群 (Outgroup)
- 2025-01-21 No. 14 - 最終回 final class
  - 最終課題 [assignment final](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-final)

----------
## Guest speaker
**特別講演**

People outside of Keio University SFC will also attend the lectures.  
他機関所属の方も参加されます。  


----------
## References
**参考文献**

- 2011-06-10 Avril Coghlan - "A Little Book of R For Bioinformatics" https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan
- CAMPBELL BIOLOGY, 11th edition ; キャンベル生物学 原書11版, 丸善出版, (2018/3/20), 1704p. https://www.maruzen-publishing.co.jp/info/index.php?action=detail&news_no=19283
  - 26章 系統と生命の樹 [Phylogeny and the Tree of Life](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)

----------
## R RStudio

- [Posit Cloud (formerly RStudio Cloud)](https://github.com/haruosuz/r4bioinfo/blob/master/references/RStudioCloud.md)
  - 2021-03-18 | 04:00 | "RStudio Cloud を使ってウェブブラウザ上でR(Studio)を利用する" https://doi.org/10.7875/togotv.2021.022
- 2023/02/01 | Equitable Equations | Learn R in 39 minutes | https://www.youtube.com/watch?v=yZ0bV2Afkjc
- 2021/02/16 | 5:23 | R Programming - DDS | "How to download and install R and RStudio" https://youtu.be/TFGYlKvQEQ4
- 2020-01-25 | 5:17 | Pydemy | "R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners" https://youtu.be/YBAWVNWiZlU
- 2020-10-11 | 6:00 | R for Ecology | "R for Ecologists (lesson 1) Installing R and RStudio" https://youtu.be/YKvkXKeGoa8
- 2018-04-08 | 5:18 | "統計解析ソフト「R」の使い方 〜Rの導入・パッケージの導入・作図・統計解析の基本編〜" https://doi.org/10.7875/togotv.2018.098
- 2017-05-12 | 7:42 | "RStudioでRを直感的に使おう MacOS版 2017" https://doi.org/10.7875/togotv.2017.043
- 2014-02-21 | 11:06 | "RStudioでRを直感的に使おう" https://doi.org/10.7875/togotv.2014.008

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

