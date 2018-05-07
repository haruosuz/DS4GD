**[生命情報解析 / 生命動態のデータサイエンス [DS2]](https://github.com/haruosuz/DS4GD/tree/master/2018)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

Table of Contents
- [NCBI sequence database](#ncbi-sequence-database)
- [assignment 3](#assignment-3) 課題No.3
- [assignment 2](#assignment-2) 課題No.2
- [assignment 1](#assignment-1) 課題No.1
- [ASSIGNMENT](#assignment) 選抜課題

----------
## NCBI sequence database

### Genome List
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
    write.fasta(sequences=seq1, names=getAnnot(seq1), file.out=paste0(ACCESSION,".fna"))

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
    write.fasta(sequences=seqs, names=seqnames, file.out="sequence.fasta")

----------
## assignment 3
**課題No.3 「DNA Sequence Statistics (1)」**    

[Exercises on DNA Sequence Statistics (1)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html#exercises)

SeqinRパッケージを用いて、配列データをRに読み込む:  

	# read the sequence into R using the SeqinR package:
    library("seqinr")
    ACCESSION <- "NC_001477" # Dengue virus 1
    #ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
    seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"))
    seq1 <- seqs[[1]]

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

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
## assignment 1
**課題No.1 「R言語入門」**    
〆切：2018-04-16 23:59:00

次の動画レッスンを見て、疑問点を報告する。[R言語入門 (全13回) - プログラミングならドットインストール](http://dotinstall.com/lessons/basic_r)【回答例】動画レッスン番号 #03 ~ #13 を見た。疑問点は次の通りである。
- 因子ベクトルというものがよくわからなかった。
- 行列とデータフレームとリストの違いが理解できなかった。

----------
## ASSIGNMENT
選抜課題

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
