SFC 2017年度 春学期 火曜日３時限 [λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)

# [生命動態のデータサイエンス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2017_41550&ks=44020)

- 科目概要：
生物のゲノム配列は進化によりダイナミックに変化している。この授業では、コンピュータ実習を通して、生命情報解析（バイオインフォマティクス）の手法を習得する。Mac OS Xを用いて、参考文献の例題を実行し、プロジェクトをすすめる。
- 成績評価：提出課題と最終発表とレポート
- 参考文献：
  - [Conrad Bessant; Darren Oakley; Ian Shadforth - Building Bioinformatics Solutions 2nd edition, Oxford University Press, 2014, 368p.](https://github.com/haruosuz/books/tree/master/bbs) 
  - [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://a-little-book-of-r-for-bioinformatics.readthedocs.org/en/latest/)

## 講義日程と資料
- 2017-04-11 第1回 [イントロダクション](#イントロダクション)
- 2017-04-18 第2回 生物学的データ [Biological data](https://github.com/haruosuz/books/tree/master/bbs#chapter-1-introduction)
- 2017-04-25 第3回 R言語入門 [Introduction to R](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#how-to-install-r-and-a-brief-introduction-to-r)
- 2017-05-02 第4回 DNA配列解析1 [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)
- 2017-05-09 第5回 DNA配列解析2 [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)
- 2017-05-13 (土) 3限(13:00～14:30) [補講](#補講)
- 2017-05-16 第6回 タンパク質配列解析 [Protein sequence analysis](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
- 2017-05-20 (土) 3限(13:00～14:30) [補講](#補講)
- 2017-05-23 第7回 [休講](http://ngs5.org/)
- 2017-05-30 第8回 [中間発表](#中間発表)
- 2017-06-06 第9回 ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-global-alignment-of-dna-sequences-using-the-needleman-wunsch-algorithm)
- 2017-06-13 第10回 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#multiple-alignment-and-phylogenetic-trees)
  - [R packages](#r-packages)
- 2017-06-20 第11回 ケーススタディ [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md)
- 2017-06-27 第12回 クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md)
- 2017-07-04 第13回 ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)
- 2017-07-11 第14回 [最終発表](#最終発表)
- 2017-07-18 [レポート](#レポート)提出期限
- ケーススタディ [Case Study](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md)
  - ゲノムDNA配列解析 [NCBI assembly summary](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#ncbi-assembly-summary)
  - タンパク質配列解析 [UniProtKB Swiss-Prot protein sequence database](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#uniprotkb-swiss-prot-protein-sequence-database)
    - アミノ酸組成 [Amino acid usage](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#amino-acid-usage)
    - ペアワイズ配列アラインメント [Pairwise Sequence Alignment](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#pairwise-sequence-alignment)

----------
## 補講
講師：[Dr. Hugues Richard](http://www.lcqb.upmc.fr/hrichard/index.html)
パリ第6大学 [Université Pierre et Marie CURIE (UPMC)](https://ja.wikipedia.org/wiki/パリ第6大学)
フランス国立科学研究センター [CNRS](https://ja.wikipedia.org/wiki/フランス国立科学研究センター)

- 2017年5月13日 (土) 3限(13:00～14:30)
[Annotation of promoter sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/hrichard/Annotation_of_promoter_sequences.pdf) | 
[プロモーター配列のアノテーション](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#annotation-of-promoter-sequences) 
- 2017年5月20日 (土) 3限(13:00～14:30)
[Annotation of Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/hrichard/Annotation_of_Coding_sequences.pdf) | 
[タンパク質コード配列のアノテーション](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#annotation-of-coding-sequences) 

----------
## 中間発表
日時：2017年5月30日(火) 3限(13:00～14:30)の希望時間  
場所：λ18  
発表時間：1人あたり最大5分（質疑応答を含む）  
スライド1枚でプロジェクトの計画（解析対象の生物や遺伝子）を紹介する。

----------
## 最終発表
日時：2017年7月11日(火) 3限(13:00～14:30)の希望時間  
場所：λ18  
発表時間：最大5分（質疑応答を含む）  

## レポート
提出期限：2017年7月18日(火)  
提出先：SFC-SFSの課題にレポートのファイルを登録する。  
書式：A4で5枚以内。本文以降に付録(appendix)を付けることができる。ファイル容量に注意する。

## 成績
最終発表＋レポート＋提出課題の総合点に基づく評価となります。

----------

## イントロダクション

### バイオインフォマティクスとは何か
[bioinformatics | バイオインフォマティクス | 生物情報科学](http://bi.biopapyrus.net)  

![http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about](http://blog.thegrandlocus.com/img/bioinformatic_word_cloud.png)

## バイオインフォマティシャン

![http://blog.fejes.ca/?p=2418](http://blog.fejes.ca/wp-content/uploads/2014/01/bioinformatics_chart1.png)

### バイオインフォマティクスの研究対象
[ゲノミクス](https://ja.wikipedia.org/wiki/ゲノミクス)、[トランスクリプトミクス](https://ja.wikipedia.org/wiki/トランスクリプトーム)、[プロテオミクス](https://ja.wikipedia.org/wiki/プロテオーム)、[メタボロミクス](https://ja.wikipedia.org/wiki/メタボロミクス)  

![http://www.metabolomics.bbsrc.ac.uk/background.htm](http://www.metabolomics.bbsrc.ac.uk/background_files/image038.gif)

#### TED Talks
- [ロブ・ナイト: 微生物がどのようにして私達を作っているのか](https://www.ted.com/talks/rob_knight_how_our_microbes_make_us_who_we_are?language=ja)
- [ジェシカ・グリーン: 私たちを取り巻く細菌と住環境のデザイン](http://www.ted.com/talks/jessica_green_good_germs_make_healthy_buildings?language=ja)
- [ジョナサン・アイゼン：微生物にこんにちは](https://www.ted.com/talks/jonathan_eisen_meet_your_microbes?language=ja)
- [リチャード・レズニック「ゲノム革命の時代へようこそ」](https://www.ted.com/talks/richard_resnick_welcome_to_the_genomic_revolution?language=ja)
- [ジェシカ・グリーン「微生物を正しく取り除くために」](http://www.ted.com/talks/jessica_green_are_we_filtering_the_wrong_microbes?language=ja)
- [クレイグ・ベンター：「人工生命」について発表する](https://www.ted.com/talks/craig_venter_unveils_synthetic_life?language=ja)
- [バリー・シュラー: ゲノム学基礎講座](https://www.ted.com/talks/barry_schuler_genomics_101?language=ja)
- [クレイグ・ベンター：目前に迫る合成生命の創造](https://www.ted.com/talks/craig_venter_is_on_the_verge_of_creating_synthetic_life?language=ja)
- [クレイグ・ヴェンター: DNAと海](https://www.ted.com/talks/craig_venter_on_dna_and_the_sea?language=ja)

### バイオインフォマティクスのリソース
[データベースとソフトウェア](https://ja.wikipedia.org/wiki/バイオインフォマティクス#.E3.83.87.E3.83.BC.E3.82.BF.E3.83.99.E3.83.BC.E3.82.B9)  

![http://www.quizbiology.com/2013/05/bioinformatics-mcq-quiz.html](http://lh5.ggpht.com/-RVDAcMLXpPQ/UaLVfpoguLI/AAAAAAAAGdw/n8DEk4aPAIg/Bioinformatics%252520Resources%25255B11%25255D.png)

#### [DNA塩基](http://www.ddbj.nig.ac.jp/sub/ref1-j.html)配列
[SILVA rRNA database](https://www.arb-silva.de)

![http://www.arb-silva.de/documentation/sina-tutorial/](http://www.arb-silva.de/fileadmin/graphics_general/main/tutorial_aligner/aligner_basic01.png)

#### タンパク質の[アミノ酸](http://www.ddbj.nig.ac.jp/sub/ref2-j.html)配列
[UniProt](https://ja.wikipedia.org/wiki/Swiss-Prot)

![http://www.uniprot.org/help/about](http://www.uniprot.org/images/overview.png)

----------

## 準備
[λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)のiMac Retina 5k 27inch

### Unix
![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

	bash

ターミナルで以下のコマンドを実行する:  

	ls
	pwd
	date
	touch test.txt

	blastp
	which blastp

レポートのサンプルを取得する:  

	wget https://github.com/haruosuz/DS4GD/raw/master/2017/examples_2016.tar.gz

### R
[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

Rコンソールで[graphicsのデモ](http://qiita.com/HirofumiYashima/items/d93e174d2de3d201c22a)を実行する:  

	demo(graphics)

パッケージを呼び出す:  

    library(seqinr)
    library(Biostrings)

Rを終了:  

	quit()

### R packages

[パッケージ | RのパッケージをCRANからインストールする方法と利用方法](http://stat.biopapyrus.net/r/package-function.html)

パッケージ [`seqinr`](https://cran.r-project.org/web/packages/seqinr/index.html), [`ape`](https://cran.r-project.org/web/packages/ape/index.html) のインストール:  

    install.packages("seqinr")
    install.packages("ape")

Bioconductor パッケージ [`Biostrings`](http://bioconductor.org/packages/release/bioc/html/Biostrings.html), [`msa`](https://bioconductor.org/packages/release/bioc/html/msa.html) のインストール:  

    source("https://bioconductor.org/biocLite.R")
    biocLite("Biostrings")
    biocLite("msa")

パッケージの呼び出し:  

    # Loading Packages
    library(seqinr)
    library(ape)
    library(Biostrings)
    library(msa)

バージョン情報の表示:  

    # Print version information
    > sessionInfo()

    R version 3.3.3 (2017-03-06)
    Platform: x86_64-apple-darwin13.4.0 (64-bit)
    Running under: OS X Mavericks 10.9.5

    other attached packages:
    msa_1.6.0
    Biostrings_2.42.1
    ape_4.1
    seqinr_3.3-6       

----------
