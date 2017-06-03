[生命動態のデータサイエンス](https://github.com/haruosuz/DS4GD)

----------

# [Clustering](https://en.wikipedia.org/wiki/Clustering)

- [Cluster Analysis](#cluster-analysis)
- [Heat Map](#heat-map)

----------

# [Cluster Analysis](https://en.wikipedia.org/wiki/Cluster_analysis)
クラスター分析

[データ・クラスタリング](https://ja.wikipedia.org/wiki/データ・クラスタリング)は、データ解析手法（特に多変量解析手法）の一種。教師なしデータ分類手法、つまり与えられたデータを外的基準なしに自動的に分類する手法。

![http://www.albert2005.co.jp/technology/mining/method3_2.html](http://www.albert2005.co.jp/technology/images/tech_mining_img77.jpg)  

### 細菌の増殖

![http://kusuri-jouhou.com/microbe/mic.html](http://kusuri-jouhou.com/img/kyoyzai-ddd8.jpg)

[細菌の増殖と遺伝子の発現量の経時変化](http://www.spring8.or.jp/ja/news_publications/press_release/2008/080828/)

![](http://www.spring8.or.jp/ja/news_publications/press_release/2008/080828_fig/fig1.png)

細菌は、与えられた環境で生存できる上限の個体数に到達すると、定常期とよばれる増殖数と死滅数が釣り合った状態に移行します。

### 変数が2個の場合のクラスター分析
簡単な例として、5個の個体について2個􏰁の変数（増殖期と定常期􏰁の遺伝子発現量）の値が観測されている場合を例にとり、 クラスター分析􏰁を行なう。

	# 5個体について2変数(x1,x2)の値が格納された行列データを作成
	x1 <- c(5,4,1,5,5)
	x2 <- c(1,2,5,4,5)
	x <- cbind(x1,x2)
	rownames(x) <- 1:5

	# データを散布図にプロット
	plot(x)

	plot(x, type="n")
	text(x, labels=rownames(x))

	# クラスターの結合方法
	# dist()関数で個体間の非類似度（距離）測定 method = "euclidean", "manhattan", "binary", ...
	dist(x)
	d <- dist(x, method="manhattan") # マンハッタン距離（2点間の差の絶対値の総和）

	# hclust()関数で階層的クラスター分析 method = "single", "complete", "average" (UPGMA), ...
	hclust(d)
	hc <- hclust(d, method="single") # 最短距離法

	# グループの形成方法
	plot(hc) # 樹形図（Cluster Dendrogram）
	abline(h = 3.5)
	abline(h = 2.5)

	# 階層的クラスターの周りに四角形を描画
	plot(hc, hang = -1)
	# 切断する距離を指定
	rect.hclust(hc, h = 3.5)
	# グループの数を指定
	rect.hclust(hc, k = 3)

	# 樹形図を切断してグループを形成
	# 切断する距離を指定
	cutree(hc, h = 3.5)
	# グループの数を指定
	cutree(hc, k = 3)

	# 行列データとクラスタリング結果を結合し、ファイル出力
	g23 <- cutree(hc, k = c(2,3))
	write.csv(cbind(x,g23), file="~/table.csv")

	# 多次元尺度構成法
	d <- dist(x) # ユークリッド距離（2点間の差の2乗和の平方根）
	loc <- cmdscale(d)
	plot(loc[, 1], loc[, 2], type="n")
	text(loc[, 1], loc[, 2], labels=rownames(x))

### 細菌の炭素源利用能
[95種類の炭素源が充填されているマイクロプレートにコロニー懸濁液を接種し発色パターンを読み取る。](http://www.cscjp.co.jp/foodsafety_d/biolog.html)

![](http://www.cscjp.co.jp/item/img/img133e01418_1.jpg)

### 変数がp個の場合のクラスター分析
細菌5菌株について10種類􏰁の炭素源利用􏰁の有無を1と0の2値データで示した。マンハッタン距離を用いた最短距離法でクラスター分析を行う。

	# 5個体について10変数の値が格納された行列データを作成
	x <- cbind(
	 c(1,1,1,1,1),
	 c(1,1,0,1,1),
	 c(1,1,0,1,1),
	 c(1,1,0,1,1),
	 c(1,0,0,1,1),
	 c(1,1,1,1,1),
	 c(0,1,1,1,1),
	 c(0,0,1,1,1),
	 c(0,0,1,1,1),
	 c(0,0,1,0,1))

	# dist()関数で個体間の距離を計算する
	d <- dist(x, method="manhattan")

	# hclust()関数で階層的クラスター分析
	hc <- hclust(d, method="single")
	plot(hc)

### [SeqinR](https://cran.r-project.org/web/packages/seqinr/index.html)
配列解析

	# Loading seqinr package
	library(seqinr)

	# A toy example of amino-acid counts in three proteins
	data(toyaa)

	# t()関数で行列を転置
	X <- t(toyaa)

	# タンパク質のアミノ酸使用パターンを比較
	# matplot()関数でプロットする
	matplot(X, type="l", col=1:ncol(X), lty=1:ncol(X))
	legend("topleft", legend=colnames(X), col=1:ncol(X), lty=1:ncol(X))

	# 階層的クラスター分析
	plot(hclust(dist(t(X))))

### 参考文献
  - [分類学と系統学：ある蜜月の終焉](http://www.e-jsps.com/2007hp/topic/Datesoudo84/mitsu.html)
  - [クラスター分析の光と闇](http://cse.naro.affrc.go.jp/minaka/R/R-cluster.html) | [pdf](http://cse.naro.affrc.go.jp/minaka/R/clustering-04.pdf)
  - [Rとクラスター分析(1)](https://www1.doshisha.ac.jp/~mjin/R/28/28.html)
  - [Rとクラスター分析(2)](https://www1.doshisha.ac.jp/~mjin/R/29/29.html)
  - [Rによる階層的クラスタリング](http://bio-info.biz/tips/r_hclust.html)

----------

# Multidimensional Scaling
[多次元尺度構成法](https://ja.wikipedia.org/wiki/多次元尺度構成法)

	# 5個体について2変数(x1,x2)の値が格納された行列データを作成
	x1 <- c(5,4,1,5,5)
	x2 <- c(1,2,5,4,5)
	x <- cbind(x1,x2)
	rownames(x) <- 1:5

	# データを散布図にプロット
	plot(x, type="n")
	text(x, labels=rownames(x))

	# 個体間の距離を測定
	d <- dist(x)

	# 多次元尺度構成法
	loc <- cmdscale(d)
	plot(loc[, 1], loc[, 2], type="n")
	text(loc[, 1], loc[, 2], labels=rownames(x))

### 参考文献
- [Rと多次元尺度法](https://www1.doshisha.ac.jp/~mjin/R/27/27.html)
- [主座標分析について簡単に紹介するよ！ - ほくそ笑む](http://d.hatena.ne.jp/hoxo_m/20120313/p1)

主座標分析(Principal Coordinate Analysis; PCoA)

----------

# Heat Map
ヒートマップ

    example(heatmap)

[You probably don’t understand heatmaps](http://www.opiniomics.org/you-probably-dont-understand-heatmaps/)

`heatmap`関数はデフォルトではデータを行で正規化(scale)する。遺伝子発現プロファイルの「形状」に基づいてクラスタリングするには、[ユークリッド距離](https://ja.wikipedia.org/wiki/ユークリッド距離)ではなく、[相関係数](https://ja.wikipedia.org/wiki/相関係数)を利用する。

### Know your distance measure

4遺伝子について8時点の遺伝子発現量の値が観測されている。

	h1 <- c(10,20,10,20,10,20,10,20)
	h2 <- c(20,10,20,10,20,10,20,10)

	l1 <- c(1,3,1,3,1,3,1,3)
	l2 <- c(3,1,3,1,3,1,3,1)

	mat <- rbind(h1,h2,l1,l2)

	par(mar=c(4,4,1,1))
	plot(1:8,rep(0,8), ylim=c(0,35), pch="", xlab="Time", ylab="Gene Expression")

	for (i in 1:nrow(mat)) {
	 lines(1:8,mat[i,], lwd=3, col=i)
	}

	legend(1,35,rownames(mat), 1:4, cex=0.7)

高発現遺伝子ペア(h1,h2)の形状は正反対。低発現遺伝子ペア(l1,l2)も同様。

![](http://www.opiniomics.org/wp-content/uploads/2015/03/gex.png)

`heatmap`関数はデフォルトでは`dist()`関数で非類似度（距離）を計算する。  
`dist()`関数はデフォルトでは[ユークリッド距離](https://ja.wikipedia.org/wiki/ユークリッド距離)（2点間の差の2乗和の平方根）を計算する。

	dist(mat)

階層的クラスター分析

l1とl2との間の距離が最小(5.65)なので、この2つの遺伝子を結合してクラスター(l1,l2)とする。
次に、h1とh2との間の距離が最小(28.28)なので、この2つの遺伝子を統合してクラスター(h1,h2)とする。
最後に、(l1,l2)と(h1,h2)を結合する。

	hc <- hclust(dist(mat))
	plot(hc)

![](http://www.opiniomics.org/wp-content/uploads/2015/03/hclust.png)

ヒートマップ

    #install.packages("gplots")
    library(gplots)

	heatmap(mat, Colv=NA, col=greenred(10))
    # Colv = NA で列の樹形図（column dendrogram）を描かない
    # 色 col = rainbow, heat.colors, topo.colors, terrain.colors

![](http://www.opiniomics.org/wp-content/uploads/2015/04/heatmap1.png)

(h1,h2)は、クラスターを形成するが、色のパターンは正反対。(l1,l2)も同様。

### Understand scaling

`heatmap`関数はデフォルトではデータを行で正規化する`(scale = "row")`、各行の平均が0、標準偏差が1となるように変換する。  
正規化しない`(scale = "none")`で**[ユークリッド距離](https://ja.wikipedia.org/wiki/ユークリッド距離)**でクラスタリングしたヒートマップを作成:  

	heatmap(mat, Colv=NA, col=greenred(10), scale="none")
    # scale = c("row", "column", "none")

![](http://www.opiniomics.org/wp-content/uploads/2015/04/heatmap2.png)

(l1,l2)は緑、(h1,h2)は赤/黒。
ヒートマップでは通常、緑色は低い値、赤色は高い値、黒色は中間の値を示す。
正規化しない場合、l1とl2は低い値（緑色）、h1とh2は高い値（赤色）と中間の値（黒色）。

### Improving things

遺伝子発現プロファイルに関して、h1とl1は同じ形状、h2とl2は同じ形状。
[ユークリッド距離](https://ja.wikipedia.org/wiki/ユークリッド距離)は、2点間の絶対的な距離だけを測定し、形状を考慮しない。
2つのプロファイルの「形状」でクラスタリングするには、[相関係数](https://ja.wikipedia.org/wiki/相関係数)を利用する。相関係数は、−1（形状が正反対）から1（形状が同一）までの値をとる。

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d4/Correlation_examples2.svg/506px-Correlation_examples2.svg.png)

	# correlation matrix
	cor(t(mat))

	# distance
	1 - cor(t(mat))

	# cluster analysis
	hc <- hclust(as.dist(1-cor(t(mat))))
	plot(hc)

![](http://www.opiniomics.org/wp-content/uploads/2015/03/hclust_corr.png)

	# heatmap
	heatmap(mat, Rowv=as.dendrogram(hc), Colv=NA, col=greenred(10))

![](http://www.opiniomics.org/wp-content/uploads/2015/04/heatmap3.png)

### 参考文献
- [ヒートマップ heatmap | R,マイクロアレイなどの遺伝子発現量の図示などによく使われる](http://stat.biopapyrus.net/graph/heatmap.html)
- [アメリエフのブログ | heatmap.2のlmatオプション](http://blog.amelieff.jp/?eid=229489)
- [heatmap 関数について調べてみた - Panda Analysis](http://panda-nikki.hatenablog.jp/entry/20131209/1386600203)
- [Rでheatmapを作成｜Shigeru Hanano｜note](https://note.mu/shigeruhanano/n/naca751f9a547)
- [干からびたウェット教授の独習でアール R](http://datator.exblog.jp/tags/ヒートマップ/)
- [バイオ系のためのR覚書：Heatmap.2の使い方覚書 - あなたにもできる！ハーバード留学！！～アラフォーからのボストン留学体験記](http://blog.goo.ne.jp/maromato2012/e/7673e6fe8e78ee02eaf4c3fe5e3f8053)
- [統合TV | 生命科学系DB・ツール使い倒し系チャンネル | 統計解析ソフト「R」の使い方 〜ヒートマップ編〜](http://togotv.dbcls.jp/ja/20091219.html)

----------




