[Keio University Shonan Fujisawa Campus](https://www.sfc.keio.ac.jp/en/) (SFC)
教室 Classroom [λ21](http://classroom.sfc.keio.ac.jp/class/l-to/l-21.html)  
2020 Spring Tuesday 3rd Period  
2020年度 春学期 火曜日[3時限 13：00～14：30](https://www.sfc.keio.ac.jp/faculty/class/class.html#1)  

# DS4GD
DATA SCIENCE FOR GENOME DYNAMICS
[Syllabus](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2020_41550&ks=B3206&key=524a8f15be61c8e20481031f349fcc8f&lang=en)  
生命動態のデータサイエンス[DS2]
[シラバス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2020_41550&ks=B3206&key=524a8f15be61c8e20481031f349fcc8f&lang=ja)  

## References
**参考文献**
- [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- [Hadley Wickham, Garrett Grolemund - R for Data Science, 2016, 520p.](https://github.com/haruosuz/books/tree/master/r4ds)

## Class Schedule & Materials
**講義日程と資料**

[[UPDATED] Calendar for Spring Semester 2020](https://www.sfc.keio.ac.jp/en/docs/681a9a34e5cb149a55e3780977a9b59f366781ec.pdf) |
[【変更後】 2020年度 春学期授業カレンダー](https://www.sfc.keio.ac.jp/doc/82bacea42ef958c454eb0044be552fc00dbb7952.pdf)

- 2020-05-05 No. 1 - イントロダクション [Introduction](#introduction)
- 2020-05-12 No. 2 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#how-to-install-r-and-a-brief-introduction-to-r)
- 2020-05-19 No. 3 - DNA配列解析(1) [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
- 2020-05-26 No. 4 - DNA配列解析(2) [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-2)
- 2020-06-02 No. 5 - [Guest Speaker](#guest-speaker)
- 2020-06-09 No. 6 - [Guest Speaker](#guest-speaker)
- 2020-06-16 No. 7 - [Guest Speaker](#guest-speaker)
- 2020-06-23 No. 8 - Case Study
- 2020-06-30 No. 9 - 中間発表 [interim report](#interim-report)
  - タンパク質データベース Protein sequence database [UniProt](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#uniprot)
  - ドットプロット [dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)
- 2020-07-07 No. 10 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
  - 2つのDNA配列間のグローバル・アライメント [Pairwise global alignment of DNA sequences](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
- 2020-07-14 No. 11 - 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
- 2020-07-21 No. 12 - 最終回
  - 最終発表 [final presentation](https://github.com/haruosuz/DS4GD/blob/master/2019giga/CaseStudy.md#assignment-14)
- 2020-07-28 レポート提出期限 Deadline for [final report](#final-report)
- [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2019giga/CaseStudy.md)

----------
## Guest speaker
**[特別講演](https://www.sfc.keio.ac.jp/faculty/class/special_lecture.html)**

----------
## interim report
**中間発表**

5 minutes will be allocated for each presentation, including presentation and discussion.

----------
## final report
**レポート**

Submit your final report (PDF/HTML document from R Markdown, Jupyter Notebook, etc.)

- [IMRAD](https://en.wikipedia.org/wiki/IMRAD) (Introduction, Methods, Results, and Discussion)

----------

## Introduction
### [Bioinformatics](http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about)

### [Bioinformatician](https://www.biostars.org/p/223069/)

### [Bioinformatics Research](https://github.com/haruosuz/books/blob/master/bbs/README.md#13-principal-applications-of-bioinformatics)

#### [Molecular phylogenetics](https://en.wikipedia.org/wiki/Molecular_phylogenetics)
**[分子系統学](https://ja.wikipedia.org/wiki/分子系統学)**

- [Washburne et al. (2018) Nat Microbiol. 3(6):652-661. "Methods for phylogenetic analysis of microbiome data."](https://www.nature.com/articles/s41564-018-0156-0)
- [Nextstrain](https://github.com/haruosuz/microbe/blob/master/references/microbe.COVID-19.md#nextstrain)
Real-time tracking of pathogen evolution
ゲノム配列データに基づいて病原体の進化と伝播をリアルタイムで追跡

<img src="https://i.gzn.jp/img/2020/03/31/nextstrain-covid19-report/00_m.png" width=25%>

#### [Microbiomes of the built environment](https://en.wikipedia.org/wiki/Microbiomes_of_the_built_environment)
**人工環境の微生物群集**

- July 2011 TED Talk 5:18 [Jessica Green: Are we filtering the wrong microbes?](https://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes) | [ジェシカ・グリーン「微生物を正しく取り除くために」](http://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes?language=ja)
- 新型コロナウイルス感染症：人工環境で感染を減らすには [Dietz et al. (2020) "2019 Novel Coronavirus (COVID-19) Pandemic: Built Environment Considerations To Reduce Transmission."](https://msystems.asm.org/content/5/2/e00245-20)

FIG 1
Structure of SARS-CoV-2 virus.  
![](https://msystems.asm.org/content/msys/5/2/e00245-20/F1.small.gif)

FIG 2
Conceptualization of SARS-CoV-2 deposition.  
![https://msystems.asm.org/content/5/2/e00245-20](https://msystems.asm.org/content/msys/5/2/e00245-20/F2.small.gif)

#### [MetaSUB](http://metasub.org/media-2/)
**[MetaSUB: Metagenomics & Metadesign of Subways & Urban Biomes](https://github.com/haruosuz/metasub/blob/master/README.md)**

- ["NYC Scientists Swab the Subway in Search of SARS-CoV-2." Is it there? So far, nope! Environmental and ongoing clinical #COVID19 efforts discussed here:](https://twitter.com/mason_lab/status/1245394591819477003)
ニューヨークの地下鉄で新型コロナウイルス（SARS-CoV-2）は今のところ見つかっていない。10％はヒトRNA、1～2％はウイルスRNA（インフルエンザウイルスを含む）、残りの88％は由来不明。

<img src="https://pbs.twimg.com/card_img/1251224380496941056/OcnxbVDI?format=jpg&name=small" width=25%>

#### Antibiotic resistance
**[抗生物質耐性](https://ja.wikipedia.org/wiki/抗微生物薬耐性)**

- TED-Ed [What causes antibiotic resistance? - Kevin Wu](https://ed.ted.com/lessons/how-antibiotics-become-resistant-over-time-kevin-wu) | [抗生物質に対する耐性が生まれるのはなぜか？ - ケビン・ウー](https://amara.org/en/videos/VllmqrFumzGt/ja/812239/)

- [The evolution of antibiotic resistance | Science](https://science.sciencemag.org/content/365/6458/1082)

![](https://science.sciencemag.org/content/sci/365/6458/1082/F1.medium.gif)

#### [Plasmid](https://en.wikipedia.org/wiki/Plasmid)
**[プラスミド](https://ja.wikipedia.org/wiki/プラスミド)**

![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Plasmid_%28english%29.svg/200px-Plasmid_%28english%29.svg.png)

- [抗生物質が効かない悪魔のスーパーバグがどれくらい怖い存在なのか理解できるムービー「The Antibiotic Apocalypse Explained」](https://gigazine.net/news/20160318-antibiotic-apocalypse-explained/)

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

#### [Nucleotide](http://www.ddbj.nig.ac.jp/sub/code-e.html#nucleotide)

![https://twitter.com/cosmos4u/status/1234503992501252096](https://pbs.twimg.com/media/ER3UpDPW4AIgzDX?format=png&name=small)

#### [Amino Acids](http://www.ddbj.nig.ac.jp/sub/code-e.html#amino)

<img src="https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41591-020-0820-9/MediaObjects/41591_2020_820_Fig1_HTML.png" alt="https://www.nature.com/articles/s41591-020-0820-9/figures/1" width=50%>

----------

### [R: The R Project for Statistical Computing](https://www.r-project.org/)
- 2017-05-12 [RStudioでRを直感的に使おう MacOS版 2017 統合TV(togotv)｜生命科学系DB・ツール使い倒し系チャンネル](https://doi.org/10.7875/togotv.2017.043)
- Jan 24, 2020 [R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners](https://www.youtube.com/watch?v=YBAWVNWiZlU)

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------

