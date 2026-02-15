[生命動態のデータサイエンス](https://github.com/haruosuz/DS4GD)

----------

# [Clustering](https://en.wikipedia.org/wiki/Clustering)

- [Cluster Analysis](#cluster-analysis)
- [Heat Map](#heat-map)

----------

# [Cluster Analysis](https://en.wikipedia.org/wiki/Cluster_analysis)
クラスター分析

[データ・クラスタリング](https://ja.wikipedia.org/wiki/データ・クラスタリング)は、データ解析手法（特に多変量解析手法）の一種。教師なしデータ分類手法、つまり与えられたデータを外的基準なしに自動的に分類する手法。

![https://www.albert2005.co.jp/knowledge/data_mining/cluster/hierarchical_clustering](https://www.albert2005.co.jp/knowledge/images/tech_mining_img77.jpg)  

### 変数が2個の場合のクラスター分析
簡単な例として、5個の個体について2個の変数（増殖期と定常期の遺伝子発現量）の値が観測されている場合を例にとり、 クラスター分析を行なう。

	# 5個体について2変数(x1,x2)の値が格納された行列データを作成
	x1 <- c(5,4,1,5,5)
	x2 <- c(1,2,5,4,5)
	x <- cbind(x1,x2)
	rownames(x) <- 1:5

	# データを散布図にプロット
	plot(x, type="n")
	text(x, labels=rownames(x))

	# クラスターの結合方法
	# dist()関数で個体間の非類似度（距離）を測定
	d <- dist(x, method="euclidean") # ユークリッド距離（2点間の差の2乗和の平方根）
	d <- dist(x, method="manhattan") # マンハッタン距離（2点間の差の絶対値の総和）

	# hclust()関数で階層的クラスター分析
	hclust(d)
	hc <- hclust(d, method="single")   # 最短距離法
	hc <- hclust(d, method="complete") # 最長距離法
	hc <- hclust(d, method="average")  # 群平均法 (UPGMA)

	# グループの形成方法

	# 樹形図（Cluster Dendrogram）
	plot(hc)

	# 階層的クラスターの周りに四角形を描画
	plot(hc, hang = -1)
	rect.hclust(hc, h = 3.5) # 切断する距離を指定
	rect.hclust(hc, k = 3)   # グループの数を指定

	# 樹形図を切断してグループを形成
	cutree(hc, h = 3.5) # 切断する距離を指定
	cutree(hc, k = 3)   # グループの数を指定

	# 行列データとクラスタリング結果を結合し、ファイル出力
	g23 <- cutree(hc, k = c(2,3))
	write.csv(cbind(x,g23), file="table.csv")

	# 多次元尺度構成法 Multidimensional Scaling
	# 主座標分析 Principal Coordinate Analysis (PCoA)
	d <- dist(x)
	loc <- cmdscale(d)
	plot(loc[, 1], loc[, 2], type="n")
	text(loc[, 1], loc[, 2], labels=rownames(x))

### 変数がp個の場合のクラスター分析
3本のタンパク質配列について3個の変数（アミノ酸 Ala, Val, Cysの含量）の値が観測されている。
ユークリッド距離を用いた最長距離法でクラスター分析を行う。

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
- 分析力をコアとするデータソリューションカンパニー・株式会社ALBERT（アルベルト）
  - [クラスター分析の手法1（概要）](http://www.albert2005.co.jp/technology/mining/cluster1.html)
  - [クラスター分析の手法2（階層クラスター分析）](http://www.albert2005.co.jp/technology/mining/cluster2.html)
- 三中信宏（農環研・計測情報）
  - [分類学と系統学：ある蜜月の終焉](http://www.e-jsps.com/2007hp/topic/Datesoudo84/mitsu.html)
  - [クラスター分析の光と闇](http://cse.naro.affrc.go.jp/minaka/R/R-cluster.html) | [pdf](http://cse.naro.affrc.go.jp/minaka/R/clustering-04.pdf)
- [Rによる階層的クラスタリング](http://bio-info.biz/tips/r_hclust.html)
- [JIN'S PAGE](http://www1.doshisha.ac.jp/~mjin/R/)
  - [Rとクラスター分析(1)](http://www1.doshisha.ac.jp/~mjin/R/Chap_28/28.html)
  - [Rとクラスター分析(2)](http://www1.doshisha.ac.jp/~mjin/R/Chap_29/29.html)
  - [Rと多次元尺度法](http://www1.doshisha.ac.jp/~mjin/R/Chap_27/27.html)
- [多次元尺度構成法](https://ja.wikipedia.org/wiki/多次元尺度構成法)
  - [主座標分析について簡単に紹介するよ！ - ほくそ笑む](http://d.hatena.ne.jp/hoxo_m/20120313/p1)

----------

### standard score
https://ja.wikipedia.org/wiki/標準得点

	標準得点 (z得点) = (得点 - 平均値) / 標準偏差

	x <- seq(0, 100, 5)
	plot(x,dnorm(x, mean=70, sd=10), type="n")
	# Math
	curve(dnorm(x, mean=60, sd=20), type="l", add=TRUE)
	abline(v = 80, lty=2)
	(80 - 60) / 20
	# Japanese
	curve(dnorm(x, mean=70, sd=10), type="l", add=TRUE, col=2)
	abline(v = 85, lty=2, col=2)
	(85 - 70) / 10

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/60.html
60. 確率分布と乱数

http://leeswijzer.org/R/R-intro17.pdf
https://rpubs.com/leeswijzer/10254
正規分布に関連する関数

----------

# Heat Map
[ヒートマップ](https://ja.wikipedia.org/wiki/ヒートマップ)

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
正規化しない`(scale = "none")`で[ユークリッド距離](https://ja.wikipedia.org/wiki/ユークリッド距離)でクラスタリングしたヒートマップを作成:  

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

### References

2017.12.29
https://stats.biopapyrus.jp/r/graph/heatmap.html
ヒートマップ | R で遺伝子発現量などをヒートマップに描く方法

2016-07-06
https://yoshi-nishikawa.hatenablog.com/entry/2016/07/06/081632
Rでヒートマップをつくる - Yoshi Nishikawa Blog

2015-12-20 21:57:38
https://blog.goo.ne.jp/maromato2012/e/7673e6fe8e78ee02eaf4c3fe5e3f8053
バイオ系のためのR覚書：Heatmap.2の使い方覚書 - あなたにもできる！ハーバード留学！！～アラフォーからのボストン留学体験記

2015年8月14日 09:47
https://note.com/shigeruhanano/n/naca751f9a547
Rでheatmapを作成｜Shigeru Hanano （花野 滋）｜note

2015-06-12
https://staffblog.amelieff.jp/entry/2015/06/12/153939
heatmapの横に色をつけるオプション - アメリエフの技術ブログ

2015-04-15
https://staffblog.amelieff.jp/entry/2015/04/15/142537
heatmap.2のlmatオプション - アメリエフの技術ブログ

2009.12.19
https://doi.org/10.7875/togotv.2009.114
統計解析ソフト「R」の使い方 〜ヒートマップ編〜 | TogoTV

http://datator.exblog.jp/tags/ヒートマップ/
干からびたウェット教授の独習でアール R


----------




