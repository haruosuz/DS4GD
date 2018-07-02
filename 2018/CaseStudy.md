**[生命情報解析 / 生命動態のデータサイエンス [DS2]](https://github.com/haruosuz/DS4GD/tree/master/2018)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「R言語入門」
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages seqinr & Biostrings」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [NCBI ASSEMBLY_REPORTS](#ncbi-assembly_reports)
- [NCBI GENOME_REPORTS](#ncbi-genome_reports)
- [assignment 6](#assignment-6) 課題No.6 「dotplot」
- [assignment 7](#assignment-7) 課題No.7 「Pairwise Sequence Alignment」
- [2018-06-19](#2018-06-19) network
- [assignment 10](#assignment-10) 課題No.10 「Multiple Alignment and Phylogenetic Trees」
- [codon usage](#codon-usage) コドン使用

----------
## Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

年月日を確認:  

    # Get Current Date and Time
    Sys.Date()

----------
## assignment 0
**選抜課題**

【課題内容】
本授業で解析したいDNAまたはタンパク質の配列を300文字以内で述べてください。課題のタイトルと参考文献も明記してください。

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
**課題No.1 「R言語入門」**    

次の動画レッスンを見て、疑問点を報告する。[R言語入門 (全13回) - プログラミングならドットインストール](http://dotinstall.com/lessons/basic_r)【回答例】動画レッスン番号 #03 ~ #13 を見た。疑問点は次の通りである。
- 因子ベクトルというものがよくわからなかった。
- 行列とデータフレームとリストの違いが理解できなかった。

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
## NCBI sequence database
## NCBI Genome List
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)のゲノム配列決定プロジェクト一覧
- FTPサイト ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/
- ゲノムブラウザ http://www.ncbi.nlm.nih.gov/genome/browse/

ゲノムブラウザ上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、"Search"ボタンを押す。
例えば、[ライム病](https://ja.wikipedia.org/wiki/ライム病)の病原体である[*Borrelia burgdorferi*](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Borrelia%20burgdorferi)を検索し、"Prokaryotes"をクリックすると、[*Borrelia burgdorferi* Strain](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Borrelia%20burgdorferi)一覧が表示されるので、列**Organism Name**の[Borrelia burgdorferi B31](https://www.ncbi.nlm.nih.gov/genome/738?genome_assembly_id=168382)をクリックして開く。
**Replicon Info**下の表の列**RefSeq**と列**INSDC**に識別子 (Accession) が示されている。
列**Type**のChrは染色体、Plsmはプラスミドを指す。

### Working with Data in R

[R の起動と終了](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html)  

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

NCBIからDNA配列を取得する:  

    # Retrieving a DNA sequence from NCBI
    library("seqinr")
    ACCESSION <- "NC_001318" # Borrelia burgdorferi B31 chromosome, complete genome
    seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)
    seq1 <- seqs[[1]]
    write.fasta(sequences=seq1, names=getAnnot(seq1), file.out=paste0(ACCESSION,".fasta"))

NCBIから複数のDNA配列を取得する:  

    # Retrieving a list of DNA sequences from NCBI
    library("seqinr")

    # create a function to retrieve several nucleotide sequences from NCBI
    retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)[[1]]

	# Make a vector containing the names of the sequences
    seqnames <- c("NC_001318", "NC_001856") # Borrelia burgdorferi B31 chromosome (NC_001318) plasmid lp38 (NC_001856)

	# Retrieve the sequences and store them in list variable "seqs"
    seqs <- lapply(seqnames,  retrieve_ncbi_fna)

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs, names=seqnames, file.out="mySequences.fasta")

----------
## assignment 3
**課題No.3 「DNA Sequence Statistics (1)」**    

[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

NCBIからDNA配列を取得する:  

    # Retrieving a DNA sequence from NCBI
    library("seqinr")
    ACCESSION <- "NC_001477" # Dengue virus 1
    #ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
    seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"))
    seq1 <- seqs[[1]]

Q1. What are the last twenty nucleotides of the genome sequence?

    seq1[(length(seq1)-20+1):length(seq1)]

Q2. What is the length in nucleotides of the genome sequence?

    length(seq1)

Q3. How many of each of the four nucleotides A, C, T and G, and any other symbols, are there in the genome sequence?

    table(seq1)

Q4. What is the GC content of the genome sequence, when (i) all non-A/C/T/G nucleotides are included, (ii) non-A/C/T/G nucleotides are discarded?

	help("GC")
    GC(seq1)
    GC(seq1, exact=FALSE)

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

http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises 

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

Q1. Draw a sliding window plot of GC content in the genome, using a window size of 200 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# write a function to make a sliding window plot:
    slidingwindowplotGC <- function(windowsize, inputseq)
    {
      require("zoo") # this function requires the 'zoo' R package # install.packages('zoo')
      x <- seq(from = 1, to = length(inputseq)-windowsize, by = windowsize)
      y <- rollapply(data = inputseq, width = windowsize, by = windowsize, FUN = GC)
      plot(x, y, type="b", xlab="Position (bp)", ylab="GC content")
    }

	# make a sliding window plot with a window size of 200 nucleotides:
    slidingwindowplotGC(200, seq1)

	# make a sliding window plot of GC content using a window size of 2000 nucleotides:
    slidingwindowplotGC(2000, seq1)

Q2. Draw a sliding window plot of GC content in the genome sequence using a window size of 20000 nucleotides. Do you see any regions of unusual DNA content in the genome (eg. a high peak or low trough)?

	# make a sliding window plot with a window size of 20000 nucleotides:
    slidingwindowplotGC(20000, seq1)

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

## NCBI assembly summary
## NCBI ASSEMBLY_REPORTS
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)のゲノム配列のメタデータが記載されている。

ftp://ftp.ncbi.nlm.nih.gov/genomes/README_assembly_summary.txt

	The assembly_summary files report metadata for the genome assemblies on the NCBI genomes FTP site.
	assembly_summary_genbank.txt            - current GenBank genome assemblies
	assembly_summary_refseq.txt             - current RefSeq genome assemblies

- [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
- [RefSeq | 重複のない生物の遺伝子データベース（ゲノムデータベース）](http://bi.biopapyrus.net/biodb/refseq.html)
- 井上 潤 [RefSeq - JI](http://www.geocities.jp/ancientfishtree/RefSeq.html)

NCBIウェブサイト (https://www.ncbi.nlm.nih.gov) にアクセスし、右下のリンク"NCBI FTP Site"をクリックして開く。  
<ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> をブラウザ（Firefox または Chrome）で開く。  
*assembly_summary_genbank.txt*, *assembly_summary_refseq.txt*を右クリックし、「リンクのURLをコピー (Copy Link)」する。

Go to the NCBI website (https://www.ncbi.nlm.nih.gov), and then click the link "NCBI FTP Site".   
Open the URL <ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/> with your browser (Firefox or Chrome).  
Right click the link *assembly_summary_genbank.txt*, *assembly_summary_refseq.txt*, and select "Copy Link Address".

### Working with Data in R

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/ncbi/assembly_reports"

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
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt"
    download.file(url = curl, destfile = basename(curl))

[Ｒ言語のデータの入出力と編集](https://www1.doshisha.ac.jp/~mjin/R/02.html)

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    d <- read.delim(file = basename(curl), stringsAsFactors = FALSE, check.names = FALSE, skip = 1) 

[データフレーム](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html)の行と列の数、先頭部分、列名の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    head(d, n = 1)
    colnames(d)
    colnames(d)[1] <- "assembly_accession"

    table(d$refseq_category)
    table(d$assembly_level)

[大腸菌](https://www.sbj.or.jp/wp-content/uploads/file/sbj/9010/9010_yomoyama-1.pdf)
[Escherichia coli K-12](https://en.wikipedia.org/wiki/Escherichia_coli_in_molecular_biology#K-12)
の完全ゲノム("Complete Genome")配列データの最新版("latest")のURLを抽出する:  

List the ftp_path (column 20) for the assemblies of interest, in this case those that have organism_name of "Escherichia coli K-12" (column 8), "latest" version_status (column 11) and "Complete Genome" assembly_level (column 12)

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x).
    pattern <- "Escherichia coli.*K-12"
    #pattern <- "Borrelia burgdorferi"
    #pattern <- "Sinorhizobium meliloti"
    #pattern <- "Escherichia.coli"
    TF <- grepl(pattern = pattern, x = d$organism_name) & grepl(pattern = "reference|representative", x = d$refseq_category) & d$assembly_level == "Complete Genome" & d$version_status == "latest"
    d[TF,]
    d$ftp_path[TF]

抽出されたURLをブラウザFirefox/Chromeで開く。*.gz*ファイルを右クリックし、「リンクのURLをコピー (Copy Link)」する。

Open the URL with your browser (Firefox or Chrome). Right click the link *.gz*, and select "Copy Link Address".

ftp://ftp.ncbi.nlm.nih.gov/genomes/all/README.txt

[What is the file content within each specific assembly directory?](https://www.ncbi.nlm.nih.gov/genome/doc/ftpfaq/#files)

    *_genomic.fna.gz: FASTA format of the genomic sequence(s) in the assembly. 
    *_cds_from_genomic.fna.gz: FASTA format of the nucleotide sequences corresponding to all CDS features annotated on the assembly, based on the genome sequence.
    *_protein.faa.gz: FASTA format of the accessioned protein products annotated on the genome assembly.
    *_genomic.gbff.gz: GenBank flat file format of the genomic sequence(s) in the assembly. 

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    curl <- paste0(d$ftp_path[TF], "/", unlist(strsplit(d$ftp_path[TF], split="/"))[10], "_genomic.fna.gz" )
    #curl <- paste0(d$ftp_path[TF], "/", unlist(strsplit(d$ftp_path[TF], split="/"))[10], "_cds_from_genomic.fna.gz" )
    download.file(url = curl, destfile = basename(curl))

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data
    library("seqinr") # Load the SeqinR package
    basename(curl)
    seqs <- read.fasta(file = basename(curl), seqtype = c("DNA"), strip.desc = TRUE)
    #seqs <- read.fasta(file = gzcon(url(curl)), seqtype = c("DNA"), strip.desc = TRUE) # Retrieve the sequences and store them in list variable "seqs"
  
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

複数のDNA配列の2連続塩基組成（観測値/期待値）を解析する:  

    # Apply a Function over a List
    X <- sapply(seqs, rho)

    # Hierarchical Clustering
    plot(hclust(dist(t(X))))

- [Wong K et al. (2002) "Dinucleotide compositional analysis of Sinorhizobium meliloti using the genome signature: distinguishing chromosomes and plasmids."](https://www.ncbi.nlm.nih.gov/pubmed/12444420)

----------
## NCBI GENOME_REPORTS

<ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/> をブラウザ（Firefox または Chrome）で開く。 
*README*をクリックして開く。

	prokaryotes.txt: Prokaryotic genome sequencing projects

	prok_reference_genomes.txt: List of reference genome: small curated subset of 
	                             really good and scientifically important prokaryotic genomes

	prok_representative_genomes.txt:  List of all selected representative prokaryotic genomes

### Working with Data in R

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/ncbi/genome_reports"

    # Invoke a System Command
    system( paste0("mkdir -p ",WorkingDirectory) )

    # Set and Get Working Directory
    setwd(WorkingDirectory)
    getwd()

    # List the Files in a Directory
    dir()

[インターネットからファイルをダウンロードする](http://webbeginner.hatenablog.com/entry/2015/02/06/212921)

    # Download File from the Internet
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_reference_genomes.txt"
    #curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_representative_genomes.txt"
    download.file(url = curl, destfile = basename(curl))

[Ｒ言語のデータの入出力と編集](https://www1.doshisha.ac.jp/~mjin/R/02.html)

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    # Loading Data into R
    d <- read.delim(file = basename(curl), stringsAsFactors = FALSE, check.names = FALSE)

[データフレーム](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html)の行と列の数、先頭部分、列名の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    head(d, n = 1)
    colnames(d)
    colnames(d)[1] <- "species_genus"

[文字列の処理](http://stat.biopapyrus.net/r/string.html)  

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    pattern <- "Escherichia coli.*K-12|Haemophilus influenzae|Borrelia burgdorferi"
    i <- grep(pattern = pattern, x = d$`Organism name`, ignore.case = TRUE)
    length(i)
    d[i,1]
    d$`Chromosome RefSeq`[i]

NCBIから複数のDNA配列を取得する:  

    # Retrieving a list of DNA sequences from NCBI
    library("seqinr")

    # create a function to retrieve several nucleotide sequences from NCBI
    retrieve_ncbi_fna <- function(ACCESSION) read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)[[1]]

    ACCESSIONs <- d$`Chromosome RefSeq`[i] # Make a vector containing RefSeq accessions of Chromosome sequences
    seqs <- lapply(ACCESSIONs,  retrieve_ncbi_fna) # Retrieve the sequences and store them in list variable "seqs"

配列データをFASTA形式ファイルとして書き出す:  

	# write the sequences to a FASTA-format file
    write.fasta(sequences=seqs, names=getAnnot(seqs), file.out="mySequences.fna", nbchar = 80)

作業を中断し再開する（Rを終了し再起動する）。作業ディレクトリを変更し、パッケージ`seqinr`を呼び出し、`read.fasta()`関数で配列データを読み込む:  

    setwd("~/projects/ncbi/genome_reports")						# Set Working Directory
    library(seqinr)									# Load the SeqinR package
    seqs <- read.fasta(file = "mySequences.fna", seqtype = c("DNA"), strip.desc = TRUE)	# Reading sequence data
    unlist(getAnnot(seqs))								# get sequence annotations

配列の数をカウントする:  

    # get the number of elements
    length(seqs)

リスト`seqs`の1番目の要素を変数`seq1`に代入する:  

    # store the first element of the list object `seqs` in a variable `seq1`
    seq1 <- seqs[[1]]

#### [DNA Sequence Statistics (1)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-1)

DNA配列の長さ:  

    # Length of a DNA sequence
    length(seq1)

DNA配列の塩基組成:  

    # Base composition of a DNA sequence
    table(seq1)

- DDBJ [配列の記載に用いる略号](http://www.ddbj.nig.ac.jp/sub/code-j.html)

DNA配列のGC含量:  

    # GC Content of DNA
    GC(seq1)

`summary()`関数でデータの要約:  

    # Object Summaries
    summary(seq1)

DNA配列の長さ、塩基組成、GC含量 (length, composition, GC) が出力される。

DNA配列の2連続塩基含量:  

    # DNA words
    count(seq1, 2)

#### [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)

Sliding windowでゲノムの局所的な塩基組成（GC content, GC skew）を解析する:  

	# Local variation in GC content
	# A sliding window analysis of GC content
	# A sliding window plot of GC content
    library(zoo)
    pdf(file="Rplot.pdf") # create a PDF device called "Rplot.pdf"
    par(mfcol=c(1,1), cex=1.5, mai = c(1.2, 1.2, 0.1, 0.1)) # c(bottom, left, top, right)

    # x-axis: Position
    windowsize <- 10000
    x <- seq(from = 1, to = length(seq1)-windowsize, by = windowsize) / 10^6
    xlab <- "Position (Mbp)"

    # y-axis: GC content
    y <- rollapply(data = seq1, width = windowsize, by = windowsize, FUN = GC)
    plot(x, y, type="l", xlab=xlab, ylab="GC content")

    # y-axis: GC skew
    GCskew <- function(x){ y <- table(x); (y["c"] - y["g"]) / (y["c"] + y["g"]) }
    y <- rollapply(data = seq1, width = windowsize, by = windowsize, FUN = GCskew)
    plot(x, y, type="l", xlab=xlab, ylab="GC skew"); abline(h = 0)

    # y-axis: Cumulative GC skew
    plot(x, cumsum(y), type="l", xlab=xlab, ylab="Cumulative GC skew")

    dev.off() # close the device

    # open current working directory
    system("open .")

- [Hiromi Nishida "ゲノム比較解析"](https://sites.google.com/site/microbioinformatics/genomu-bi-jiao-jie-xi)
- [小池、木ノ内 (2010) "バクテリアの塩基配列における文字の含量を用いた解析"](http://www.topic.ad.jp/ipsj-tohoku/archive/2010/report/report14/10-6-A5-1.pdf)
- [Dutta C, Paul S. (2012) Microbial lifestyle and genome signatures.](https://www.ncbi.nlm.nih.gov/pubmed/23024607)
- [Karlin S (2001) Trends Microbiol. "Detecting anomalous gene clusters and pathogenicity islands in diverse bacterial genomes."](https://www.ncbi.nlm.nih.gov/pubmed/11435108) | [pdf](https://eclass.uoa.gr/modules/document/file.php/D473/Βιβλιογραφία/DNA%20Composition/Karlin_2001.pdf)
- [Arakawa K, Tomita M. (2007)](https://www.ncbi.nlm.nih.gov/pubmed/19461976/) | ["バクテリアゲノムの複製による選択度合いを定量化"](http://www.iab.keio.ac.jp/research/highlight/papers/200904130118.html)

![](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2684130/bin/EBO-03-159-g002.jpg)

DNA配列の2連続塩基組成（観測値/期待値）:  

    # Over-represented and under-represented DNA words
    rho(seq1, wordsize = 2)
    
    par(cex=0.7)
    barplot(sort(rho(seq1, wordsize = 2)))
    abline(h=1)

`sapply()`関数は、リストの各要素に関数を適用する。
複数のDNA配列を解析する:  

    # Apply a Function over a List
    X <- sapply(seqs, rho)

[26. names 属性と要素のラベル](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/26.html)

    # Exploring and Transforming Dataframes
    dim(X)
    colnames(X)
    colnames(X) <- getAnnot(seqs)
    colnames(X) <- substr(unlist(getAnnot(seqs)), 1, 15)
    colnames(X) <- sapply(unlist(getAnnot(seqs)), function(x) paste0(unlist(strsplit(x, split=" "))[2:3], collapse=" ") )

[45. ファイルへのデータ出力](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/45.html)

    write.csv(t(X), file="table.csv", quote=TRUE, row.names=TRUE)
    write.table(t(X), file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names = NA)

`matplot()`関数でプロットする:  

    matplot(X, type="l", col=1:ncol(X), lty=1:ncol(X))
    legend("topleft", legend=colnames(X), col=1:ncol(X), lty=1:ncol(X))

クラスター分析 [Cluster Analysis](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#cluster-analysis)

    # Hierarchical Clustering
    plot(hclust(dist(t(X))))

ヒートマップ [Heat Map](https://github.com/haruosuz/DS4GD/blob/master/2017/hclust.md#heat-map)

    # Draw a Heat Map
    heatmap(X, margins=c(10,5), cexCol=1.0)

- [Campbell A et al. (1999) "Genome signature comparisons among prokaryote, plasmid, and mitochondrial DNA."](https://www.ncbi.nlm.nih.gov/pubmed/10430917)

![](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC17754/bin/pq1692140001.jpg)

- [塩基組成に基づいたプラスミドの宿主域の予測](http://www.sigmbi.jp/?m=201601)

----------

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
## assignment 6
**課題No.6 「dotplot」**

https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#comparing-two-sequences-using-a-dotplot

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

![http://techacademy.jp/magazine/5155](http://static.techacademy.jp/magazine/wp-content/uploads/2015/01/ss-1-620x375.jpg)

[ターミナル](http://techacademy.jp/magazine/5155)を開き、`bash`を起動する:  

    # change shell to bash
    bash

[(Rで)塩基配列解析](http://www.iu.a.u-tokyo.ac.jp/~kadota/r_seq.html)
「2-1. 配列解析基礎」坊農秀雅 (DBCLS)
[講義資料](http://www.iu.a.u-tokyo.ac.jp/~kadota/bioinfo_ngs_sokushu_2014/20140905_2-1_bono.pdf)

	# 配列取得方法
	## togowsの利用 http://togotv.dbcls.jp/20110425.html
    curl -L "http://togows.dbcls.jp/entry/protein/NP_009193.fasta" > HsDJ1.pep.fa
    curl -L "http://togows.dbcls.jp/entry/protein/NP_001232899.fasta" > BmDJ1.pep.fa

	# dottup
	dottup -asequence HsDJ1.pep.fa -bsequence BmDJ1.pep.fa -wordsize 4

	# needle, water
	needle HsDJ1.pep.fa BmDJ1.pep.fa	water HsDJ1.pep.fa BmDJ1.pep.fa

----------
## assignment 7
**課題No.7 「Pairwise Sequence Alignment」**

http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter4.html#exercises

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
## 2018-06-19

- 講師: 山中 遼太 氏 [Dr. Ryota Yamanaka](http://www.genome.rcast.u-tokyo.ac.jp/872) (Oracle)
- 演題: [ネットワーク分析とグラフデータベース／データ分析プラットフォーム](https://dl.dropboxusercontent.com/s/u20ej6bq7c7uwzr/Yamanaka_20180619_01.pptx)

Rコード

	# igraph のセットアップ
	#install.packages("igraph")
	library(igraph)
	
	# グラフの読み込み
	edge <- c(1,2, 1,4, 2,3, 2,3, 2,4, 3,1, 4,4)
	g <- graph(edge)
	V(g)
	E(g)
	plot(g)

	# グラフのロード
	## グラフをロードします
	a <- as.matrix(read.csv("https://dl.dropboxusercontent.com/s/yfcqpobisdpz7th/hero-network.csv", h=FALSE))
	g <- graph.edgelist(a, directed=FALSE)

	## キャラクター（ノード）の数を表示します
	print(V(g))
	## 一緒に登場するキャラクターの組（エッジ）の数を表示します
	print(E(g))
	
	##ロードしたグラフに前処理を施します
	g <- simplify(g, remove.multiple=T, remove.loops=T)

	## 再度、エッジの数を表示します
	print(E(g))

	# 重要なヒーローの特定
	## まず、各ノードの次数中心性を求めます
	d <- degree(g)
	## 計算結果を参照します
	head(sort(d, decreasing=T), 10)
	
	## 次に、各ノードのページランクを求めます
	p <- page.rank(g)
	## 計算結果を参照します
	head(sort(p$vector, decreasing=T), 10)

	## 同様に、各ノードの媒介中心性も求めてみます
	b <- betweenness(g)
	## 計算結果を参照します
	head(sort(b, decreasing=T), 10)

	# コミュニティの抽出
	## 各ノードの連結成分を求めてみます
	c <- clusters(g)
	## 各クラスターのサイズを確認します
	print(c$csize)

	## マイナーなクラスタのメンバーを確認します。
	groups(c)[2:4]
	
	## グラフ中のコミュニティを貪欲法を使って抽出します。	## これは計算コストの低いコミュニティ抽出のアルゴリズムです。
	c <- fastgreedy.community(g)
	## 抽出されたコミュニティの数を出力します
	print(c)

	# スケールフリー・ネットワーク
	## まず、ノードが 10個のとき、30個のときのネットワークをそれぞれ描画してみます。
	g <- barabasi.game(10, m=2, directed=FALSE)
	plot(g)
	
	g <- barabasi.game(30, m=2, directed=FALSE)
	plot(g)

	## ノードが 10,000個になると描画してもよくわからないので、	## 次数（つながっているノードの数）ごとにどれくらいの割合のノードが	## 分布しているか（次数分布）をグラフにしてみます。
	g <- barabasi.game(10000, m=2, directed=FALSE)
	dd <- degree.distribution(g)
	plot(dd[-1], log="x", xlab="degree", ylab="proportion")

	## さらに、ノード間の平均距離を調べてみます。
	average.path.length(g)

- [Pellegrini M et al. (1999) "Assigning protein functions by comparative genome analysis: protein phylogenetic profiles."](https://www.ncbi.nlm.nih.gov/pubmed/10200254)

----------
## assignment 10
**課題No.10 「Multiple Alignment and Phylogenetic Trees」**

http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter5.html#exercises

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Calculate the genetic distances between four protein sequences of interest. Which are the most closely related proteins, and which are the least closely related, based on the genetic distances?

    library("seqinr")
    # create a function to retrieve several sequences from UniProt
    retrieve_seqs_uniprot <- function(ACCESSION) read.fasta(file = paste0("http://www.uniprot.org/uniprot/",ACCESSION,".fasta"), seqtype = c("AA"), strip.desc = TRUE)[[1]]

    seqnames <- c("Q9YRR4", "Q9YP96", "B0LSS3", "Q6TFL5") # Make a vector containing the names of the sequences
    seqs <- lapply(seqnames,  retrieve_seqs_uniprot) # Retrieve the sequences and store them in list variable "seqs"

    # write out the sequences to a FASTA file
    write.fasta(seqs, seqnames, file="myseq.fasta")

    # Read an XStringSet object from a file
    library(Biostrings)
    mySequences <- readAAStringSet(file = "myseq.fasta")

    # Multiple Sequence Alignment using ClustalW
    library(msa)
    myAlignment <- msa(mySequences, "ClustalW")

    # write an XStringSet object to a file
    writeXStringSet(unmasked(myAlignment), file = "myaln.fasta")

    # read the FASTA-format alignment into R, and calculate the genetic distances between the protein sequences:
    myaln <- read.alignment(file = "myaln.fasta", format = "fasta")
    mydist <- dist.alignment(myaln)
    mydist

Q2. Build an unrooted phylogenetic tree of the four proteins, using the neighbour-joining algorithm. Which are the most closely related proteins, based on the tree?

    par(family="mono")

    library(ape)
    mytree <- nj(mydist)
    plot.phylo(mytree, type="unrooted")

Q3. Build an unrooted phylogenetic tree of the four proteins, based on a trimmed alignment of the four proteins. Does this differ from the tree based on the untrimmed alignment (in Q2)? Can you explain why?

    # Trimming a multiple sequence alignment by discarding columns with too many gaps.
    library(microseq)
    msa <- readFasta(in.file = "myaln.fasta")
    print(nchar(msa$Sequence))
    msa.trimmed <- msaTrim(msa = msa, gap.end = 0.3, gap.mid = 0.3)
    print(nchar(msa.trimmed$Sequence))
    writeFasta(fdta = msa.trimmed, out.file = "msa.trimmed.fasta", width = 80)

    # read the FASTA-format alignment into R, and calculate the genetic distances between the protein sequences:
    myaln <- read.alignment(file = "msa.trimmed.fasta", format = "fasta")
    mydist <- dist.alignment(myaln)
    mydist

    # construct a phylogenetic tree
    mytree <- nj(mydist)
    plot.phylo(mytree, type="unrooted")

Q4. Build a rooted phylogenetic tree of the four proteins based on a trimmed alignment, using an outgroup. Which are the most closely related proteins, based on the tree? What extra information does this tree tell you, compared to the unrooted tree in Q2?

    retrieve_seqs_uniprot <- function(ACCESSION) read.fasta(file = paste0("http://www.uniprot.org/uniprot/",ACCESSION,".fasta"), seqtype = c("AA"), strip.desc = TRUE)[[1]]
    seqnames <- c("Q9YRR4", "Q9YP96", "B0LSS3", "Q6TFL5", "Q32ZE1") # Make a vector containing the names of the sequences
    seqs <- lapply(seqnames,  retrieve_seqs_uniprot) # Retrieve the sequences and store them in list variable "seqs"

    # write out the sequences to a FASTA file
    write.fasta(seqs, seqnames, file="myseq.fasta")

    # Read an XStringSet object from a file
    library(Biostrings)
    mySequences <- readAAStringSet(file = "myseq.fasta")

    # Multiple Sequence Alignment using ClustalW
    library(msa)
    myAlignment <- msa(mySequences, "ClustalW")

    # write an XStringSet object to a file
    writeXStringSet(unmasked(myAlignment), file = "myaln.fasta")

    # Trimming a multiple sequence alignment by discarding columns with too many gaps.
    library(microseq)
    msa <- readFasta(in.file = "myaln.fasta")
    print(nchar(msa$Sequence))
    msa.trimmed <- msaTrim(msa = msa, gap.end = 0.5, gap.mid = 0.9)
    print(nchar(msa.trimmed$Sequence))
    writeFasta(fdta = msa.trimmed, out.file = "msa.trimmed.fasta", width = 80)

    # read the FASTA-format alignment into R, and calculate the genetic distances between the protein sequences:
    myaln <- read.alignment(file = "msa.trimmed.fasta", format = "fasta")
    mydist <- dist.alignment(myaln)
    mydist

    # construct a phylogenetic tree
    mytree <- nj(mydist)
    mytree <- root(mytree, outgroup = "Q32ZE1", resolve.root = TRUE)
    plot.phylo(mytree, main = "Phylogenetic Tree")

----------
## codon usage
**コドン使用**

- [コドン表 [BioWiki]](https://biowiki.edu-wiki.org/コドン表)
- [遺伝暗号(コドン）使用の種による多様性](https://www.nig.ac.jp/museum/evolution/04.html)
- [PHX/PA user guide](http://www.cmbl.uga.edu/software/ASeqH.htm)
- [Karlin S, Mrázek J, Campbell A, Kaiser D. (2001) "Characterizations of highly expressed genes of four fast-growing bacteria."](https://www.ncbi.nlm.nih.gov/pubmed/11489855)
- [Henry I, Sharp PM. (2007) "Predicting gene expression level from codon usage bias."](https://www.ncbi.nlm.nih.gov/pubmed/17038449)

https://cran.r-project.org/web/packages/seqinr/seqinr.pdf

    # Load the SeqinR package
    library(seqinr)

uco Codon usage indices
    ## Show all possible codons:    words()
    ## Make a coding sequence from this:    (cds <- s2c(paste(words(), collapse = "")))
    ## Get codon counts:    uco(cds, index = "eff")
    ## Get codon relative frequencies:    uco(cds, index = "freq")
    ## Get RSCU values:    uco(cds, index = "rscu")
    ## Show what happens with ambiguous bases:    uco(s2c("aaannnttt"))
    ## Use a real coding sequence:

[NCBI ASSEMBLY_REPORTS](#ncbi-assembly_reports)

    # Retrieving sequence data
    ftp_path <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/005/845/GCF_000005845.2_ASM584v2"
    curl <- paste0(ftp_path, "/", unlist(strsplit(ftp_path, split="/"))[10], "_cds_from_genomic.fna.gz" )
    seqs <- read.fasta(file = gzcon(url(curl)), seqtype = c("DNA"), strip.desc = TRUE) # Retrieve the sequences and store them in list variable "seqs"
    length(seqs) # Print out the number of sequences retrieved

`unlist()`関数は、リストの要素を端からベクトルとして結合して 1 つのベクトルとしてまとめる。
複数のDNA配列の結合データを解析する:  

    # Flatten Lists
    GC1(unlist(seqs)) # G+C in the 1st position of the codon bases
    GC2(unlist(seqs)) # G+C in the 2nd position of the codon bases
    GC3(unlist(seqs)) # G+C in the 3rd position of the codon bases

uco Codon usage indices

    seq1 <- seqs[[1]]    uco(seq1, index = "eff")  # Absolute frequencies
    uco(seq1, index = "freq") # Relative frequencies    uco(seq1, index = "rscu") # Relative Synonymous Codon Usage    df <- uco(seq1, as.data.frame = TRUE) # all indices are returned into a data frame

Relative Synonymous Codon Usage (RSCU)

    # RSCU for the collection of all genes
    cu.all <- uco(unlist(seqs), index="rscu")

Highly expressed genes encoding ribosomal proteins

    # get sequence annotations
    myAnnotation <- getAnnot(seqs)

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x).
    TF <- grepl(pattern = "ribosomal protein", x = myAnnotation, ignore.case = TRUE) 
    #TF <- grepl(pattern = "ribosomal", x = myAnnotation, ignore.case = TRUE) & !grepl(pattern = "transferase|hydroxylase|modification", x = myAnnotation, ignore.case = TRUE)
    sum(TF)

    # RSCU for the collection of ribosomal protein genes
    cu.rp <- uco(unlist(seqs[TF]), index="rscu")

Individual genes (>100 codons in length)

    # >300 bp
    seqs <- seqs[sapply(seqs, length) > 300]

    # RSCU for individual genes    cu.seqs <- t(sapply(seqs, uco, index="rscu"))

Codon usage difference between genes

    # Distances between a single genes and the collection of all genes (average gene)
    D_all <- dist(rbind(cu.all, cu.seqs))[1:nrow(cu.seqs)]

    # Distances between a single genes and the collection of ribosomal protein genes (highly expressed genes)
    D_rp <- dist(rbind(cu.rp, cu.seqs))[1:nrow(cu.seqs)]

    # Plot
    plot(D_rp, D_all, type="n")
    points(D_rp[!TF], D_all[!TF], pch="+", col=1)
    points(D_rp[TF], D_all[TF], pch=19, col=2)
    abline(0,1)

    # Predicted gene expression levels
    E_g <- D_all / D_rp

    # Predicted highly expressed (PHX) 
    PHX <- E_g > 1.05

    # Put indicies in a dataframe
    len <- sapply(seqs, length)
    Description <- sub(pattern="(.+)gene=(.+)](.+)locus_tag=([^]]+)](.+)protein=([^]]+)](.+)", replacement="\\4;\\2;\\6", x=myAnnotation)
    d.f <- data.frame(len, D_rp, D_all, E_g, PHX, Description)
    d.f <- d.f[order(d.f$E_g, decreasing=TRUE),]

[45. ファイルへのデータ出力](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/45.html)

    write.csv(d.f, file="table.csv", quote=TRUE, row.names=TRUE)
    write.table(d.f, file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names = NA)

----------


