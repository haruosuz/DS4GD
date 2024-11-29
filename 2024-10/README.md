# 2024-10

生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2]  
[K-LMS](https://lms.keio.jp/courses/102414)  
[Syllabus](https://syllabus.sfc.keio.ac.jp/courses/2024_25381)

----------

## Class Schedule & Materials
**講義日程と資料**

- [2024年度授業カレンダー_Class calendar for the year AY 2024.pdf](https://keio.box.com/s/cbc8kqhls14qc5wba354gynmovqdpm8e)
- [References](#references)
- 2024-10-01 No. 1 - イントロダクション Introduction
  - [R RStudio](#r-rstudio)
  - 課題1 [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-1)
- 2024-10-08 No. 2 - R言語入門 Introduction to R
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter_installr.R
  - 課題2 [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-2)
- 2024-10-15 No. 3 - DNA配列解析(1) DNA Sequence Statistics (1)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter1_dna1.R | my_test1_dna.R
  - 課題3 [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-3)
  - [NCBI Datasets](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-datasets)
- 2024-10-22 No. 4 - DNA配列解析(2) DNA Sequence Statistics (2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter2_dna2.R | my_test2_kmer.R
  - 課題4 [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-4)
- 2024-10-29 No. 5 - タンパク質配列データベース UniProt | ドットプロット Dotplot
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter4_align.R | my_test3_dotplot.R
  - 課題5 [assignment 5](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-5)
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#blast)
- 2024-11-05 No. 6 - ペアワイズ配列アラインメント Pairwise Sequence Alignment
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter4_align.R
  - 課題6 [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-6)
- 2024-11-12 No. 7 - 相同性のテスト [Test the homology](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-blast)
  - 課題7 [assignment 7](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-7) my_ds4gd_report.R
- 2024-11-19 補講 Makeup Class Day | No. 8 - 多重置換 Multiple Substitutions | 進化距離 Evolutionary Distances
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_ds4gd_model.R
- 2024-11-19 ～ 2024-11-25 三田祭（準備・片付） Mita Festival (Prep / clean up)
- 2024-11-26 [SFC（総・環・政メ）は通常の授業なし No regular classes at SFC (PM,EI,MG)](https://keio.box.com/s/cbc8kqhls14qc5wba354gynmovqdpm8e)
- 2024-12-03 No. 9 - [Online] [Guest Speaker](#guest-speaker)
  - 課題9 [assignment 9](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-9)
- 2024-12-10 - 休講 no class
- 2024-12-17 No. 10 - TBA
- 2024-12-24 No. 11 - TBA
- 湘南藤沢キャンパス一斉休業 Office closed（12/28～1/4）
- 2025-01-07 No. 12 - 多重整列と系統樹 Multiple Alignment and Phylogenetic trees
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-10/scripts_ds4gd.zip) my_chapter5_msa_tree.R
  - 課題12 [assignment 12](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-12) my_assignment_chapter5_msa_tree.R
- 2025-01-14 No. 13 - TBA
- 2025-01-21 No. 14 - 最終回 final class
  - 最終課題 [assignment final](https://github.com/haruosuz/DS4GD/blob/master/2024-10/CaseStudy.md#assignment-final)

----------
## Guest speaker
**特別講演**

People outside of Keio University SFC will also attend the lectures.  
他機関所属の方も参加されます。  

### 2024-12-03
- Speaker: Dr. Jun Inoue (The University of Tokyo)  
井上 潤 博士（東京大学）
- Website: https://fish-evol.org/
- Slides: [分子系統解析 Molecular Phylogenetic Analysis](https://yurai.aori.u-tokyo.ac.jp/slide_keio24/20241203_inoue_keiko.pdf)

----------
## References
**参考文献**

- [2011-06-10 Avril Coghlan - "A Little Book of R For Bioinformatics"](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- [CAMPBELL BIOLOGY, 11th edition ; キャンベル生物学 原書11版, 丸善出版, (2018/3/20), 1704p.](https://www.maruzen-publishing.co.jp/info/index.php?action=detail&news_no=19283)
  - 26章 系統と生命の樹 [Phylogeny and the Tree of Life (pdf)](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
- [Ziheng Yang - Computational Molecular Evolution (Oxford Series in Ecology and Evolution), Oxford University Press (2006/12/7), 374p.](http://abacus.gene.ucl.ac.uk/CME/) | [Table of Contents](http://abacus.gene.ucl.ac.uk/CME/TableOfContents.pdf)
  - [藤 博幸　加藤 和貴　大安 裕美　訳. 分子系統学への統計的アプローチ ―計算分子進化学―, 共立出版, 2009.3, 360p.](https://www.kyoritsu-pub.co.jp/book/b10010733.html) | [詳細目次（pdf）](https://kyoritsu-pub.sakura.ne.jp/app/file/goods_contents/1152.pdf)

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

