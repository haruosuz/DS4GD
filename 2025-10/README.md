# 2025-10

生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2]  
[K-LMS](https://lms.keio.jp/courses/124135)  
[Syllabus](https://gslbs.keio.jp/syllabus/detail?ttblyr=2025&entno=12811&lang=en)

----------

## Class Schedule & Materials
**講義日程と資料**

- [授業カレンダー](https://www.sfc.keio.ac.jp/contact/class_calendar.html) | [Class Calendar](https://www.sfc.keio.ac.jp/en/contact/class_calendar.html)
  - [2025年度 SFC授業カレンダー（2024.11.26更新）](https://www.sfc.keio.ac.jp/doc/2025_classcalendars_jp.pdf) | [SFC Calendars for 2025（Update November 26, 2024）](https://www.sfc.keio.ac.jp/en/docs/2025_classcalendars_en.pdf)
- 2025-10-07 No. 1 - イントロダクション Introduction
  - [R RStudio](#r-rstudio)
  - 課題1 [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-1)
- 2025-10-14 No. 2 - R言語入門 Introduction to R
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2025-10/scripts_ds4gd.zip) my_chapter_installr.R
  - 課題2 [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-2) my_setup_packages.R
- 2025-10-21 No. 3 - DNA配列解析(1) DNA Sequence Statistics (1)
  - [NCBI Datasets](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-datasets)
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#genome-signature)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2025-10/scripts_ds4gd.zip) my_chapter1_dna1.R
  - 課題3 [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-3)
- 2025-10-28 No. 4 - DNA配列解析(2) DNA Sequence Statistics (2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2025-10/scripts_ds4gd.zip) my_chapter2_dna2.R
  - 課題4 [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-4)
- 2025-11-04 No. 5 - タンパク質配列データベース UniProt | ドットプロット Dotplot
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#blast)
- 2025-11-11 No. 6 - ペアワイズ配列アラインメント Pairwise Sequence Alignment
  - 課題6 [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-6)
- 2025-11-18 No. 7 - 相同性のテスト [Test the homology](https://github.com/haruosuz/DS4GD/blob/master/CaseStudy.md#ncbi-blast)
- 2025-11-19 ～ 2025-11-25 三田祭（準備・片付） Mita Festival (Prep / clean up)
- 2025-12-02 No. 8 - TBD
- 2025-12-09 No. 9 - [Online] [Guest Speaker](#guest-speaker)
- 2025-12-16 No. 10 - [Online] [Guest Speaker](#guest-speaker)
- 2025-12-23 No. 11 - TBD
- 湘南藤沢キャンパス一斉休業 Office closed（12/29～1/4）
- 2026-01-06 No. 12 - 多重整列と系統樹 Multiple Alignment and Phylogenetic trees
  - 課題12 [assignment 12](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-12)
- 2026-01-13 No. 13 - 質疑応答 Q&A
  - 最終課題 [assignment final](https://github.com/haruosuz/DS4GD/blob/master/2025-10/CaseStudy.md#assignment-final)
- 2026-01-20 No. 14 - 最終回 final class

----------
## Guest speaker
**特別講演**

- Speaker: Dr. Rumiko Suzuki (National Institute of Genetics)  
鈴木 留美子 博士（国立遺伝学研究所）
- Title: Inference of divergence times on bacterial phylogenetic trees									

----------
## References
**参考文献**

- [2011-06-10 Avril Coghlan - "A Little Book of R For Bioinformatics"](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- [CAMPBELL BIOLOGY, 11th edition ; キャンベル生物学 原書11版, 丸善出版, (2018/3/20), 1704p.](https://www.maruzen-publishing.co.jp/book/b10112384.html)
  - 26章 系統と生命の樹 [Phylogeny and the Tree of Life (pdf)](https://www.maruzen-publishing.co.jp/files/書籍営業部/講義用資料/2018/キャンベル11授業用パワポサンプル26_Lecture_Presentation.pdf)
- [Ziheng Yang - Computational Molecular Evolution (Oxford Series in Ecology and Evolution), Oxford University Press (2006/12/7), 374p.](http://abacus.gene.ucl.ac.uk/CME/) | [Table of Contents](http://abacus.gene.ucl.ac.uk/CME/TableOfContents.pdf)

----------
## R RStudio

- [Posit Cloud (formerly RStudio Cloud)](https://github.com/haruosuz/r4bioinfo/blob/master/references/RStudioCloud.md)
  - 2023.12.12 | 52:32 | "Posit Cloud (旧：RStudio Cloud) を用いて生物配列データ解析に取り組む @ AJACSオンライン18" https://doi.org/10.7875/togotv.2023.087
  - 2021-03-18 | 04:00 | "RStudio Cloud を使ってウェブブラウザ上でR(Studio)を利用する" https://doi.org/10.7875/togotv.2021.022
- 2023/02/01 | Equitable Equations | Learn R in 39 minutes https://www.youtube.com/watch?v=yZ0bV2Afkjc
- 2022/07/12 | 20:20 | 白黒パンダの統計教室 | 基礎から始める　R言語を使った統計解析　第１回『RとRstudioのインストールと初期設定』 https://www.youtube.com/watch?v=vdTte2Wsx1I
- 2022/04/17 | 13:01 | 三木 健miki takeshi | RStudioで広がる統計解析：RStudioのインストール https://www.youtube.com/watch?v=GtR1qCB-tfc
- 2021/02/16 | 5:23 | R Programming - DDS | "How to download and install R and RStudio" https://youtu.be/TFGYlKvQEQ4
- 2020-01-25 | 5:17 | Pydemy | "R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners" https://youtu.be/YBAWVNWiZlU
- 2020-10-11 | 6:00 | R for Ecology | "R for Ecologists (lesson 1) Installing R and RStudio" https://youtu.be/YKvkXKeGoa8
- 2019/08/27 [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)
- 2018.04.08 | 5:18 | "統計解析ソフト「R」の使い方 〜Rの導入・パッケージの導入・作図・統計解析の基本編〜" https://doi.org/10.7875/togotv.2018.098
- 2017.05.12 | 7:42 | "RStudioでRを直感的に使おう MacOS版 2017" https://doi.org/10.7875/togotv.2017.043
- 2014.02.21 | 11:06 | "RStudioでRを直感的に使おう" https://doi.org/10.7875/togotv.2014.008

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

