Keio SFC 2019 Spring Tuesday 3rd Period  
SFC 2019年度 春学期 火曜日3時限 
教室 Classroom [λ21](http://classroom.sfc.keio.ac.jp/class/l-to/l-21.html)

# DS4GD
DATA SCIENCE FOR GENOME DYNAMICS / GENOME INFORMATICS
[Syllabus](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2019_41550&ks=B3206&key=bcef5cf1aa68da4bc44794e7cde04480&lang=en)  
生命動態のデータサイエンス/生命情報解析
[シラバス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2019_41550&ks=B3206)  

## References
**参考文献**
- [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- [坊農秀雅, 小野浩雅 (監修). 生命科学データベース・ウェブツール, メディカルサイエンスインターナショナル, 2019, 168p.](https://www.medsi.co.jp/books/products/detail.php?product_id=3665)
- [藤博幸 (編). よくわかるバイオインフォマティクス入門, 講談社, 2019, 205p.](https://www.kspub.co.jp/book/detail/5138212.html)

## Class Schedule & Materials
**講義日程と資料**

[2019年度 春学期授業カレンダー](https://www.sfc.keio.ac.jp/doc/19s_calendar_j.pdf)

- [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md)
- 2019-04-09 No. 1 - イントロダクション [Introduction](#introduction)
  - 顧みられない熱帯病 [Neglected Tropical diseases](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#neglected-tropical-diseases)
- 2019-04-16 No. 2 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#how-to-install-r-and-a-brief-introduction-to-r)
- 2019-04-23 No. 3 - DNA配列解析(1) [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
  - ゲノムの特徴 [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
  - Case Study [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#ncbi-genome-list)
- 2019-04-30 *【国民の休日】National Holiday*
- 2019-05-07 No. 4 - DNA配列解析(2) [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-2)
- 2019-05-14 No. 5 - Case Study [NCBI GENOME_REPORTS](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#ncbi-genome_reports)
- 2019-05-21 No. 6 - タンパク質コード配列 [Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#coding-sequences)
- 2019-05-28 No. 7 - 中間発表 [interim report](#interim-report)
  - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
    - ドットプロット [dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)
- 2019-06-04 No. 8 - [Guest Speaker](#guest-speaker)
- 2019-06-11 No. 9 - [Guest Speaker](#guest-speaker)
- 2019-06-18 No. 10 - [Guest Speaker](#guest-speaker)
- 2019-06-25 No. 11 - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
  - 2つのDNA配列間のグローバル・アライメント [Pairwise global alignment of DNA sequences](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
- 2019-07-02 No. 12 - Case Study [NCBI GENOME_REPORTS](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#ncbi-genome_reports)
  - *k*-mer 連続塩基組成 [Over-represented and under-represented DNA words](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#over-represented-and-under-represented-dna-words)
- 2019-07-09 No. 13 - Case Study [2019-07-09](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#2019-07-09)
  - Case Study [NCBI ASSEMBLY_REPORTS](https://github.com/haruosuz/DS4GD/blob/master/2019/CaseStudy.md#ncbi-assembly_reports)
  - 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
- 2019-07-16 No. 14 - 最終回
  - 最終発表 [final presentation](#final-presentation)
  - 春学期の授業について「学期終わりの全体調査」の学生作業期間 7月9日（火）10時～7月26日（金）23時
- 2019-07-23 レポート提出期限 Deadline for [final report](#final-report)

----------
## Guest speaker
**特別講演**

- 講師: 森秀人 氏
- [講義資料](https://github.com/ponnhide/DS4GD_HM)
  - 2019-06-04 No. 8 [Python入門](https://github.com/ponnhide/DS4GD_HM/blob/master/DS4GD_HM1.md#python入門)
  - 2019-06-11 No. 9 https://github.com/ponnhide/DS4GD_HM/blob/master/DS4GD_HM2.md
    - [sequence analysis with Python](https://github.com/ponnhide/DS4GD_HM/blob/master/DS4GD_HM2.md#dnaprotein-sequence-analysis-wiith-python)
  - 2019-06-18 No. 10 https://github.com/ponnhide/DS4GD_HM/blob/master/DS4GD_HM3.md
```
git clone https://github.com/ponnhide/DS4GD_HM
cd DS4GD_HM/
cd sample_program/

python GCskew_slide.py
python plot2.py sample2_GCskew.txt

python get_CDS.py 
ls -ltr
```

----------
## interim report
**中間発表**

スライド1枚以上を用いてプロジェクト（解析対象の生物や遺伝子）について説明する。
発表時間：1人あたり最大5分（質疑応答を含む）

5 minutes will be allocated for each presentation, including presentation and discussion.

----------
## final presentation
**最終発表**

Five minutes will be allocated for each presentation.

発表時間：1人あたり最大5分

----------
## final report
**レポート**

Submit your final report in PDF format.

- 提出期限：2019年7月23日(火)  
- 提出先：SFC-SFSの課題にレポートのファイルを登録する。  
- 書式：A4で5枚以内。本文以降に付録(appendix)を付けることができる。ファイル容量に注意する。
- 文章構成：[IMRAD](https://ja.wikipedia.org/wiki/IMRAD)形式。序論、方法、結果と考察、参考文献を含める。

----------

## Introduction
### [Bioinformatics](http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about)
### [Bioinformatician](http://blog.fejes.ca/?p=2418)
### [Bioinformatics Research](https://github.com/haruosuz/books/tree/master/bbs#13-principal-applications-of-bioinformatics)
#### [Microbiomes of the built environment](https://en.wikipedia.org/wiki/Microbiomes_of_the_built_environment)
**人工環境の微生物群集**

![https://www.biomedcentral.com/collections/builtenvironment](https://resource-cms.springernature.com/springer-cms/rest/v1/content/6629006/data/v1)

- [ジェシカ・グリーン「微生物を正しく取り除くために」](http://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes?language=ja) | [Jessica Green: Are we filtering the wrong microbes? | TED Talk](https://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes)
  - [Kembel et al. (2012) "Architectural design influences the diversity and structure of the built environment microbiome."](https://www.ncbi.nlm.nih.gov/pubmed/22278670)

![](https://media.nature.com/m685/nature-assets/ismej/journal/v6/n8/images/ismej2011211f2.jpg)

**[MetaSUB: Metagenomics & Metadesign of Subways & Urban Biomes](https://github.com/haruosuz/metasub/blob/master/README.md)**
都市のメタゲノム

#### [Plasmid](https://en.wikipedia.org/wiki/Plasmid)
**[プラスミド](https://ja.wikipedia.org/wiki/プラスミド)**

- [抗生物質が効かない悪魔のスーパーバグがどれくらい怖い存在なのか理解できるムービー「The Antibiotic Apocalypse Explained」](https://gigazine.net/news/20160318-antibiotic-apocalypse-explained/)
細菌は染色体とプラスミドという2種類のDNAを持っています。
細菌同士は接触するとプラスミドを交換。
プラスミドを交換することで細菌の能力を強化。
- [Yano et al. (2018) "Reconsidering plasmid maintenance factors for computational plasmid design."](https://www.ncbi.nlm.nih.gov/pubmed/30619542)
  - [Table 1 Lists of plasmids in different incompatibility groups.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6312765/table/t0005/?report=objectonly)
- ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/plasmids.txt

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

#### [Nucleotide](http://www.ddbj.nig.ac.jp/sub/code-e.html#nucleotide)

![http://www.arb-silva.de/documentation/sina-tutorial/](https://www.arb-silva.de/fileadmin/graphics_general/main/tutorial_aligner/01_input_dataset.png)

#### [Amino Acids](http://www.ddbj.nig.ac.jp/sub/code-e.html#amino)

![http://abacus.bates.edu/bioinformatics1/sequencesearch3.html](http://abacus.bates.edu/bioinformatics1/screenshots/NCBI-5-FASTA.jpg)

----------

### [R: The R Project for Statistical Computing](https://www.r-project.org/)
[RStudioでRを直感的に使おう MacOS版 2017](https://doi.org/10.7875/togotv.2017.043)

![http://www.sthda.com/english/wiki/running-rstudio-and-setting-up-your-working-directory-easy-r-programming](http://www.sthda.com/sthda/RDoc/images/rstudio.png)

----------

