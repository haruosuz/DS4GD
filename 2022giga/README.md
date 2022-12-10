# 2022giga

2022年秋学期
[生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2] (GIGA/GG/GI)](https://sol.sfc.keio.ac.jp/courses/7123)

----------

## Class Schedule & Materials
**講義日程と資料**

- [授業カレンダー](https://www.sfc.keio.ac.jp/faculty/calendars/class_calendar.html) | 
[Class Calendar](https://www.sfc.keio.ac.jp/en/faculty/calendars/class_calendar.html)
  - [春学期・秋学期授業カレンダー（2022.9.6更新）](https://www.sfc.keio.ac.jp/doc/2022_classcalendars_jp.pdf) | 
[Calendars for Spring and Fall Semesters（Update September 6, 2022）](https://www.sfc.keio.ac.jp/en/docs/2022_classcalendars_en.pdf)
- 
- 2022-10-04 No. 1 - イントロダクション Introduction
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
  - ゲノムリスト [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2021/CaseStudy.md#ncbi-genome-list)
  - [References](#references)
  - [R RStudio](#r-rstudio)
  - 課題1 [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-1)
- 2022-10-11 No. 2 - R言語入門 | Introduction to R
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_chapter_installr.R
  - 課題2 [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-2)
- 2022-10-18 No. 3 - DNA配列解析(1) | DNA Sequence Statistics (1)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_chapter1_dna1.R
  - 課題3 [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-3)
- 2022-10-25 No. 4 - DNA配列解析(2) | DNA Sequence Statistics (2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_chapter2_dna2.R
  - 課題4 [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-4)
- 2022-11-01 No. 5 - タンパク質配列データベース UniProt | ドットプロット Dotplot
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_chapter4_align.R
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast)
  - 課題5 [assignment 5](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-5)
- 2022-11-08 No. 6 - ペアワイズ配列アラインメント | Pairwise Sequence Alignment | 大域・局所アラインメント Global/Local alignment
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_chapter4_align.R
  - 課題6 [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-6)
- 2022-11-15 No. 7 - 系統と生命の樹 [Phylogeny and the Tree of Life](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_ds4gd_tree.R
  - 課題7 [assignment 7](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-7)
- 三田祭期間 Mita Festival（11/18～11/24）
- 2022-11-29 No. 8 - 中間発表 [Interim report](#interim-report)
  - 課題8 [assignment 8](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-8)
- 2022-12-06 No. 9 - 系統樹の見方 [How to read a phylogenetic tree](https://artic.network/how-to-read-a-tree.html)
  - [Download SeaView](https://doua.prabi.fr/software/seaview) 
- 2022-12-13 No. 10 - [Guest Speaker](#guest-speaker)
- 2022-12-20 No. 11 - 多重整列と系統樹 | Multiple Alignment and Phylogenetic trees
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_chapter5_msa_tree.R
  - 課題11 [assignment 11](https://github.com/haruosuz/DS4GD/blob/master/2022giga/CaseStudy.md#assignment-11)
- 2022-12-27 No. 12 - [Guest Speaker](#guest-speaker)
- 事務室閉室 Office closed (12/28～1/5)
- 2023-01-17 No. 13 - TBA
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2022giga/scripts_ds4gd.zip) my_ds4gd_2022.R
  - [NCBI BLAST](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#ncbi-blast)
- 2023-01-24 No. 14 - 最終回 final class
  - 最終発表 [Final presentation](#final-presentation)
  - 最終課題 [final assignment](https://github.com/haruosuz/DS4GD/blob/master/2022/CaseStudy.md#final-assignment)
- 試験 Exam (1/26～2/2)

----------
## interim report
**中間発表**

Presentation time is 1 minute. Report an object of interest (DNA, protein, other textual sequences, etc.).

発表時間は1分。興味のある対象（DNA、タンパク質、その他のテキスト配列など）を報告する。

----------
## Guest speaker
**[特別講演](https://www.sfc.keio.ac.jp/faculty/class/special_lecture.html)**

People outside of Keio University SFC will also attend the lectures.  
他機関所属の方も参加されます。  


### 2022-12-13
- Speaker: Dr. Mahoko Takahashi Ueda (Medical Research Institute Tokyo Medical and Dental University)  
上田真保子博士（東京医科歯科大学難治疾患研究所）
- Title: The basics of gene expression analysis in R

### 2022-12-27
- Speaker: Dr. Kirill Kryukov (National Institute of Genetics)  
キリル クリュコフ博士（国立遺伝学研究所）
- Title: Fundamentals of Big Data Sequence Analysis

----------
## Final presentation
**口頭発表**

発表時間：1人あたり最大5分（質疑応答を含む）。
興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）の解析結果を報告する。解析の例として、配列の統計（長さ、GC含量、塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、大域アラインメント、局所アラインメント）、多重整列、系統樹などが含まれる。

Presentation time: 5 minutes will be allocated for each presentation (including Q&A).
Report your main findings on analyses of objects (DNA, protein, and other textual sequences, etc.) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global alignment, and local alignment), multiple sequence alignment, and phylogenetic trees, etc.

----------
## References
**参考文献**

- Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p. https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan
  - 顧みられない熱帯病 [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)
- CAMPBELL BIOLOGY, 11th edition ; キャンベル生物学 原書11版, 丸善出版, (2018/3/20), 1704p. https://www.maruzen-publishing.co.jp/info/index.php?action=detail&news_no=19283
  - 26章 系統と生命の樹 [Phylogeny and the Tree of Life](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
-
- [How to interpret the phylogenetic trees — Nextstrain documentation](https://docs.nextstrain.org/en/latest/learn/interpret/how-to-read-a-tree.html)
- Andrew Rambaut - "How to read a phylogenetic tree", 2018-07-30 https://artic.network/how-to-read-a-tree.html
- Dave Hone - "How to read a phylogenetic tree" https://archosaurmusings.wordpress.com/2008/12/18/how-to-read-a-phylogenetic-tree/
- 2015-01-05 [PhyloBotanist: How to root a phylogenetic tree: outgroup, midpoint and other methods](http://phylobotanist.blogspot.com/2015/01/how-to-root-phylogenetic-tree-outgroup.html)
- 2012-06-07 [The Cabbages of Doom: How to root a phylogenetic tree](http://cabbagesofdoom.blogspot.com/2012/06/how-to-root-phylogenetic-tree.html)

----------
## R RStudio
- [RStudio Cloud](https://github.com/haruosuz/r4bioinfo/blob/master/references/RStudioCloud.md)
  - 2021-03-18 "RStudio Cloud を使ってウェブブラウザ上でR(Studio)を利用する" https://doi.org/10.7875/togotv.2021.022
- 2020-01-25 "R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners" https://youtu.be/YBAWVNWiZlU
- 2020-10-11 "R for Ecologists (lesson 1) Installing R and RStudio" https://youtu.be/YKvkXKeGoa8
- 2018-04-08 "統計解析ソフト「R」の使い方 〜Rの導入・パッケージの導入・作図・統計解析の基本編〜" https://doi.org/10.7875/togotv.2018.098
- 2017-05-12 "RStudioでRを直感的に使おう MacOS版 2017" https://doi.org/10.7875/togotv.2017.043
- 2014-02-21 "RStudioでRを直感的に使おう" https://doi.org/10.7875/togotv.2014.008

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

