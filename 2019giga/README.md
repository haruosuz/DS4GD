Keio SFC 
2019 Fall Tuesday 2nd Period
2019年度 秋学期 火曜日２時限
教室 Classroom [λ21](http://classroom.sfc.keio.ac.jp/class/l-to/l-21.html)

# DS4GD
DATA SCIENCE FOR GENOME DYNAMICS (GIGA)
[Syllabus](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2019_25381&ks=B3206&key=c2db0cdbb741a9be92dffba95e846145&lang=en)  
生命動態のデータサイエンス (GIGA)
[シラバス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2019_25381&ks=B3206&key=c2db0cdbb741a9be92dffba95e846145&lang=ja)

## References
**参考文献**
- [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)

## Class Schedule & Materials
**講義日程と資料**

[Calendar for Fall Semester 2019](https://www.sfc.keio.ac.jp/doc/19f_calendar_e.pdf)
[2019年度 秋学期授業カレンダー](https://www.sfc.keio.ac.jp/doc/19f_calendar_j.pdf)

- 2019-09-24 No. 1 - イントロダクション [Introduction](#introduction)
  - 顧みられない熱帯病 [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)
- 2019-10-01 No. 2 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#how-to-install-r-and-a-brief-introduction-to-r)
- 2019-10-08 No. 3 - DNA配列解析(1) [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
  - Case Study [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2019giga/CaseStudy.md#ncbi-genome-list)
- 2019-10-15 No. 4 - DNA配列解析(2) [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-2)
- 2019-10-22 即位礼【国民の休日】*[National Holiday](https://www8.cao.go.jp/chosei/shukujitsu/gaiyou.html)*
- 2019-10-29 No. 5 - Case Study [NCBI GENOME_REPORTS](https://github.com/haruosuz/DS4GD/blob/master/2019giga/CaseStudy.md#ncbi-genome_reports)
- 2019-11-05 No. 6 - タンパク質コード配列 [Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#coding-sequences)
- 2019-11-12 No. 7 - 中間発表 [interim report](#interim-report)
- 2018-11-19 午前：前半科目追試 | 午後：三田祭準備 *[Preparation for Mita Festival](http://www.gakuji.keio.ac.jp/en/calendar.html)*
- 2019-11-26 No. 8 - [Guest Speaker](#guest-speaker)
- 2019-12-03 No. 9 - [Guest Speaker](#guest-speaker)
- 2019-12-10 No. 10 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
  - ドットプロット [dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)
- 2019-12-17 No. 11 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
  - 2つのDNA配列間のグローバル・アライメント [Pairwise global alignment of DNA sequences](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
- 2019-12-24 No. 12 - 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
- 2020-01-07 No. 13 - Case Study [NCBI ASSEMBLY_REPORTS](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#ncbi-assembly_reports)
- 2020-01-14 No. 14 - 最終発表 [final presentation](#final-presentation)
- 2020-01-21 レポート提出期限 Deadline for [final report](#final-report)

----------
## interim report
**中間発表**

5 minutes will be allocated for each presentation, including presentation and discussion.

----------
## final presentation
**最終発表**

Five minutes will be allocated for each presentation.

----------
## final report
**レポート**

Submit your final report in PDF format.

----------

## Introduction
### [Bioinformatics](http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about)
### [Bioinformatician](http://blog.fejes.ca/?p=2418)
### [Bioinformatics Research](https://github.com/haruosuz/books/tree/master/bbs#13-principal-applications-of-bioinformatics)
#### [Human microbiome](https://en.wikipedia.org/wiki/Human_microbiome)
**[ヒト微生物群集](https://ja.wikipedia.org/wiki/ヒトマイクロバイオーム)**

- [You are your microbes - Jessica Green and Karen Guillemin | TED-Ed](https://ed.ted.com/lessons/you-are-your-microbes-jessica-green-and-karen-guillemin)

![http://kaihooo.com/microbea/](http://kaihooo.com/wp-content/uploads/microbea.png)

#### antibiotic resistance
**[抗生物質耐性](https://ja.wikipedia.org/wiki/抗微生物薬耐性)**

- [What causes antibiotic resistance? - Kevin Wu | TED-Ed](https://ed.ted.com/lessons/how-antibiotics-become-resistant-over-time-kevin-wu)

- [The evolution of antibiotic resistance | Science](https://science.sciencemag.org/content/365/6458/1082)

#### [Plasmid](https://en.wikipedia.org/wiki/Plasmid)
**[プラスミド](https://ja.wikipedia.org/wiki/プラスミド)**

![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Plasmid_%28english%29.svg/200px-Plasmid_%28english%29.svg.png)

- [抗生物質が効かない悪魔のスーパーバグがどれくらい怖い存在なのか理解できるムービー「The Antibiotic Apocalypse Explained」](https://gigazine.net/news/20160318-antibiotic-apocalypse-explained/)

#### [Microbiomes of the built environment](https://en.wikipedia.org/wiki/Microbiomes_of_the_built_environment)
**人工環境の微生物群集**

- TED Talk [Jessica Green: Are we filtering the wrong microbes?](https://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes) | [ジェシカ・グリーン「微生物を正しく取り除くために」](http://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes?language=ja)
  - [Kembel et al. (2012) "Architectural design influences the diversity and structure of the built environment microbiome."](https://www.ncbi.nlm.nih.gov/pubmed/22278670)

#### [MetaSUB](http://metasub.org/media-2/)
**[MetaSUB: Metagenomics & Metadesign of Subways & Urban Biomes](https://github.com/haruosuz/metasub/blob/master/README.md)**

![https://twitter.com/Daniela_Bezdan/status/1009876180684754944](https://pbs.twimg.com/media/DgPMfQ9X0AMEi1l?format=jpg&name=small)

#### Epidemiology
**[疫学](https://ja.wikipedia.org/wiki/疫学)**

- TED Talk [Steven Johnson: How the "ghost map" helped end a killer disease](https://www.ted.com/talks/steven_johnson_tours_the_ghost_map) | [スティーブ・ジョンソンの感染地図](https://www.ted.com/talks/steven_johnson_tours_the_ghost_map?embed=true&language=ja)
- [Nathan Grubaugh on Twitter](https://twitter.com/NathanGrubaugh/status/1164553815376441350)
  - [Travel Surveillance and Genomics Uncover a Hidden Zika Outbreak during the Waning Epidemic: Cell](https://www.cell.com/cell/fulltext/S0092-8674(19)30783-4)

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

#### [Nucleotide](http://www.ddbj.nig.ac.jp/sub/code-e.html#nucleotide)

![http://www.arb-silva.de/documentation/sina-tutorial/](https://www.arb-silva.de/fileadmin/graphics_general/main/tutorial_aligner/01_input_dataset.png)

#### [Amino Acids](http://www.ddbj.nig.ac.jp/sub/code-e.html#amino)

- [trfA - Plasmid replication initiator protein TrfA - Escherichia coli - trfA gene & protein](https://www.uniprot.org/uniprot/P07676)

----------

### [R: The R Project for Statistical Computing](https://www.r-project.org/)
[RStudioでRを直感的に使おう MacOS版 2017](https://doi.org/10.7875/togotv.2017.043)

![http://www.sthda.com/english/wiki/running-rstudio-and-setting-up-your-working-directory-easy-r-programming](http://www.sthda.com/sthda/RDoc/images/rstudio.png)

----------





