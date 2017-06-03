SFC 2016年度 春学期 水曜日３時限 [λ18](http://classroom.sfc.keio.ac.jp/class/l-to/l-18.html)

# [生命動態のデータサイエンス](https://vu.sfc.keio.ac.jp/course2014/summary/syll_view_c.cgi?yc=2016_41550&ks=B3206)
DATA SCIENCE FOR GENOME DYNAMICS [DS2]  

- 科目概要：この授業では、コンピュータ実習を通して、生命情報解析（バイオインフォマティクス）の手法を習得する。Mac OS Xを用いて、参考文献の例題を実行し、プロジェクトをすすめる。
- 成績評価：提出課題と最終発表とレポート
- 参考文献：
  - [Conrad Bessant; Darren Oakley; Ian Shadforth - Building Bioinformatics Solutions 2nd edition, Oxford University Press, 2014, 368p.](https://github.com/haruosuz/books/tree/master/bbs) 
  - [Avril Coghlan - A Little Book of R For Bioinformatics, 2011, 73p.](https://a-little-book-of-r-for-bioinformatics.readthedocs.org/en/latest/)

## 講義日程と資料
- 2016-04-13 第1回 [イントロダクション](https://github.com/haruosuz/DS4GD/blob/master/README.md)
- 2016-04-20 第2回 [生物学的データ Biological data](https://github.com/haruosuz/books/tree/master/bbs#chapter-1-introduction)
- 2016-04-27 第3回 [R入門](https://dl.dropboxusercontent.com/s/upqb2nzzb2j867f/BBS.md.html) 4.1.3 ベクトルとデータフレーム
- 2016-05-11 第4回 [R入門](https://dl.dropboxusercontent.com/s/upqb2nzzb2j867f/BBS.md.html) 4.1.4 実験データ
- 2016-05-18 第5回 [R入門](https://dl.dropboxusercontent.com/s/upqb2nzzb2j867f/BBS.md.html) 4.1.5 データ型; 4.1.6 データのインポート
- 2016-05-25 第6回 [R入門](https://dl.dropboxusercontent.com/s/upqb2nzzb2j867f/BBS.md.html) 4.1.7 データの視覚化
- 2016-06-01 第7回 [R入門](https://dl.dropboxusercontent.com/s/upqb2nzzb2j867f/BBS.md.html) 4.1.8 Rプログラム; 4.1.9 関数; 4.2 多変量解析; 4.3 Rパッケージ
- 2016-06-08 第8回 [配列解析 DNA Sequence Statistics](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan)
- 2016-06-15 第9回 休講
- 2016-06-22 第10回 [ペアワイズ配列アラインメント Pairwise Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#pairwise-sequence-alignment)
- 2016-06-29 第11回 多重配列アライメント、系統解析、配列解析
 - [多重配列アライメント Multiple Sequence Alignment](https://github.com/haruosuz/r4bioinfo/tree/master/R_msa#multiple-sequence-alignment)
 - [系統解析 Phylogenetic Analysis](https://github.com/haruosuz/r4bioinfo/tree/master/R_msa#phylogenetics)
 - [配列解析 SeqinR](https://github.com/haruosuz/r4bioinfo/tree/master/R_msa#seqinr)
- 2016-07-06 第12回 [クラスター分析 Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2016/hclust.md)
- 2016-07-13 第13回 [ヒートマップ Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2016/hclust.md#heat-map)
- 2016-07-20 第14回 [最終発表](#最終発表)
- [ケーススタディ Case Study](https://github.com/haruosuz/DS4GD/blob/master/2016/CaseStudy.md)

----------

## 補講日程と資料
- 2016-06-08
 - 4時限 (14:45～16:15) ε11 [「統計で嘘をつく方法」小寺 正明 氏（東京工業大学）](https://dl.dropboxusercontent.com/u/33495171/DS4GD/KeioStatistics2_rm2.pptx)
 - 5時限 (16:30～18:00) ε11 [「ネットワーク分析入門」山中 遼太 氏（日本オラクル）](https://www.dropbox.com/s/b6zgoki5vfobofy/Yamanaka_20160608.pptx?dl=0)

[hero-network.csv](https://www.dropbox.com/s/q1yst95hpethah7/hero-network.csv?dl=0)をRに読み込むコマンド:

	a <- as.matrix(read.csv("https://dl.dropboxusercontent.com/u/33495171/hero-network.csv", h=FALSE))

----------

## 最終発表
日時：2016年7月20日(水) 2限,3限(11:10～12:40,13:00～14:30)の希望時間  
場所：λ18  
発表時間：最大5分（質疑応答を含む）  

## レポート
提出期限：2016年7月27日(水)  
提出先：SFC-SFSの課題にレポートのファイルを登録する。  
書式：A4で5枚以内。本文以降に付録(appendix)を付けることができる。ファイル容量に注意する。

----------

## 関連授業
- [SFC2015年度秋学期 基礎バイオインフォマティクス](https://github.com/haruosuz/introBI)
 - [スライドのサンプル](https://dl.dropboxusercontent.com/u/33495171/introBI/slides.pdf)  
- [SFC2010年度春学期 ゲノム解析プログラミング](http://www.bioinfo.sfc.keio.ac.jp/class/genpro/)
 - [レポートのサンプル](http://www.bioinfo.sfc.keio.ac.jp/class/genpro/Report/genpro08s_repsamp1.pdf)  

----------

## バイオインフォマティクスとは何か
[bioinformatics | バイオインフォマティクス | 生物情報科学](http://bi.biopapyrus.net)  

![http://blog.thegrandlocus.com/2015/06/what-is-bioinformatics-about](http://blog.thegrandlocus.com/img/bioinformatic_word_cloud.png)

## バイオインフォマティクスの研究対象
[ゲノミクス](https://ja.wikipedia.org/wiki/ゲノミクス)、[トランスクリプトミクス](https://ja.wikipedia.org/wiki/トランスクリプトーム)、[プロテオミクス](https://ja.wikipedia.org/wiki/プロテオーム)、[メタボロミクス](https://ja.wikipedia.org/wiki/メタボロミクス)  

![http://www.metabolomics.bbsrc.ac.uk/background.htm](http://www.metabolomics.bbsrc.ac.uk/background_files/image038.gif)

## バイオインフォマティクスのリソース
[データベースとソフトウェア](https://ja.wikipedia.org/wiki/バイオインフォマティクス#.E3.83.87.E3.83.BC.E3.82.BF.E3.83.99.E3.83.BC.E3.82.B9)  

![http://www.quizbiology.com/2013/05/bioinformatics-mcq-quiz.html](http://lh5.ggpht.com/-RVDAcMLXpPQ/UaLVfpoguLI/AAAAAAAAGdw/n8DEk4aPAIg/Bioinformatics%252520Resources%25255B11%25255D.png)

## バイオインフォマティシャン

![http://blog.fejes.ca/?p=2418](http://blog.fejes.ca/wp-content/uploads/2014/01/bioinformatics_chart1.png)

- [The five habits of bad bioinformaticians](http://www.opiniomics.org/the-five-habits-of-bad-bioinformaticians/) 悪いバイオインフォマティシャンの習慣：不適切なソフトウェアを使用する。文献で最新の情報を得ない。酷いドキュメントを書く、または全く書かない。テストを実施しない。既に存在しているものをまた作る（車輪の再発明）。

----------

## 準備

[ここをクリック](https://github.com/dazoakley/bbs-v2/archive/master.zip)して、[Building Bioinformatics Solutions](https://github.com/haruosuz/books/tree/master/bbs)の補足資料`bbs-v2-master`をダウンロードする。

### Unixコマンド

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、以下のコマンドを実行する:  

	cd
	pwd
	ls

### R言語

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

Rコンソールで、以下のコマンドを実行する:  

	demo()
	demo(graphics)

### 学習サイト
- ドットインストール - 3分動画でマスターする初心者向けプログラミング学習サイト
 - [UNIXコマンド入門 (一般ユーザー編) (全16回)](http://dotinstall.com/lessons/basic_unix)
 - [R言語入門 (全13回)](http://dotinstall.com/lessons/basic_r)

----------
