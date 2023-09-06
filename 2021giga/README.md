# 2021giga

2021年秋学期
[生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS [DS2] (GIGA/GG/GI)](https://sol.sfc.keio.ac.jp/courses/4061)

----------

## Class Schedule & Materials
**講義日程と資料**

- [授業カレンダー](https://www.sfc.keio.ac.jp/faculty/calendars/class_calendar.html) | 
[Class Calendar](https://www.sfc.keio.ac.jp/en/faculty/calendars/class_calendar.html)
  - [秋学期授業カレンダー（2021.4.16更新）](https://www.sfc.keio.ac.jp/doc/2c6b009ba61de50f46e7f830507c41e030b1c39e.pdf) | 
[Calendar for Fall Semester（Update April 16, 2021)](https://www.sfc.keio.ac.jp/en/docs/c65c747c09c52d4eac8c05218756d184308ed72e.pdf)
- 
- 2021-10-05 No. 1 - イントロダクション Introduction
  - [References](#references)
  - [A Little Book of R For Bioinformatics](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md)
    - 顧みられない熱帯病 [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)
  - [R/RStudio](#r-rstudio)
  - 2021-10-11 23:59 課題1提出期限 Deadline for [assignment 1](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-1)
- 2021-10-12 No. 2 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#how-to-install-r-and-a-brief-introduction-to-r)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_chapter_installr.R
  - 2021-10-18 23:59 課題2提出期限 Deadline for [assignment 2](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-2)
- 2021-10-19 No. 3 - DNA配列解析(1) [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_chapter1_dna1.R
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
  - ゲノムリスト [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2021/CaseStudy.md#ncbi-genome-list)
  - 2021-10-25 23:59 課題3提出期限 Deadline for [assignment 3](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-3)
- 2021-10-26 No. 4 - DNA配列解析(2) [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-2)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_chapter2_dna2.R
  - 2021-11-01 23:59 課題4提出期限 Deadline for [assignment 4](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-4)
- 2021-11-02 No. 5 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment) | UniProt | ドットプロット Dotplot
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_chapter4_align.R
  - 配列類似性検索 [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast)
  - 2021-11-08 23:59 課題5提出期限 Deadline for [assignment 5](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-5)
- 2021-11-09 No. 6 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment) | 大域アラインメント Global alignment | 局所アラインメント Local alignment
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_chapter4_align.R
  - 2021-11-15 23:59 課題6提出期限 Deadline for [assignment 6](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-6)
- 2021-11-16 No. 7 - 中間発表 [interim report](#interim-report)
  - 2021-11-22 23:59 課題7提出期限 Deadline for [assignment 7](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-7)
- 2021-11-23 *勤労感謝の日【国民の休日】[National holiday](https://www8.cao.go.jp/chosei/shukujitsu/gaiyou.html)*
- 三田祭期間 Mita Festival（11/19～11/24）
- 2021/11/19（金）-30（火）[慶應義塾大学｜SFC Open Research Forum 2021](https://twitter.com/hashtag/ORF2021?f=live)
- 2021-11-30 No. 8 - [Guest Speaker](#guest-speaker)
  - 2021-12-06 23:59 課題8提出期限 Deadline for [assignment 8](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-8)
- 2021-12-07 No. 9 - [Guest Speaker](#guest-speaker)
  - 2021-12-13 23:59 課題9提出期限 Deadline for [assignment 9](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-9)
- 2021-12-14 No. 10 - Inferring Phylogenetic Trees
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_ds4gd_tree.R
  - 2021-12-20 23:59 課題10提出期限 Deadline for [assignment 10](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-10)
- 2021-12-21 No. 11 - 多重整列と系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
  - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_chapter5_msa_tree.R
  - 2021-12-27 23:59 課題11提出期限 Deadline for [assignment 11](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-11)
- 事務室閉室 Office closed （12/28～1/5）
- 2022-01-11 No. 12 - [scripts_ds4gd.zip](https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip) my_script2report.R
  - [Chunk options](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#chunk-options)
  - 2022-01-17 23:59 課題12提出期限 Deadline for [assignment 12](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-12)
- 2022-01-18 No. 13 No. 13 最終回 final class
  - 最終発表 [final presentation](#final-presentation)
  - 2022-01-25 23:59 課題13提出期限 Deadline for [assignment 13](https://github.com/haruosuz/DS4GD/blob/master/2021giga/CaseStudy.md#assignment-13)

----------
## Guest speaker
**[特別講演](https://www.sfc.keio.ac.jp/faculty/class/special_lecture.html)**

People outside of Keio University SFC will also attend the lectures.  
他機関所属の方も参加されます。  

Speaker: Dr. Anish MS Shrestha
アニシュ・シュレスタ博士

2021-11-30 (Tue) 11:10-12:40
Title: ["Data-structures for fast sequence analysis"](https://github.com/haruosuz/DS4GD/blob/master/2021giga/guest-speaker/2021-11-30/Data_structures_20211130.pdf)

2021-12-07 (Tue) 11:10-12:40
Title: ["DNA-protein alignment for functional genomics of non-model organisms"](https://github.com/haruosuz/DS4GD/blob/master/2021giga/guest-speaker/2021-12-07/non_model_organisms_rna_seq_20211207.pdf)

----------
## interim report
**中間発表**

One minute will be allocated for each presentation. Please report objects (DNA, protein, and other textual sequences, etc.) you're interested in.

1人あたり最大1分で興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を報告する。

----------
## final presentation
**最終発表**

Presentation time: 10 minutes will be allocated for each presentation (including Q&A).
Report your main findings on analyses of objects (DNA, protein, and other textual sequences, etc.) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global alignment, and local alignment), multiple sequence alignment, and phylogenetic trees, etc.

発表時間：1人あたり最大10分（質疑応答を含む）。
興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）の解析結果を報告する。解析の例として、配列の統計（長さ、GC含量、塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、大域アラインメント、局所アラインメント）、多重整列、系統樹などが含まれる。

----------
## References
**参考文献**

- Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p. https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan
- Nextstrain / Genomic epidemiology of novel coronavirus - Global subsampling https://nextstrain.org/ncov/global
- 2021-08-05 ["How Urban Microbiomes Contribute to the Ecology of City Life"](https://asm.org/Articles/2021/August/How-Urban-Microbiomes-Contribute-to-the-Ecology-of)
- [Rob DeSalle, Ian Tattersall - "A Natural History of Beer", 2019, 256p.](https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99393943804031) https://yalebooks.yale.edu/book/9780300233674/natural-history-beer
- [David Quammen - "The Tangled Tree", 2018/9/6, 480p.](https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma9926392103104034)
- Savage et al. (2018) "Quantitative evaluation of music copyright infringement." http://fma2018.mus.auth.gr/files/papers/FMA2018_paper_4.pdf
- Barbrook, A., Howe, C., Blake, N. et al. The phylogeny of The Canterbury Tales. Nature 394, 839 (1998). https://doi.org/10.1038/29667

----------
### R RStudio
- 2020/01/25 "R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners" https://youtu.be/YBAWVNWiZlU
- 2020/10/11 "R for Ecologists (lesson 1) Installing R and RStudio" https://youtu.be/YKvkXKeGoa8
- 2018-04-08 "統計解析ソフト「R」の使い方 〜Rの導入・パッケージの導入・作図・統計解析の基本編〜" https://doi.org/10.7875/togotv.2018.098
- 2017-05-12 "RStudioでRを直感的に使おう MacOS版 2017" https://doi.org/10.7875/togotv.2017.043

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

