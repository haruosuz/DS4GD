[Keio University Shonan Fujisawa Campus](https://www.sfc.keio.ac.jp/en/) (SFC)  
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
  - [scripts.zip](https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip)

## Class Schedule & Materials
**講義日程と資料**

[[UPDATED] Calendar for Spring Semester 2020](https://www.sfc.keio.ac.jp/en/docs/681a9a34e5cb149a55e3780977a9b59f366781ec.pdf) |
[【変更後】 2020年度 春学期授業カレンダー](https://www.sfc.keio.ac.jp/doc/82bacea42ef958c454eb0044be552fc00dbb7952.pdf)

- 2020-05-05 No. 1 - イントロダクション [Introduction](#introduction)
  - [RとRStudio](#r-rstudio)
- 2020-05-12 No. 2 - R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#how-to-install-r-and-a-brief-introduction-to-r)
- 2020-05-19 No. 3 - DNA配列解析(1) [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-1)
  - [Genome signature](https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#genome-signature)
  - [NCBI Genome List](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#ncbi-genome-list)
- 2020-05-26 No. 4 - DNA配列解析(2) [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#dna-sequence-statistics-2)
- 2020-06-02 No. 5 - [Guest Speaker](#guest-speaker)
- 2020-06-09 No. 6 - [Guest Speaker](#guest-speaker)
- 2020-06-16 No. 7 - [Guest Speaker](#guest-speaker)
- 2020-06-23 No. 8 - 中間発表 [interim report](#interim-report)
  - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
    - タンパク質データベース Protein sequence database [UniProt](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#uniprot)
    - ドットプロット [dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)
  - [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast)
- 2020-06-30 No. 9
  - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-sequence-alignment)
    - グローバル・アライメント [Pairwise global alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
    - ローカル・アラインメント [Pairwise local alignment](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#pairwise-local-alignment-of-protein-sequences-using-the-smith-waterman-algorithm)
- 2020-07-07 No. 10 - 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
- 2020-07-14 No. 11 - [scripts.zip](https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip)
scripts/my_script2report.R
  - [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md)
    - [NCBI BLAST](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#ncbi-blast)
    - [Chunk options](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#chunk-options)
- 2020-07-21 No. 12 - 最終回
  - 最終発表 [final presentation](#final-presentation)
- 2020-07-28 レポート提出期限 Deadline for [final report](#final-report)

----------
## Guest speaker
**[特別講演](https://www.sfc.keio.ac.jp/faculty/class/special_lecture.html)**

- 講師: 山本 楠 氏 Daniel Evans-Yamamoto
- 講義資料 https://danyamamotoevans.github.io/blog/code/ds4gd

----------
## interim report
**中間発表**

Presentation time: 5 minutes will be allocated for each presentation (including Q&A).
Briefly describe objects (DNA, protein, and other textual sequences, etc.) you will analyze in your project, using your presentation slides (PowerPoint/Keynote/PDF/HTML document).

発表時間：1人あたり最大5分（質疑応答を含む）。
プレゼンテーションのスライド（PowerPoint/Keynote/PDF/HTML形式ファイル）を用いて、プロジェクトで解析するオブジェクト（DNA、タンパク質、その他のテキスト配列など）について説明する。

----------
## final presentation
**最終発表**

Presentation time: 5 minutes will be allocated for each presentation (including Q&A).
Report your main findings on analyses of objects (DNA, protein, and other textual sequences, etc.) you're interested in. The analyses can include DNA sequence statistics (length, GC content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global sequence alignment, and local sequence alignment), multiple sequence alignment, and phylogenetic trees, etc.

発表時間：1人あたり最大5分（質疑応答を含む）。
興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）の解析結果を報告する。解析の例として、配列の統計（長さ、GC含量、塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル配列アライメント、ローカル配列アライメント）、多重配列アライメント、系統樹などが含まれる。

----------
## final report
**レポート**

Submit your final report as a PDF/HTML document.

- https://en.wikipedia.org/wiki/IMRAD
(Introduction, Methods, Results, and Discussion) is a common organizational structure (a document format).
- https://ja.wikipedia.org/wiki/IMRAD
は、文章構成の型式の名称の1つである。
  - Title（タイトル; T）
  - Introduction（導入; I） :What are you studying and why?(何を研究したのか？、何故それを研究したのか)
  - Methods（研究方法; M） :What did you do?（具体的には何をしたのか？）
  - Results（実験結果; R） :What did you find?（何がわかったのか?）
  - Discussion（考察; D） :What do your findings mean?(あなたが見つけたことは何を意味するのか？）
  - References（参考文献一覧）

----------

## Introduction
### [Bioinformatics](http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about)

### [Bioinformatician](https://www.biostars.org/p/223069/)

### [Bioinformatics Research](https://github.com/haruosuz/books/blob/master/bbs/README.md#13-principal-applications-of-bioinformatics)

#### [Microbiomes of the built environment](https://en.wikipedia.org/wiki/Microbiomes_of_the_built_environment)
**人工環境の微生物群集**

- July 2011 TED Talk 5:18 [Jessica Green: Are we filtering the wrong microbes?](https://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes) | [ジェシカ・グリーン「微生物を正しく取り除くために」](http://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes?language=ja)
  - [Kembel et al. (2012) "Architectural design influences the diversity and structure of the built environment microbiome."](https://www.ncbi.nlm.nih.gov/pubmed/22278670)
- 新型コロナウイルス感染症：人工環境で感染を減らすには [Dietz et al. (2020) "2019 Novel Coronavirus (COVID-19) Pandemic: Built Environment Considerations To Reduce Transmission."](https://msystems.asm.org/content/5/2/e00245-20)
Conceptualization of SARS-CoV-2 deposition.  
![https://msystems.asm.org/content/5/2/e00245-20](https://msystems.asm.org/content/msys/5/2/e00245-20/F2.small.gif)

#### [MetaSUB: Metagenomics & Metadesign of Subways & Urban Biomes](https://github.com/haruosuz/metasub/blob/master/README.md)

- 紹介ビデオ [MetaSUB Introductory Video](https://vimeo.com/171773795)
- ニューヨークの地下鉄で新型コロナウイルスは今のところ見つかっていない。
["NYC Scientists Swab the Subway in Search of SARS-CoV-2." Is it there? So far, nope! Environmental and ongoing clinical #COVID19 efforts discussed here:](https://twitter.com/mason_lab/status/1245394591819477003)

<img src="https://media.wired.com/photos/5ea73fc731d06e000847a5ec/master/w_2560%2Cc_limit/Science_microbiome_covid19-1204320628.jpg" alt="https://www.wired.com/story/microbe-mappers-are-tracking-covid-19s-invisible-traces/" width=25%>

#### Antibiotic resistance
**[抗生物質耐性](https://ja.wikipedia.org/wiki/抗微生物薬耐性)**

- TED-Ed [What causes antibiotic resistance? - Kevin Wu](https://ed.ted.com/lessons/how-antibiotics-become-resistant-over-time-kevin-wu) | [抗生物質に対する耐性が生まれるのはなぜか？ - ケビン・ウー](https://amara.org/en/videos/VllmqrFumzGt/ja/812239/)

#### [Plasmid](https://en.wikipedia.org/wiki/Plasmid)
**[プラスミド](https://ja.wikipedia.org/wiki/プラスミド)**

![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Plasmid_%28english%29.svg/200px-Plasmid_%28english%29.svg.png)

- [抗生物質が効かない悪魔のスーパーバグがどれくらい怖い存在なのか理解できるムービー「The Antibiotic Apocalypse Explained」](https://gigazine.net/news/20160318-antibiotic-apocalypse-explained/)
細菌は染色体とプラスミドという2種類のDNAを持っています。
細菌同士は接触するとプラスミドを交換。
プラスミドを交換することで細菌の能力を強化。
- [Yano et al. (2018) "Reconsidering plasmid maintenance factors for computational plasmid design."](https://www.ncbi.nlm.nih.gov/pubmed/30619542)

### [Bioinformatics resources](https://github.com/haruosuz/books/tree/master/bbs#15-publicly-available-bioinformatics-resources)

----------

### R RStudio
- Jan 24, 2020 [R - Install R and R Studio on Windows, Mac, Linux (2020) - R Programming Tutorial for Beginners](https://www.youtube.com/watch?v=YBAWVNWiZlU)
- 2017-05-12 [RStudioでRを直感的に使おう MacOS版 2017 統合TV(togotv)｜生命科学系DB・ツール使い倒し系チャンネル](https://doi.org/10.7875/togotv.2017.043)
- (Rで)塩基配列解析 http://www.iu.a.u-tokyo.ac.jp/~kadota/r_seq.html
- [RとRStudioのインストール方法の解説](http://yukiyanai.github.io/jp/resources/)
  - [Linux (Ubuntu) 編 (PDF, 4.6MB)](http://yukiyanai.github.io/jp/resources/docs/install-R_ubuntu.pdf)
  - [macOS 編 (PDF, 4.9MB)](http://yukiyanai.github.io/jp/resources/docs/install-R_macOS.pdf)
  - [Windows 編 （PDF, 5.8MB）](http://yukiyanai.github.io/jp/resources/docs/install-R_windows.pdf)

<img src="https://d33wubrfki0l68.cloudfront.net/8a64bb047429d7ae0e2acae35c40e421e6439bf6/80e5d/diagrams/rstudio-editor.png" alt="https://r4ds.had.co.nz/workflow-scripts.html" width=50%>

----------
