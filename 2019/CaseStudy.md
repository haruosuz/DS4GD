**[生命情報解析 / 生命動態のデータサイエンス [DS2]](https://github.com/haruosuz/DS4GD/tree/master/2019)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「Introduction to R」
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages seqinr & Biostrings」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [NCBI ASSEMBLY_REPORTS](#ncbi-assembly_reports)
- [NCBI GENOME_REPORTS](#ncbi-genome_reports)
- [2019-07-09](#2019-07-09)
- [Coding sequences](#coding-sequences) タンパク質コード配列
  - [codon usage](#codon-usage) コドン使用
  - [amino acid usage](#amino-acid-usage) アミノ酸使用
- [assignment 7](#assignment-7) 課題No.7 「dotplot」
- [assignment 11](#assignment-11) 課題No.11 「Pairwise Sequence Alignment」
- [assignment 12](#assignment-12) 課題No.12 「draft report」
- [assignment 13](#assignment-13) 課題No.13 「presentation slides」

----------

https://twitter.com/Symbionticism/status/1123203760564637697
Seth Bordenstein on Twitter: "This is a game changer. Many intracellular microbes have a genome wide bias in A’s and T’s. The major assumption has been a mutational bias / drift impacts this outcome. Well, not so fast. Evidence below that selection can contribute or cause it.… https://t.co/yfDqN3b3Lj"
8:33 AM - 30 Apr 2019
https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1007778
Selective advantages favour high genomic AT-contents in intracellular elements
Accordingly, introducing AT-rich and GC-rich plasmids into other bacterial species with different genomic GC-contents revealed that the costs of G+C-rich plasmids decreased with an increasing GC-content of their host’s genomic DNA. 

----------
## assignment 0
**選抜課題**

【課題内容】
本授業で解析したい生物（ゲノム/遺伝子/タンパク質）配列を300文字以内で述べてください。課題のタイトルと参考文献も明記してください。

DNAまたはタンパク質の配列を検索するには、

- NCBIウェブサイト (https://www.ncbi.nlm.nih.gov) にアクセスし、ウェブページ上部の検索ボックスにキーワード（例えば、"Candidatus Midichloria mitochondrii"）を入力して、"Search"ボタンを押す
https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#retrieving-genome-sequence-data-via-the-ncbi-website

または

- UniProtウェブサイト (http://www.uniprot.org) にアクセスし、ウェブページ上部の検索ボックスにキーワード（例えば、"antibiotic resistance Clostridium difficile"）を入力して、"Search"ボタンを押す
https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#viewing-the-uniprot-webpage-for-a-protein-sequence

---

Please describe DNA or protein sequences you're interested in. Please also state your project title and references.

To find DNA or protein sequences,

- go to the NCBI website (https://www.ncbi.nlm.nih.gov), type keywords (e.g. "Candidatus Midichloria mitochondrii") in the Search box at the top of the webpage, and press the “Search” button beside the Search box.
http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#retrieving-genome-sequence-data-via-the-ncbi-website

or

- go the UniProt website (http://www.uniprot.org). At the top of the UniProt website, you will see a search box, and you can type keywords (e.g. "antibiotic resistance Clostridium difficile") that you are looking for in this search box, and then click on the “Search” button to search for it.
http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#viewing-the-uniprot-webpage-for-a-protein-sequence

----------
## assignment 1
**課題No.1 「Introduction to R」**    

以下の何れかの動画レッスンを見て、疑問点を報告する。
Watch one of the following videos and write your comments or questions.
- [R言語入門 (全13回)](http://dotinstall.com/lessons/basic_r)
- [Introduction to R](https://www.youtube.com/watch?v=WiO44CiSPF0&list=PL8eNk_zTBST_KL2gnciUv1oor0ECw8Hqg)


[回答例]
[Example answer]

[R言語入門 (全13回)](http://dotinstall.com/lessons/basic_r)の動画レッスン番号 #03 ~ #13 を見た。疑問点は次の通りである。
1. 行列とデータフレームとリストの違いが理解できなかった。
2. 因子ベクトルというものがよくわからなかった。

I watched the videos #3 to #13 of [Introduction to R](https://www.youtube.com/watch?v=WiO44CiSPF0&list=PL8eNk_zTBST_KL2gnciUv1oor0ECw8Hqg). My questions are as follows:
1. What is difference between dataframe and list in R? 

----------
## assignment 2
**課題No.2 「Installing R packages seqinr & Biostrings」**

RパッケージseqinrとBioconductorパッケージBiostringsをインストールする。

パッケージseqinrのインストール:  

    # Install the "seqinr" package:
    install.packages("seqinr")

BioconductorパッケージBiostringsのインストール:  

    # Install the Bioconductor package called "Biostrings":
    source("https://bioconductor.org/biocLite.R")
    biocLite("Biostrings")

パッケージの呼び出し:  

    # Load the packages into R:
    library("seqinr")
    library("Biostrings")

Rパッケージのバージョンを確認:  

    # Print the versions of these packages:
    packageVersion("seqinr")
    packageVersion("Biostrings")

Rのバージョンを確認:  

    # Print the version of R running:
    R.version.string

回答例:  

    # Example answer:  

    > packageVersion("seqinr")
    [1] ‘3.4.5’

    > packageVersion("Biostrings")
    [1] ‘2.42.1’

    > R.version.string
    [1] "R version 3.3.3 (2017-03-06)"

Record the version of R and R packages by the `sessionInfo()` function.

    > sessionInfo()
    R version 3.3.3 (2017-03-06)
    Platform: x86_64-apple-darwin13.4.0 (64-bit)
    Running under: OS X Mavericks 10.9.5

References:

https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages

----------

## NCBI Genome List
[NCBI](https://integbio.jp/dbcatalog/record/nbdc00584)
[国立生物工学情報センター](https://ja.wikipedia.org/wiki/国立生物工学情報センター)
の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。
例えば、[シノリゾビウム属](https://ja.wikipedia.org/wiki/シノリゾビウム属)に属する種*Sinorhizobium meliloti*を検索する。
[ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Sinorhizobium%20meliloti)、検索ボックス下の「Overview (1); Eukaryotes (0); Prokaryotes (204); Viruses (0); Plasmids (65); Organelles (0)」のうち、「Prokaryotes」をクリックすると、*Sinorhizobium meliloti*に属する菌株**Strain**が表示される。
[ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Sinorhizobium%20meliloti)、列**Organism Name**の"Sinorhizobium meliloti 1021"株をクリックして開く。
[ここで](https://www.ncbi.nlm.nih.gov/genome/1004?genome_assembly_id=300472)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に識別子 (Accession) が示されている。
列**Type**のChrは染色体、Plsmはプラスミドを指す。

複数のレプリコン（染色体とプラスミド）を保有する細菌の例:
```
Agrobacterium tumefaciens str. C58 | 4 replicons (chromosome circular; chromosome linear; plasmid At; plasmid Ti)
Aureimonas sp. AU20 | 9 replicons (plasmid pAU20rrn)
炭疽菌 Bacillus anthracis str. 'Ames Ancestor' | chromosome; plasmid pXO1; plasmid pXO2
Borrelia burgdorferi B31 | 22 replicons
放射線耐性菌 Deinococcus radiodurans R1 | chromosome 1; chromosome 2; plasmid CP1; plasmid MP1
コレラ菌 Vibrio cholerae O1 biovar El Tor str. N16961 | chromosome I; chromosome II
ウェルシュ菌 Clostridium perfringens str. 13 (plasmid pCP13)
Cupriavidus necator (a.k.a. Ralstonia eutropha) JMP134 (IncP­-1 plasmid pJP4)
腸管出血性大腸菌 Escherichia coli O157:H7 str. Sakai (plasmid pO157, pOSAK1)
大腸菌 Escherichia coli SMS-3-5 (IncF plasmid pSMS35_130)
Geobacter lovleyi SZ
Mycobacteroides abscessus subsp. bolletii (IncP-1β plasmid pMAB01)
Pseudomonas resinovorans NBRC 106553 (strain CA10; IncP-­7 plasmid pCAR1.3)
サルモネラ チフス菌 Salmonella enterica subsp. enterica serovar Typhi str. CT18 (plasmid pHCM1, pHCM2)
サルモネラ ネズミチフス菌 Salmonella enterica subsp. enterica serovar Typhimurium str. SL1344 (IncQ plasmid pRSF1010_SL1344)
アルファルファ根粒菌 Sinorhizobium meliloti 1021 (plasmid pSymA, pSymB)
ペスト菌 Yersinia pestis CO92 (plasmid pCD1, pPCP1, pMT1)
```

[ゲノム　第4版](https://www.medsi.co.jp/books/products/detail.php?product_id=3642)
第8章 原核生物ゲノムと真核生物の細胞小器官ゲノム
| 8.1 原核生物ゲノムの構造的特徴
| 一部の細菌は直鎖状ゲノムや分節ゲノムをもつ
| 表8.1 代表的なプラスミドの特徴
| 表8.2 原核生物のゲノム構成の例

NCBIからDNA配列を取得する:  

    # Retrieving a DNA sequence from NCBI
    library("seqinr")
    ACCESSION <- "NC_001477" # Dengue virus 1
    #ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
    #ACCESSION <- "NC_003047" # Sinorhizobium meliloti 1021 chromosome
    #ACCESSION <- "NC_003037" # Sinorhizobium meliloti 1021 plasmid pSymA
    #ACCESSION <- "NC_003078" # Sinorhizobium meliloti 1021 plasmid pSymB
    #ACCESSION <- "NC_001318" # Borrelia burgdorferi B31 chromosome
    #ACCESSION <- "NC_000908" # Mycoplasma genitalium G37, complete genome
    filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta") # http://togows.dbcls.jp/help/
    seqs <- read.fasta(file = filename, seqtype = c("DNA"), strip.desc = TRUE)
    seq1 <- seqs[[1]]

----------
## assignment 3
**課題No.3 「DNA Sequence Statistics (1)」**

[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. What are the last twenty nucleotides of the genome sequence?

    seq1[(length(seq1)-20+1):length(seq1)]

Q2. What is the length in nucleotides of the genome sequence?

    length(seq1)

Q3. How many of each of the four nucleotides A, C, T and G, and any other symbols, are there in the genome sequence?

    table(seq1)

[DDBJ 配列の記載に用いる略号](http://www.ddbj.nig.ac.jp/sub/code-j.html)

Q4. What is the GC content of the genome sequence, when (i) all non-A/C/T/G nucleotides are included, (ii) non-A/C/T/G nucleotides are discarded?

	help("GC")
    GC(seq1)
    GC(seq1, exact=FALSE)
    GC(seq1, exact=TRUE)

Q5. How many of each of the four nucleotides A, C, T and G are there in the complement of the genome sequence?

![http://revertra.webcrow.jp/DNA/index.php](http://revertra.webcrow.jp/DNA/dnaseq.png)

	help.search("complement")
	help("comp")
    table(comp(seq1))

Q6. How many occurrences of the DNA words CC, CG and GC occur in the genome sequence?

    count(seq=seq1, wordsize=2)

Q7. How many occurrences of the DNA words CC, CG and GC occur in the (i) first 1000 and (ii) last 1000 nucleotides of the genome sequence?
How can you check that the subsequence that you have looked at is 1000 nucleotides long?

    count(seq=seq1[1:1000], wordsize=2)
    count(seq=seq1[(length(seq1)-1000+1):length(seq1)], wordsize=2)

----------
## assignment 4
**課題No.4 「DNA Sequence Statistics (2)」**

[Exercises on DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

[53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
フォント・ファミリーを指定する．

    par(family="mono")

Q1. Draw a sliding window plot of GC content in the genome, using a window size of 200 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# write a function to make a sliding window plot:
    slidingwindowplotGC <- function(windowsize, inputseq)
    {
      require("zoo") # this function requires the 'zoo' R package # install.packages('zoo')
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = GC)
      plot(x, y, type="l", xlab="Position (bp)", ylab="GC content")
    }

	# make a sliding window plot with a window size of 200 nucleotides:
    slidingwindowplotGC(200, seq1)

Q2. Draw a sliding window plot of GC content in the genome sequence using a window size of 2000 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# make a sliding window plot of GC content using a window size of 2000 nucleotides:
    slidingwindowplotGC(2000, seq1)

Q3. Write a function to calculate the AT content of a DNA sequence (ie. the fraction of the nucleotides in the sequence that are As or Ts). What is the AT content of the genome?

	# Here is a function to calculate the AT content of a genome sequence:
    AT <- function(x){ library("seqinr"); 1 - GC(x) }

    # use the function to calculate the AT content of the genome:
    AT(seq1)

    # AT = 1 - GC, ie. (AT + GC = 1):
    GC(seq1)
    AT(seq1) + GC(seq1)

Q4. Write a function to draw a sliding window plot of AT content.

	# write a function to make a sliding window plot:
    slidingwindowplotAT <- function(windowsize, inputseq)
    {
      require("zoo")
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      AT <- function(x){ library("seqinr"); 1 - GC(x) }
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = AT)
      plot(x, y, type="b", xlab="Position (bp)", ylab="AT content")
    }

Use it to make a sliding window plot of AT content along the genome, using a windowsize of 2000 nucleotides. 

    par(mfrow=c(2,1))
	# make a sliding window plot of AT content:
    slidingwindowplotAT(2000, seq1)
	# This is the mirror image of the plot of GC content (because AT equals 1 minus GC):
    slidingwindowplotGC(2000, seq1)

Q5. Is the 3-nucleotide word GAC over-represented or under-represented in the genome sequence?

	# search for a function to calculate rho by typing:
	help.search("rho")

	# calculate Rho for words of length 3 in the genome
	rho(seq1, wordsize=3)

    # rho > 1: over-represented
    # rho < 1: under-represented

----------

## NCBI ASSEMBLY_REPORTS
NCBIのゲノム配列のメタデータが記載されている。

ftp://ftp.ncbi.nlm.nih.gov/genomes/README_assembly_summary.txt

	The assembly_summary files report metadata for the genome assemblies on the NCBI genomes FTP site.
	assembly_summary_genbank.txt            - current GenBank genome assemblies
	assembly_summary_refseq.txt             - current RefSeq genome assemblies

- April 9, 2018 [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
- 2018-10-23 [RefSeq - JI](http://fish-evol.org/RefSeq.html) 井上 潤
- 2017.03.12 [RefSeq | 詳細な注釈づけられている冗長性のない核酸データベース](https://bi.biopapyrus.jp/db/refseq.html)

NCBIウェブサイト (https://www.ncbi.nlm.nih.gov) にアクセスし、右下のリンク"NCBI FTP Site"をクリックして開く。  
<ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> をブラウザ（Firefox または Chrome）で開く。  
*assembly_summary_genbank.txt* または *assembly_summary_refseq.txt* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

Go to the NCBI website (https://www.ncbi.nlm.nih.gov), and then click the link "NCBI FTP Site".   
Open the URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> with your browser (Firefox or Chrome).  
Right click the link *assembly_summary_genbank.txt* or *assembly_summary_refseq.txt*, and select "Copy Link Address".

### Working with Data in R
Rの起動 [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/data/ncbi/assembly_reports/"

    # Invoke a System Command
    system( paste0("mkdir -p ",WorkingDirectory) )

    # Set and Get Working Directory
    setwd(WorkingDirectory)
    getwd()

    # List the Files in a Directory
    dir()

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_genbank.txt"
    #curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt"
    download.file(url = curl, destfile = basename(curl))

[Ｒ言語のデータの入出力と編集](https://www.cis.doshisha.ac.jp/mjin/R/02.html)

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    # Loading Data into R
    filename <- basename(curl)
    d <- read.delim(file = filename, stringsAsFactors = FALSE, check.names = FALSE, skip = 1) 

[データフレーム](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html)の行と列の数、先頭部分、列名の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    head(d, n = 1)
    colnames(d)
    colnames(d)[1] <- "assembly_accession"

    table(d$refseq_category)
    table(d$assembly_level)

例えば、[シノリゾビウム属](https://ja.wikipedia.org/wiki/シノリゾビウム属)に属する種*Sinorhizobium meliloti*
の完全ゲノム("Complete Genome")配列データの最新版("latest")のURLを抽出する:  

List the ftp_path (column 20) for the assemblies of interest, in this case those that have organism_name of "Sinorhizobium meliloti" (column 8), "latest" version_status (column 11) and "Complete Genome" assembly_level (column 12)

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x).
    pattern <- "Sinorhizobium meliloti"
    #pattern <- "B.*burgdorferi" # "Borrelia burgdorferi"
    TF <- grepl(pattern = pattern, x = d$organism_name) & grepl(pattern = "reference|representative", x = d$refseq_category) & d$assembly_level == "Complete Genome" & d$version_status == "latest"
    d[TF,]
    d$ftp_path[TF]

抽出されたURLをブラウザFirefox/Chromeで開く。*README.txt*ファイルを右クリックし、「リンクのURLをコピー (Copy Link)」する。

Open the URL with your browser (Firefox or Chrome). Right click the link *README.txt*, and select "Copy Link Address".

ftp://ftp.ncbi.nlm.nih.gov/genomes/all/README.txt

[What is the file content within each specific assembly directory?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#files)

    *_genomic.fna.gz: FASTA format of the genomic sequence(s) in the assembly. 
    *_cds_from_genomic.fna.gz: FASTA format of the nucleotide sequences corresponding to all CDS features annotated on the assembly, based on the genome sequence.
    *_protein.faa.gz: FASTA format of the accessioned protein products annotated on the genome assembly.
    *_genomic.gbff.gz: GenBank flat file format of the genomic sequence(s) in the assembly. 

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    filesuffix <- "_genomic.fna.gz"
    #filesuffix <- "_cds_from_genomic.fna.gz"
    #filesuffix <- "_protein.faa.gz"
    curl <- paste0(d$ftp_path[TF], "/", unlist(strsplit(d$ftp_path[TF], split="/"))[10], filesuffix )
    download.file(url = curl, destfile = basename(curl))

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data and store them in list variable "seqs"
    library("seqinr") # Load the SeqinR package
    filename <- basename(curl)
    seqs <- read.fasta(file = filename, seqtype = c("DNA"), strip.desc = TRUE)
    #seqs <- read.fasta(file = gzcon(url(curl)), seqtype = c("DNA"), strip.desc = TRUE)

    length(seqs) # get the number of elements
    unlist(getAnnot(seqs)) # get sequence annotations

- [24. apply() ファミリー](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/24.html)

`sapply()`関数は、リストの各要素に関数を適用する。  
複数のDNA配列を解析する:  

    # Apply a Function over a List
    sapply(seqs, length)
    sapply(seqs, GC)

- [23. リスト](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html)

`unlist()`関数は、リストの要素を端からベクトルとして結合して 1 つのベクトルとしてまとめる。
複数のDNA配列の結合データを解析する:  

    # Flatten Lists
    length(unlist(seqs))
    GC(unlist(seqs))

### References

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/
Genomes Download FAQ

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#protocols
2. What is the best protocol to use to download large data sets?

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#files
11. What is the file content within each specific assembly directory?

*_cds_from_genomic.fna.gz
FASTA format of the nucleotide sequences corresponding to all CDS features annotated on the assembly, based on the genome sequence.

*_genomic.fna.gz
FASTA format of the genomic sequence(s) in the assembly. 

*_genomic.gbff.gz
GenBank flat file format of the genomic sequence(s) in the assembly. 

*_protein.faa.gz
FASTA format of the accessioned protein products annotated on the genome assembly.

http://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#howtofind
12. How can I find the sequence and annotation of my genome of interest?

Using the assembly summary report files

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#current
14. How can I download only the current version of each assembly?

Use either of the two master assembly summary files, or the assembly_summary.txt file for the species or taxonomic group of interest (see above), select those assemblies that are marked as "latest" in the version_status column (11), and then use the FTP path indicated in column 20 to download the data.

https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#allcomplete
15. How can I download RefSeq data for all complete bacterial genomes?

Append the filename of interest, in this case "*_genomic.gbff.gz" to the FTP directory names. One way to do this would be using the following awk command:

	awk 'BEGIN{FS=OFS="/";filesuffix="genomic.gbff.gz"}{ftpdir=$0;asm=$10;file=asm"_"filesuffix;print ftpdir,file}' ftpdirpaths > ftpfilepaths

----------
## NCBI GENOME_REPORTS

ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)
の表のテキスト版をFTPサイトからダウンロードする。
<ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/> をブラウザ（Firefox または Chrome）で開く。 
*README*をクリックして開く。

```
eukaryotes.txt: Eukaryotic genome sequencing projects
prokaryotes.txt: Prokaryotic genome sequencing projects
viruses.txt:   Viral genome sequencing projects
```

Rの起動 [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/data/ncbi/genome_reports"

    # Invoke a System Command
    system( paste0("mkdir -p ",WorkingDirectory) )

    # Set and Get Working Directory
    setwd(WorkingDirectory)
    getwd()

    # List the Files in a Directory
    dir()

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prokaryotes.txt" # 原核生物 # 60.9 MB
    #curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/eukaryotes.txt" # 真核生物 # 2.1 MB
    #curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/viruses.txt"    # ウイルス # 4.7 MB
    download.file(url = curl, destfile = basename(curl))

[Ｒ言語のデータの入出力と編集](https://www.cis.doshisha.ac.jp/mjin/R/02.html)

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    # Loading Data into R
    filename <- basename(curl)
    d <- read.delim(file = filename, stringsAsFactors = FALSE, check.names = FALSE)

- [R – データフレームの参照・変更](http://taustation.com/r-datafrrame-display-modification/)

行と列の数、列名、先頭部分の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    colnames(d)
    head(d, n=1)

    table(d$Status)

[文字列 | R で文字列の切り出しや置換などの文字列処理を行う方法](https://stats.biopapyrus.jp/r/basic/string.html)

生物名 `#Organism/Name` で検索し抽出する:  
```
# grep(pattern, x) returns the positions of all elements in x that match pattern
# grepl returns a logical vector (match or not for each element of x).
Organism_Name <- "Sinorhizobium meliloti 1021"
#Organism_Name <- "Bacillus anthracis.*Ames Ancestor|E.*coli O157.*Sakai|JMP134"
TF <- grepl(pattern = Organism_Name, x = d$`#Organism/Name`)
sum(TF)
d[TF,]
```

複数のDNA配列をNCBIから取得する:  
```
# Retrieving a list of DNA sequences from NCBI

# Load the SeqinR package
library("seqinr")

# create a function to retrieve several nucleotide sequences from NCBI
retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)[[1]]

# Make a vector containing NCBI GenBank/RefSeq accessions
## create a system command to be invoked, as a character string

### viruses ウイルス
Organism_Name <- "orovirus"
command <- paste0("grep -v '^#' viruses.txt | awk -F '\t' '$1 ~ /", Organism_Name ,"/ && $10 !~ /-/ && $15 ~ /Complete Genome/ {print $0}' | cut -f10 | tr ';' '\n' | perl -pe 's/(.+:)*(([A-Z]+_*)[A-Z0-9]+)\\.[0-9]+.*/$2/g;'")

### eukaryotes 真核生物
Organism_Name <- "Saccharomyces cerevisiae S288C"
command <- paste0("grep -v '^#' eukaryotes.txt | awk -F '\t' '$1 ~ /", Organism_Name ,"/ {print $0}' | cut -f10 | tr ';' '\n' | perl -pe 's/.+:(([A-Z]+_*)[A-Z0-9]+)\\.[0-9]+.*/$1/g;'")

### prokaryotes 原核生物
Organism_Name <- "Sinorhizobium meliloti 1021"
#Organism_Name <- "Sinorhizobium meliloti 1021|Deinococcus radiodurans R1"
#Organism_Name <- "Bacillus anthracis.*Ames Ancestor|E.*coli O157.*Sakai|JMP134"
command <- paste0("grep -v '^#' prokaryotes.txt | awk -F '\t' '$1 ~ /", Organism_Name ,"/ {print $0}' | cut -f9 | tr ';' '\n' | perl -pe 's/.+:(([A-Z]+_*)[A-Z0-9]+)\\.[0-9]+.*/$1/g;'")
#command <- paste0("grep -v '^#' prokaryotes.txt | awk -F '\t' '$1 ~ /", Organism_Name ,"/ && $16 ~ /Complete Genome/ && $20 ~ /REFR/ {print $0}' | cut -f9 | tr ';' '\n' | perl -pe 's/.+:(([A-Z]+_*)[A-Z0-9]+)\\.[0-9]+.*/$1/g;'")

## Invoke a System Command
ACCESSIONs <- system(command, intern=TRUE)
#ACCESSIONs <- c("NC_003047", "NC_003037", "NC_003078") #Organism_Name <- "Sinorhizobium meliloti 1021"
ACCESSIONs

# Retrieve the sequences and store them in list variable "seqs"
seqs <- lapply(ACCESSIONs,  retrieve_ncbi_fna)
```

配列の数をカウントする:  

    # get the number of elements
    length(seqs)

配列の名前（アクセッション番号）を取得する:  

    # get sequence names
    getName(seqs)

配列のアノテーションを取得する:  

    # get sequence annotations
    getAnnot(seqs)

配列データをFASTA形式ファイルとして書き出す:  

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs, names=getAnnot(seqs), file.out="mySequences.fna", nbchar = 80)

    # open current working directory
    system("open .")

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    setwd("~/projects/data/ncbi/genome_reports")					# Set Working Directory
    library(seqinr)									# Load the SeqinR package
    seqs <- read.fasta(file = "mySequences.fna", seqtype = c("DNA"), strip.desc = TRUE)	# Reading sequence data

リスト`seqs`の1番目の要素を変数`seq1`に代入する:  

    # store the first element of the list object `seqs` in a variable `seq1`
    seq1 <- seqs[[1]]

### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)

`summary()`関数でデータの要約:  

    # Object Summaries
    summary(seq1)

DNA配列の長さ、塩基組成、GC含量 (length, composition, GC) が出力される。

DNA配列の2連続塩基含量（カウント）:  

    # DNA words
    count(seq=seq1, wordsize=2)

### [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)
連続塩基組成 [Over-represented and under-represented DNA words](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#over-represented-and-under-represented-dna-words)

DNA配列の2連続塩基組成（観測値/期待値）:  

    # Over-represented and under-represented DNA words
    rho(seq = seq1, wordsize=2)

[53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
関数 par()

[50. 高水準作図関数](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/50.html)
棒グラフ：barplot()

[51. 低水準作図関数](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/51.html)
直線
abline

    par(family="mono")
    par(cex = 0.7)

    barplot(sort(rho(seq1, wordsize = 2)))
    abline(h=1)

- [applyファミリー | R で同じ処理を”並列的”に実行する関数](https://stats.biopapyrus.jp/r/basic/apply.html)

```
# Apply a Function over a List
lapply(seqs, summary)
sapply(seqs, summary)
```

DNA配列の長さ、G+C含量、アノテーションのテーブルを作成する:  
```
# Apply a Function over a List
Length <- sapply(seqs, length)
GCcontent <- sapply(seqs, GC)
Annotation <- unlist(getAnnot(seqs))
df <- data.frame(Length, GCcontent, Annotation)
```

- [CSVやTSVで出力](http://a-habakiri.hateblo.jp/entry/2016/12/12/222806)

データのエクスポート。  
`write.csv`関数でカンマ区切りファイルとして出力する:  
`write.table`関数でタブ区切りファイルとして出力する:  

    # Exporting Data
    write.csv(df, file="table.csv", quote=TRUE, row.names=TRUE)
    write.table(df, file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names=NA)

    # open current working directory
    system("open .")

複数のDNA配列の2連続塩基組成（観測値/期待値）を解析する:  

    # Apply a Function over a List
    X <- sapply(seqs, rho, wordsize = 2)

#### colnames

[26. names 属性と要素のラベル](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/26.html)

```
# Exploring and Transforming Dataframes
dim(X)
colnames(X)
colnames(X) <- getName(seqs) # get sequence names
colnames(X) <- getAnnot(seqs) # get sequence annotations

# Substrings # e.g. "NC_003047.1 Si"
#colnames(X) <- substr(getAnnot(seqs), 1, 14)

# Genus Species # e.g. "Sinorhizobium meliloti"
#colnames(X) <- sapply(getAnnot(seqs), function(x) paste0(unlist(strsplit(x, split=" "))[2:3], collapse=" ") )

# Accession Replicon # e.g. "NC_003047.1 chromosome", "NC_003037.1 plasmid pSymA", "NC_003078.1 plasmid pSymB"
#colnames(X) <- sub(pattern="([^ ]+) ([^ ]+) (.+ (chromosome.*|.*plasmid.*|.+'|DNA)), .+", replacement="\\1 \\4", getAnnot(seqs))

# Accession Genus Name # e.g. "NC_003037.1 Sinorhizobium pSymA"
#colnames(X) <- sub(pattern="([^ ]+) ([^ ]+) (.+) ([^ ]+), complete .+", replacement="\\1 \\2 \\4", getAnnot(seqs))
```

[50. 高水準作図関数](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/50.html)
matplot()

    matplot(X, type="l", col=1:ncol(X), lty=1:ncol(X))
    legend("bottomleft", legend=colnames(X), col=1:ncol(X), lty=1:ncol(X))

クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)

    # Hierarchical Clustering
    plot(hclust(dist(t(X))), hang=-1)

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    # Draw a Heat Map
    heatmap(X, margins=c(14, 2), cexCol=0.9, scale="none", col=rev(gray.colors(12)))

[Flip color range of heatmap in base R - Stack Overflow](https://stackoverflow.com/questions/56101927/flip-color-range-of-heatmap-in-base-r)

### References
オリゴヌクレオチド組成の解析
- [Takahashi M et al. (2009) "Estimation of bacterial species phylogeny through oligonucleotide frequency distances."](https://www.ncbi.nlm.nih.gov/pubmed/19442633)
- [Suzuki H et al. (2008) "Using Mahalanobis distance to compare genomic signatures between bacterial plasmids and chromosomes."](https://www.ncbi.nlm.nih.gov/pubmed/18953039)
- [Wong K et al. (2002) "Dinucleotide compositional analysis of Sinorhizobium meliloti using the genome signature: distinguishing chromosomes and plasmids."](https://www.ncbi.nlm.nih.gov/pubmed/12444420)
- [Campbell A et al. (1999) "Genome signature comparisons among prokaryote, plasmid, and mitochondrial DNA."](https://www.ncbi.nlm.nih.gov/pubmed/10430917)

![](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC17754/bin/pq1692140001.jpg)

----------
## 2019-07-09
[NCBI GENOME_REPORTS](#ncbi-genome_reports)

Rの起動 [Running R](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#running-r)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/data/ncbi/genome_reports"
    #system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
    setwd(WorkingDirectory); getwd() # Set and Get Working Directory
    dir() # List the Files in a Directory

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    # Loading Data into R
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prokaryotes.txt"
    #download.file(url = curl, destfile = basename(curl))
    filename <- basename(curl)
    d <- read.delim(file = filename, stringsAsFactors = FALSE, check.names = FALSE)

行と列の数、列名、先頭部分の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    colnames(d)
    head(d, n=1)

複数のDNA配列をNCBIから取得する:  
```
# Retrieving a list of DNA sequences from NCBI
library("seqinr") # Load the SeqinR package
# create a function to retrieve several nucleotide sequences from NCBI
retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)[[1]]

# Make a vector containing NCBI GenBank/RefSeq accessions
## create a system command to be invoked, as a character string
Organism_Name <- "Bacillus anthracis.*Ames Ancestor|E.*coli O157.*Sakai"
command <- paste0("grep -v '^#' prokaryotes.txt | awk -F '\t' '$1 ~ /", Organism_Name ,"/ {print $0}' | cut -f9 | tr ';' '\n' | perl -pe 's/.+:(([A-Z]+_*)[A-Z0-9]+)\\.[0-9]+.*/$1/g;'")
## Invoke a System Command
ACCESSIONs <- system(command, intern=TRUE)
ACCESSIONs

# Retrieve the sequences and store them in list variable "seqs"
seqs <- lapply(ACCESSIONs,  retrieve_ncbi_fna)
```

配列の数とアノテーションを確認する:  
```
length(seqs) # get the number of elements
unlist(getAnnot(seqs)) # get sequence annotations
```

#### [k-mer frequency](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#over-represented-and-under-represented-dna-words)

k=2,3,4連続塩基組成を解析する:
```
# Over-represented and under-represented DNA words
 k = 2 # 2-mers or dinucleotide
#k = 3 # 3-mers or trinucleotide
#k = 4 # 4-mers or tetranucleotide
myrho <- sapply(seqs, rho, wordsize = k)

# Exploring and Transforming Dataframes
dim(myrho)
colnames(myrho) <- getName(seqs) # get sequence names
colnames(myrho)
```

#### [clustering](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)
クラスタリング

[距離行列 distance matrix](https://ja.wikipedia.org/wiki/距離行列)
```
# Calculating distances between sequences
mydist <- dist(t(myrho), method = "euclidean")
```

距離行列を用いて、[非加重結合法 Unweighted Pair Group Method with Arithmetic mean (UPGMA)](https://ja.wikipedia.org/wiki/非加重結合法) により樹 tree を構築する:
```
# Hierarchical Clustering
hc <- hclust(mydist, method = "average") # UPGMA

par(family="mono")
plot(hc, hang = -1)
```

距離行列を用いて、[近隣結合法 Neighbor-Joining (NJ)](https://ja.wikipedia.org/wiki/近隣結合法) により樹 tree を構築する:
```
# 無根樹の構築
# Building an unrooted tree
library(ape) # install.packages("ape")
mytree <- nj(mydist)
plot.phylo(mytree, type = "unrooted")

# 有根樹の構築
# Building a rooted tree
library(phangorn) # install.packages("phangorn")
mytree <- midpoint(mytree) # midpoint rooting
plot.phylo(ladderize(mytree, right = FALSE), main = "Neighbor-Joining midpoint rooted tree", cex=0.9)

# Newick形式ファイルとして保存する
# Saving a tree as a Newick-format tree file
write.tree(mytree, file="mytree.newick")

# open current working directory
system("open .")
```

Newick形式ファイルから[SeaView](http://doua.prabi.fr/software/seaview)で樹 tree を描く。

### References
- 多重配列アライメントと系統樹 [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
- 三中信宏 (2003) クラスター分析の光と闇 ――なぜヒトは分類に憑かれるのか？―― [html](http://cse.naro.affrc.go.jp/minaka/R/R-cluster.html) [pdf](http://cse.naro.affrc.go.jp/minaka/R/clustering-04.pdf)
- 2016-09-10 [「種問題」ははてしなく続く - archief voor stambomen](http://leeswijzer.hatenablog.com/entry/2016/09/10/102132)

----------


## [Coding sequences](https://github.com/haruosuz/DS4GD/blob/master/2017/CaseStudy.md#annotation-of-coding-sequences)
- [Coding region](https://en.wikipedia.org/wiki/Coding_region)
- [DDBJ タンパク質コード配列; CDS feature について](https://www.ddbj.nig.ac.jp/ddbj/cds.html)
- [オープンリーディングフレーム](https://ja.wikipedia.org/wiki/オープンリーディングフレーム) (Open Reading Frame; ORF)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/data/ncbi/eutils"
    system( paste0("mkdir -p ",WorkingDirectory) ) # Invoke a System Command
    setwd(WorkingDirectory); getwd() # Set and Get Working Directory
    dir() # List the Files in a Directory

[NCBI Genome List](#ncbi-genome-list)
でゲノムを探す。
- [Tardigrada](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Tardigrada) [ヨコヅナクマムシ (Ramazzottius varieornatus) ゲノム配列データの公開](https://www.ddbj.nig.ac.jp/news/ja/wn160915.html)
- [ミディクロリア](https://ja.wikipedia.org/wiki/ミディクロリア) [Candidatus Midichloria mitochondrii](https://www.ncbi.nlm.nih.gov/genome/2543) はミトコンドリアに細胞内共生する細菌である。
- [サルモネラ](https://ja.wikipedia.org/wiki/サルモネラ) ネズミチフス菌 [Salmonella enterica subsp. enterica serovar Typhimurium str. SL1344](https://www.ncbi.nlm.nih.gov/genome/152?genome_assembly_id=154382) のプラスミド pRSF1010_SL1344 は、IncQグループに属する広宿主域 broad host range プラスミドである ([新谷ら, 2013](https://www.jseb.jp/wordpress/wp-content/uploads/13-02-125.pdf))。

[E-utilities](https://github.com/haruosuz/bioinfo/blob/master/references/README.bioinfo.tools.md#e-utilities)を用いて、
NCBIから配列データを取得する:  
```
# Retrieving sequence data from NCBI
library("seqinr") # Loading seqinr package

ACCESSION <- "NC_017719" # Salmonella enterica subsp. enterica serovar Typhimurium str. SL1344 plasmid pRSF1010_SL1344
#ACCESSION <- "NC_015722" # Candidatus Midichloria mitochondrii IricVA
#ACCESSION <- "AP017609" # Ramazzottius varieornatus mitochondrial DNA, complete genome, strain: YOKOZUNA-1

## nucleotide FASTA
fna <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)

## CDS nucleotide FASTA
ffn <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)

## CDS protein FASTA
faa <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_aa&retmode=text"), seqtype = c("AA"), strip.desc = TRUE)

# 配列の数をカウントする:  
# get the number of elements
length(fna)
length(ffn)
length(faa)

# 配列のアノテーションを取得する:  
# get sequence annotations
getAnnot(fna)
head(getAnnot(ffn), 2)
head(getAnnot(faa), 2)

# 配列データをFASTA形式ファイルとして書き出す:  
# Writing sequence data out as a FASTA file
write.fasta(sequences=fna, names=getAnnot(fna), file.out=paste0(ACCESSION,".fna"))
write.fasta(sequences=ffn, names=getAnnot(ffn), file.out=paste0(ACCESSION,".ffn"))
write.fasta(sequences=faa, names=getAnnot(faa), file.out=paste0(ACCESSION,".faa"))
```

- prokka [Output Files](https://github.com/tseemann/prokka/blob/master/README.md#output-files)

| Extension | Description |
| --------- | ----------- |
| .fna | Nucleotide FASTA file of the input contig sequences. |
| .ffn | Nucleotide FASTA file of all the prediction transcripts (CDS, rRNA, tRNA, tmRNA, misc_RNA) |
| .faa | Protein FASTA file of the translated CDS sequences. |

- [45. ファイルへのデータ出力](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/45.html)

関数`save()`でデータの構造を記録する。呼び出す場合は関数`load()`を用いる。
```
save(fna, ffn, faa, file="my_fna_ffn_faa.RData") # Save R Objects
ls() # List Objects
rm(faa, ffn, fna) # Remove Objects
load(file="my_fna_ffn_faa.RData") # Reload Saved Datasets
```

- [applyファミリー | R で同じ処理を”並列的”に実行する関数](https://stats.biopapyrus.jp/r/basic/apply.html)

`sapply()`関数は、リストの各要素に関数を適用する。  
タンパク質コード配列（CDS）の長さ、G+C含量、アノテーションのテーブルを作成する:  
```
# Apply a Function over a List
Length <- sapply(ffn, length)
GCcontent <- sapply(ffn, GC) # Global G+C content
GCp3 <- sapply(ffn, GC3) # G+C at 3rd codon position
Annotation <- sub(pattern=".+\\[locus_tag=(.+)\\] \\[protein=(.+)\\] (\\[(protein_id|pseudo)=(.+)) \\[location=.+", replacement="\\1 \\2 \\3", getAnnot(ffn))
df <- data.frame(Length, GCcontent, GCp3, Annotation)
```

- [CSVやTSVで出力](http://a-habakiri.hateblo.jp/entry/2016/12/12/222806)

データのエクスポート。  
`write.csv`関数でカンマ区切りファイルとして出力する:  
`write.table`関数でタブ区切りファイルとして出力する:  

    # Exporting Data
    write.csv(df, file="table.csv", quote=TRUE, row.names=TRUE)
    write.table(df, file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names=NA)

    # open current working directory
    system("open .")

- [R – データフレームの参照・変更](http://taustation.com/r-datafrrame-display-modification/)
  - [データフレームの要素の参照・変更](http://taustation.com/r-datafrrame-display-modification/#i-5)

行と列の数、列名、先頭部分の確認:  
```
# Exploring and Transforming Dataframes
dim(df)
colnames(df)
head(df, n=1)

# データフレームの要素の参照
df[, c("Length", "GCcontent", "GCp3")]
df[, 1:3]
( val <- df[, -4] )
```

- https://github.com/haruosuz/introBI/blob/master/2017/CaseStudy.md#2017-10-05

`summary()`関数でデータフレームの列を要約する。  
CDSの要約統計量（最小値、中央値、最大値など）を求める:  

    summary(val)

[53. グラフィックスパラメータ（弐）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/53.html)
フォント・ファミリーを指定する．

    par(family="mono")

[R | R を利用した統計解析およびデータの視覚化](https://stats.biopapyrus.jp/r/)

    plot(val)

[pairs.panels](https://github.com/haruosuz/r4bioinfo/blob/master/R_memo/R_plot.md#pairspanels)

```
#install.packages("psych")
library(psych)
pairs.panels(val)
```

- 2019年5月16日[【合成生物学】大腸菌の遺伝コードを圧縮する](https://www.natureasia.com/ja-jp/nature/pr-highlights/12951)
[Total synthesis of Escherichia coli with a recoded genome | Nature](https://www.nature.com/articles/s41586-019-1192-5)

```
# to plot genetic code as in textbooks
tablecode()
```

### codon usage
**コドン使用**

テスト用の配列データを作成する。  
[`count`](https://rdrr.io/rforge/seqinr/man/count.html)関数で3連続塩基`(wordsize = 3)`をカウントする。  
[`uco`](https://rdrr.io/rforge/seqinr/man/uco.html)関数でコドン使用頻度`(index = "eff", "freq", "rscu")`を計算する。
```
# Create tests
testseq <- s2c("ttcttt")

## trimer counts
count(seq = testseq, wordsize = 3)

## codon counts `eff`
uco(seq = testseq, index = "eff")

## relative frequencies `freq`
uco(seq = testseq, index = "freq")

## Relative Synonymous Codon Usage `rscu`
uco(seq = testseq, index = "rscu")
```

- [リストをベクトルに変換するunlist()関数](https://ito-hi.blog.so-net.ne.jp/2011-07-12)

`unlist()`関数は、リストの要素を端からベクトルとして結合して 1 つのベクトルとしてまとめる。
全CDSのデータを結合する(concatenate):  

    # Flatten Lists
    ffn.concat <- unlist(ffn)

全CDSの結合データのコドン使用頻度`("eff", "freq", "rscu")`を計算し、カンマ区切りファイルとして出力する:  

    # Codon usage for the collection of all genes
    df.uco <- uco(ffn.concat, as.data.frame=TRUE) # all indices are returned into a data frame

    # Export data as a CSV file to be read by spreadsheets:
    write.csv(df.uco[order(df.uco$AA),], file="table.uco.csv", quote=TRUE, row.names=FALSE)

    # open current working directory
    system("open .")

[`getTrans`](https://www.rdocumentation.org/packages/seqinr/versions/3.4-5/topics/getTrans)
関数を用いて、核酸配列をタンパク質に翻訳する:  

    # Translate nucleic acid sequences into proteins
    myTrans <- getTrans(ffn)
    myTrans[[1]]
    faa[[1]]

### amino acid usage
**[アミノ酸](https://ja.wikipedia.org/wiki/アミノ酸)使用**

平成22年度、清水謙多郎 [タンパク質の配列から機能を予測する](http://www.iu.a.u-tokyo.ac.jp/lectures/AG01/100511/motif.html)

`[[ ]]`はリスト内の要素（ベクトル）を取り出す。
リストの1番目の要素を取り出す:  

    # extract the 1st element:
    faa1 <- faa[[1]]

`summary()`関数でデータの要約:  

    # Object Summaries
    summary(faa1)

配列の長さ(length)、アミノ酸組成(composition)、物理化学的クラスの割合(AA.Property)が出力される。

![http://www.r-exercises.com/2017/05/10/accessing-and-manipulating-biological-databases-solutions-part-3/](http://www.r-exercises.com/wp-content/uploads/2017/05/Fig3-300x300.png)

[`AAstat()`](https://www.rdocumentation.org/packages/seqinr/versions/3.3-3/topics/AAstat)
関数を用いて、タンパク質の配列情報（アミノ酸残基数、物理化学的クラスの割合、[等電点](https://ja.wikipedia.org/wiki/等電点)の理論値）を求める:  

    # Get protein statistics
    AAstat(seq=faa1)

    aa <- AAstat(seq=faa1, plot=FALSE)

    # Get amino acid counts
    aa$Compo

    # Get the percentage of each physico-chemical classes
    aa$Prop
    aa$Prop$Aromatic

[`getAnnot`](https://rdrr.io/rforge/seqinr/man/getAnnot.html)
関数を用いて、配列のアノテーションを取得する:  

    # get sequence annotations
    myAnnot <- getAnnot(faa)

[文字列 | R で文字列の切り出しや置換などの文字列処理を行う方法](https://stats.biopapyrus.jp/r/basic/string.html)

[転移酵素](https://ja.wikipedia.org/wiki/転移酵素) "transferase" と、機能が不明なタンパク質 "hypothetical protein" を抽出する:  

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x).
    pattern <- "transferase|hypothetical.protein"
    TF <- grepl(pattern = pattern, x = myAnnot, ignore.case = TRUE)
    #TF <- !grepl(pattern = "hypothetical.protein", x = myAnnot, ignore.case = TRUE)
    sum(TF)
    myAnnot[TF]

[リスト](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html)の成分を取り出す:  

    # extract the elements of the list object
    faa[TF]

`sapply()`関数は、リストの各要素に関数を適用する。  
複数タンパク質配列のアミノ酸使用の絶対度数と相対度数を求める:  

    # absolute frequencies
    X <- sapply(faa[TF], function(x) AAstat(x, plot=FALSE)$Compo )
    write.csv(t(X), file="table.aa_af.csv")

    # relative frequencies
    X <- sapply(faa[TF], function(x) summary(x)$composition )
    write.csv(t(X), file="table.aa_rf.csv")

    # open current working directory
    system("open .")

[26. names 属性と要素のラベル](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/26.html)

    # Exploring and Transforming Dataframes
    dim(X)
    colnames(X) <- sub(pattern=".+protein=(.+)\\] \\[(protein_id|pseudo)=.+", replacement="\\1", getAnnot(faa[TF]))

クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)

    # Hierarchical cluster analysis
    plot(hclust(dist(t(X))), hang=-1)

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    # Draw a Heat Map
    heatmap(X, margins=c(14, 2), cexCol=0.9, scale="none", col=rev(gray.colors(12)))

----------
## assignment 7
**課題No.7 「dotplot」**

ドットプロットで2つの配列を比較
[Comparing two sequences using a dotplot](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#comparing-two-sequences-using-a-dotplot)

Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Download FASTA-format files of two protein sequences from UniProt.

    # CySp1 - Cylindrical silk protein 1 - Nephila clavata (Joro spider)
    library("seqinr")
    seq1 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q2V0S3.fasta")[[1]]
    seq2 <- read.fasta(file = "http://www.uniprot.org/uniprot/Q2V0S4.fasta")[[1]]

    length(seq1) # 757
    length(seq2) # 1259

	par(family="mono")

Q2. Create a dotplot for two sequences.

    dotPlot(seq1, seq2, wsize = 3, wstep = 3, nmatch = 3)

Q3. Create a self-similarity dot-plot; i.e. Comparing the sequence against itself.

    dotPlot(seq1, seq1, wsize = 3, wstep = 3, nmatch = 3)
    dotPlot(seq2, seq2, wsize = 3, wstep = 3, nmatch = 3)

----------
### Elongation Factor
翻訳伸長因子
[EF-Tu](https://ja.wikipedia.org/wiki/EF-Tu)
[EF-G](https://ja.wikipedia.org/wiki/EF-G)

[重複遺伝子EF-Tu/1aとEF-G/2に基づく超生物界の複合系統樹](https://www.brh.co.jp/research/formerlab/miyata/2005/post_000008.html)

----------
## assignment 11
**課題No.11 「Pairwise Sequence Alignment」**

[Exercises on Sequence Alignment](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Download FASTA-format files of two protein sequences of interest from UniProt.

    library("seqinr")
    seq1 <- read.fasta(file = "http://togows.dbcls.jp/entry/protein/NP_009193.fasta")[[1]]
    seq2 <- read.fasta(file = "http://togows.dbcls.jp/entry/protein/NP_001232899.fasta")[[1]]

    seq1string <- toupper(c2s(seq1))	# convert the sequence to a string and to uppercase
    seq2string <- toupper(c2s(seq2))	# convert the sequence to a string and to uppercase

Q2. What is the alignment score for the optimal global alignment between the two proteins, when you use the BLOSUM50 scoring matrix?
(set gapOpening = -9.5 and gapExtension = -0.5)

	library("Biostrings")		# load the Biostrings package
	data(BLOSUM50)			# load the BLOSUM50 scoring matrix
    myglobalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
	gapOpening = -9.5, gapExtension = -0.5)	# align the two sequences
	myglobalAlign

Q3. Use the writePairwiseAlignments() function to view the optimal global alignment.

    writePairwiseAlignments(myglobalAlign)

Q4. What global alignment score do you get for the two proteins, when you use the BLOSUM62 alignment matrix?

	data(BLOSUM62)			# load the BLOSUM62 scoring matrix
    myglobalAlign2 <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM62",
	gapOpening = -9.5, gapExtension = -0.5)	# align the two sequences
	myglobalAlign2

Q5. What is the alignment score for the optimal local alignment between the two proteins?

    mylocalAlign <- pairwiseAlignment(seq1string, seq2string, substitutionMatrix = "BLOSUM50",
	gapOpening = -9.5, gapExtension = -0.5, type="local")
	mylocalAlign

----------
## assignment-12
**課題No.12 「draft report」**

Integrate and edit your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it in PDF format.

これまでの課題（興味あるDNA/タンパク質の配列解析の結果）を統合・編集してレポートのドラフトを作成し、PDFファイルで提出する。

----------
## assignment-13
**課題No.13 「presentation slides」**

https://github.com/haruosuz/DS4GD/tree/master/2018giga#final-presentation

2019-07-16 最終発表のスライド <YOUR_NAME.pdf> を提出する。
発表時間：1人あたり最大5分

生物学的データ（ゲノムDNA配列やタンパク質配列）の解析結果を報告する。解析の例として、DNA配列の統計（長さ、GC含量、連続塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル/ローカル・アラインメント）、Pythonによる配列解析などが含まれる。

Submit your PDF presentation slides for your final presentation 最終発表 Tuesday 2019-07-16.
Five minutes will be allocated for each presentation, including presentation and discussion.

Report your main findings on analyses of biological data (e.g. genome DNA sequences and protein sequences) you're interested in. The analyses can include DNA sequence statistics (length, GC Content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global/local alignment), sequence analysis with Python, etc.

----------
