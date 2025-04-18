# 2024-04

生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2]  
[K-LMS](https://lms.keio.jp/courses/91203)  
[Syllabus](https://syllabus.sfc.keio.ac.jp/courses/2024_41550)

----------

## Class Schedule & Materials
**講義日程と資料**

- [授業カレンダー](https://www.sfc.keio.ac.jp/contact/class_calendar.html) | Class Calendar
  - [2024年度 SFC授業カレンダー（2023.12.11更新）](https://www.sfc.keio.ac.jp/doc/2024_classcalendars_jp.pdf) | https://www.sfc.keio.ac.jp/en/docs/2024_classcalendars_en.pdf
- [References](#references)
- 2024-04-09 No. 1 - イントロダクション Introduction
  - [R RStudio](#r-rstudio)
  - 課題1 [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-1)
- 2024-04-16 No. 2 - R言語入門 Introduction to R
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_chapter_installr.R
  - 課題2 [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-2)
  - よくわかるバイオインフォマティクス入門 | 1章　配列解析
- 2024-04-23 No. 3 - DNA配列解析(1) DNA Sequence Statistics (1)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_chapter1_dna1.R | my_test1_dna.R
  - 課題3 [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-3)
  - [NCBI Datasets](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-datasets)
  - よくわかるバイオインフォマティクス入門 | 6章　ゲノム解析 | ゲノムの特徴 | ゲノムサイズ | GC含量 (GC content)
- 2024-04-30 No. 4 - DNA配列解析(2) DNA Sequence Statistics (2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_chapter2_dna2.R
  - 課題4 [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-4)
  - よくわかるバイオインフォマティクス入門 | 6章　ゲノム解析 | スライデイングウインドウ (sliding window)
- 2024-05-07 No. 5 - タンパク質配列データベース UniProt | ドットプロット Dotplot
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_chapter4_align.R
  - 課題5 [assignment 5](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-5)
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#blast)
  - よくわかるバイオインフォマティクス入門 | 1章　配列解析 | 変異と置換および分子進化 | 6章　ゲノム解析 | ドットプロット (dotplot)
- 2024-05-14 No. 6 - ペアワイズ配列アラインメント Pairwise Sequence Alignment
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_chapter4_align.R
  - 課題6 [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-6)
  - よくわかるバイオインフォマティクス入門 | 1章　配列解析 | 配列データベースと配列検索 | 配列アラインメント | ペアワイズアラインメント
- 2024-05-21 No. 7 - 系統と生命の樹 [Phylogeny and the Tree of Life](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
  - 課題7 [assignment 7](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-7)
- 2024-05-25（土曜日）13:00～ 補講
- 2024-05-28 No. 8 - 分子系統解析 | 有根系統樹と無根系統樹 | 外群 (outgroup)
  - 課題8 [assignment 8](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-8)
  - よくわかるバイオインフォマティクス入門 | 2章　分子進化 | 分子系統樹
- 2024-06-04 休講 no class |
[補講/試験](https://www.sfc.keio.ac.jp/doc/2024_classcalendars_jp.pdf)
[Makeup Class Day/Exam](https://www.sfc.keio.ac.jp/en/docs/2024_classcalendars_en.pdf)
- 2024-06-11 No. 9 - [Guest Speaker](#guest-speaker) 松井 求 博士（東京大学）系統解析の過去・現在・未来
  - 課題9 [assignment 9](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-9)
- 2024-06-18 No. 10 - 都市のマイクロバイオーム Urban Microbiome
  - 課題10 [assignment 10](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-10)
- 2024-06-21 (金) 6限 [Global City Sampling Day (gCSD)](https://github.com/haruosuz/metasub/blob/master/README.md#csd)
- 2024-06-25 No. 11 - [Guest Speaker](#guest-speaker) 鈴木 留美子 博士（国立遺伝学研究所）細菌集団の分析方法
  - 課題11 [assignment 11](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-11)
- 2024-07-02 No. 12 - 多重整列と系統樹 Multiple Alignment and Phylogenetic trees
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_chapter5_msa_tree.R
  - 課題12 [assignment 12](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-12)
- 2024-07-09 No. 13 - Text formatting with Markdown
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2024-04/scripts_ds4gd.zip) my_script2report/my_script2report.R
  - [Chunk options](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#chunk-options)
  - 相同性のテスト [Test the homology](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-blast)
  - よくわかるバイオインフォマティクス入門 | 1章　配列解析 | 相同 (homologous) | 2章　分子進化 | オーソロガスおよびパラロガスな遺伝子の関係
- 2024-07-16 No. 14 - 最終回 final class
  - 最終課題 [assignment final](https://github.com/haruosuz/DS4GD/blob/master/2024-04/CaseStudy.md#assignment-final)
- 2024-07-18 2024-07-20 補講

----------
## Guest speaker
**特別講演**

People outside of Keio University SFC will also attend the lectures.  
他機関所属の方も参加されます。  


### 2024-06-11
- Speaker: Dr. Motomu Matsui (The University of Tokyo)  
松井 求 博士（東京大学）
- Title: [系統解析の過去・現在・未来](https://drive.google.com/file/d/1MbHO7VPEqi93eczxWqElsvyWHnjgOODO/view?usp=drive_link)

### 2024-06-25
- Speaker: Dr. Rumiko Suzuki (National Institute of Genetics)  
鈴木 留美子 博士（国立遺伝学研究所）
- Title: 細菌集団の分析方法

'MEGA 11'をダウンロードしてください。
Please download 'MEGA 11'.
https://www.megasoftware.net/

MLST配列
http://sayer.nig.ac.jp/rusuzuki/keio/Asia-Okinawa_newname.fas
ファイル名を「Asia-Okinawa.fas」として保存

距離行列データ
http://sayer.nig.ac.jp/rusuzuki/keio/Distance_matrix.csv

距離行列データ完成形
http://sayer.nig.ac.jp/rusuzuki/keio/Distance_matrix_comp.csv

PCAプロット用カラーデータ
http://sayer.nig.ac.jp/rusuzuki/keio/dotcolors.csv

----------
## References
**参考文献**

- 2011-06-10 Avril Coghlan - "A Little Book of R For Bioinformatics" https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan
- 2018-11-19 藤博幸（編） - よくわかるバイオインフォマティクス入門 https://www.kspub.co.jp/book/detail/5138212.html | 1章　配列解析 | 2章　分子進化 | 6章　ゲノム解析
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

