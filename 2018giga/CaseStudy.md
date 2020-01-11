
**[生命情報解析 / 生命動態のデータサイエンス [DS2]](https://github.com/haruosuz/DS4GD/tree/master/2018giga)**  
https://vu.sfc.keio.ac.jp/sfc-sfs/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [2018-10-18](#2018-10-18) GIGA
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題No.1 「Introduction to R」
- [assignment 2](#assignment-2) 課題No.2 「Installing R packages seqinr & Biostrings」
- [NCBI](#ncbi)
- [Codon usage](#codon-usage) コドン使用
- [assignment 3](#assignment-3) 課題No.3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題No.4 「DNA Sequence Statistics (2)」
- [NCBI ASSEMBLY_REPORTS](#ncbi-assembly_reports)
- [NCBI GENOME_REPORTS](#ncbi-genome_reports)
- [assignment 6](#assignment-6) 課題No.6 「dotplot」
- [assignment 7](#assignment-7) 課題No.7 「Pairwise Sequence Alignment」
- [assignment 8](#assignment-8) 課題No.8 「Multiple Alignment and Phylogenetic Trees」
- [assignment 9](#assignment-9) 課題No.9 「draft report」
- [assignment 10](#assignment-10) 課題No.10 「presentation slides」
- [Sequence similarity search](#sequence-similarity-search) 配列類似性検索
- [UniProtKB Swiss-Prot protein sequence database](#uniprotkb-swiss-prot-protein-sequence-database) タンパク質配列データベース

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
## NCBI
[国立生物工学情報センター](https://ja.wikipedia.org/wiki/国立生物工学情報センター)

[ゲノムブラウザ](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、"Search"ボタンを押す。
例えば、[ライム病](https://ja.wikipedia.org/wiki/ライム病)の病原体である[*Borrelia burgdorferi*](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/Borrelia%20burgdorferi)を検索し、"Prokaryotes"をクリックすると、[*Borrelia burgdorferi* Strain](https://www.ncbi.nlm.nih.gov/genome/browse/#!/prokaryotes/Borrelia%20burgdorferi)一覧が表示されるので、列**Organism Name**の[Borrelia burgdorferi B31](https://www.ncbi.nlm.nih.gov/genome/738?genome_assembly_id=168382)をクリックして開く。
**Replicon Info**下の表の列**RefSeq**と列**INSDC**に識別子 (Accession) が示されている。
列**Type**のChrは染色体、Plsmはプラスミドを指す。

[GenomeBentoProject](http://wiki.lifesciencedb.jp/mw/GenomeBentoProject)

![http://togotv.dbcls.jp/togopic.2013.18.html](https://dbarchive.biosciencedbc.jp/data/togo-pic/image/201306_genome_bento.png)


### E-utilities
- [Entrez Programming Utilities Help - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK25501/)
  - [Entrez Direct: E-utilities on the UNIX Command Line - Entrez Programming Utilities Help - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK179288/)
  - [The E-utilities In-Depth: Parameters, Syntax and More - Entrez Programming Utilities Help - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK25499/)
    - [Table 1 – Valid values of &retmode and &rettype for EFetch (null = empty string)](https://www.ncbi.nlm.nih.gov/books/NBK25499/table/chapter4.T._valid_values_of__retmode_and/?report=objectonly)

| Record Type | &rettype | &retmode |
|:-----------:|:--------:|:--------:|
| Additional option for db = nuccore |
| db = nuccore, nucest, nucgss, protein or popset |
| FASTA | fasta | text |
| GenBank flat file with full sequence (contigs) | gbwithparts | text |
| CDS nucleotide FASTA | fasta_cds_na | text |
| CDS protein FASTA | fasta_cds_aa | text |
| db = sequences |
| FASTA | fasta | text |

```
# Retrieving sequence data from NCBI
library("seqinr")
ACCESSION <- "NC_001318" # Borrelia burgdorferi B31 chromosome, complete genome
#ACCESSION <- "NC_008011.1" # Lawsonia intracellularis PHE/MN1-00

# fasta
seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)
write.fasta(sequences=seqs, names=getAnnot(seqs), file.out=paste0(ACCESSION,".fna"))

# fasta_cds_aa
seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_aa&retmode=text"), seqtype = c("AA"), strip.desc = TRUE)
write.fasta(sequences=seqs, names=getAnnot(seqs), file.out=paste0(ACCESSION,".faa"))

# fasta_cds_na
seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)
write.fasta(sequences=seqs, names=getAnnot(seqs), file.out=paste0(ACCESSION,".ffn"))

# Inspecting data
length(seqs) # get the number of elements
head(unlist(getAnnot(seqs))) # get sequence annotations
```

----------
## Codon usage
**コドン使用**

https://github.com/haruosuz/DS4GD/blob/master/2018/CaseStudy.md#codon-usage

[NCBI ASSEMBLY_REPORTS](#ncbi-assembly_reports)

[タンパク質コード配列(CDS)](https://www.ddbj.nig.ac.jp/ddbj/cds.html)データを取得する:  

    # Retrieving sequence data from NCBI

    # Load the SeqinR package
    library(seqinr)

    # accession prefix: GCA for GenBank and GCF for RefSeq
    ftp_path <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/005/845/GCF_000005845.2_ASM584v2" # Escherichia coli str. K-12 substr. MG1655
    filesuffix <- "_cds_from_genomic.fna.gz"
    curl <- paste0(ftp_path, "/", unlist(strsplit(ftp_path, split="/"))[10], filesuffix )
    seqs <- read.fasta(file = gzcon(url(curl)), seqtype = c("DNA"), strip.desc = TRUE) # Retrieve the sequences and store them in list variable "seqs"

    # E-utilities: fasta_cds_na
    ACCESSION <- "NC_008011.1" # Lawsonia intracellularis PHE/MN1-00
    seqs <- read.fasta(file = paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta_cds_na&retmode=text"), seqtype = c("DNA"), strip.desc = TRUE)

    # Print out the number of sequences retrieved
    length(seqs)

DNA配列の長さが3の倍数（コドン）にならないCDS（例えば、偽遺伝子 pseudogene）を解析から除外する:  

    TF <- sapply(seqs, length)%%3 != 0; sum(TF); unlist(getAnnot(seqs[TF])); # [pseudo=true]
    TF <- grepl(pattern = "pseudo=true", x = getAnnot(seqs)); sum(TF); unlist(getAnnot(seqs[TF]))
    seqs <- seqs[!TF]

`unlist()`関数は、リストの要素を端からベクトルとして結合して 1 つのベクトルとしてまとめる。
複数のDNA配列の結合データを作成する:  

    # Flatten Lists
    seqs.concat <- unlist(seqs)

全てのタンパク質コード配列(CDS)の累積コドン使用頻度（絶対度数、相対度数、観測度数と期待度数の比）を計算する:  

    # Codon usage for the collection of all genes
    uco(seqs.concat, index = "eff")  # Absolute frequencies
    uco(seqs.concat, index = "freq") # Relative frequencies
    uco(seqs.concat, index = "rscu") # Relative Synonymous Codon Usage (RSCU)
    df <- uco(seqs.concat, as.data.frame = TRUE) # all indices are returned into a data frame

    # Data Output
    write.csv(df[order(df$AA),], file="~/Desktop/table.csv", quote=TRUE, row.names=TRUE)
    write.table(df[order(df$AA),], file="~/Desktop/table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names = NA)

G-language System 
[コドン使用の解析](http://www.g-language.org/wiki/restgenomeanalysisjapanese#コドン使用の解析)
[Codon usage analysis](http://www.g-language.org/wiki/restgenomeanalysisenglish#codon_usage_analysis)

- http://rest.g-language.org/NC_008011 # Lawsonia intracellularis PHE/MN1-00 chromosome, complete genome.
- http://rest.g-language.org/NC_008011/codon_compiler/data=R0
- http://rest.g-language.org/NC_008011/codon_compiler/data=R3
- http://rest.g-language.org/help/codon_compiler

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
    filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta") # http://togows.dbcls.jp/help/
    seqs <- read.fasta(file = filename, seqtype = c("DNA"), strip.desc = TRUE)
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

[Exercises on DNA Sequence Statistics (2)](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter2.html#exercises)

Download the DNA sequence of your genome of interest. Answer the following questions. For each question, please record your answer, and what you typed to get this answer.

NCBIからDNA配列を取得する:  

    # Retrieving a DNA sequence from NCBI
    library("seqinr")
    ACCESSION <- "NC_001477" # Dengue virus 1
    #ACCESSION <- "NC_002677" # Mycobacterium leprae TN chromosome
    #ACCESSION <- "NC_001318" # Borrelia burgdorferi B31 chromosome, complete genome
    filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta") # http://togows.dbcls.jp/help/
    seqs <- read.fasta(file = filename, seqtype = c("DNA"), strip.desc = TRUE)
    seq1 <- seqs[[1]]

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
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/ASSEMBLY_REPORTS/assembly_summary_refseq.txt"
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

[大腸菌](https://www.sbj.or.jp/wp-content/uploads/file/sbj/9010/9010_yomoyama-1.pdf)
[Escherichia coli K-12](https://en.wikipedia.org/wiki/Escherichia_coli_in_molecular_biology#K-12)
の完全ゲノム("Complete Genome")配列データの最新版("latest")のURLを抽出する:  

List the ftp_path (column 20) for the assemblies of interest, in this case those that have organism_name of "Escherichia coli K-12" (column 8), "latest" version_status (column 11) and "Complete Genome" assembly_level (column 12)

    # grep(pattern, x) returns the positions of all elements in x that match pattern
    # grepl returns a logical vector (match or not for each element of x).
    pattern <- "Escherichia coli.*K-12"
    #pattern <- "Borrelia burgdorferi"
    #pattern <- "Sinorhizobium meliloti"
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
    filesuffix <- "_genomic.fna.gz"
    #filesuffix <- "_cds_from_genomic.fna.gz"
    #filesuffix <- "_protein.faa.gz"
    curl <- paste0(d$ftp_path[TF], "/", unlist(strsplit(d$ftp_path[TF], split="/"))[10], filesuffix )
    download.file(url = curl, destfile = basename(curl))

`read.fasta()`関数で配列データを読み込む:  

    # Reading sequence data
    library("seqinr") # Load the SeqinR package
    filename <- basename(curl)
    seqs <- read.fasta(file = filename, seqtype = c("DNA"), strip.desc = TRUE)
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

    par(family="mono")

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
    curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_reference_genomes.txt"
    #curl <- "ftp://ftp.ncbi.nlm.nih.gov/genomes/GENOME_REPORTS/prok_representative_genomes.txt"
    download.file(url = curl, destfile = basename(curl))

[Ｒ言語のデータの入出力と編集](https://www.cis.doshisha.ac.jp/mjin/R/02.html)

データのインポート。`read.delim()`関数でタブ区切りファイルを読み込む:  

    # Loading Data into R
    filename <- basename(curl)
    d <- read.delim(file = filename, stringsAsFactors = FALSE, check.names = FALSE)

[データフレーム](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/39.html)の行と列の数、先頭部分、列名の確認:  

    # Exploring and Transforming Dataframes
    dim(d)
    head(d, n = 1)
    colnames(d)
    colnames(d)[1] <- "species_genus"

[文字列 | R で文字列の切り出しや置換などの文字列処理を行う方法](https://stats.biopapyrus.jp/r/basic/string.html)

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

    setwd("~/projects/data/ncbi/genome_reports")					# Set Working Directory
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
    count(seq=seq1, wordsize=2)

#### [DNA Sequence Statistics (2)](https://github.com/haruosuz/r4bioinfo/tree/master/R_Avril_Coghlan#dna-sequence-statistics-2)

Sliding windowでゲノムの局所的な塩基組成（GC content, GC skew）を解析する:  

	# Local variation in GC content
	# A sliding window analysis of GC content
	# A sliding window plot of GC content
    library(zoo) # rollapply

    pdf(file="Rplot.pdf") # create a PDF device called "Rplot.pdf"

    par(family="mono")

    par(mfcol=c(1,1), cex=1.5, mai = c(1.2, 1.2, 0.1, 0.1)) # c(bottom, left, top, right)

    # x-axis: Position
    windowsize <- 10000
    x <- seq(from = 1, to = length(seq1)-windowsize, by = windowsize) / 10^6
    xlab <- "Position (Mb)"

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
- [Arakawa K, Tomita M. (2007)](https://www.ncbi.nlm.nih.gov/pubmed/19461976/) | ["バクテリアゲノムの複製による選択度合いを定量化"](http://www.iab.keio.ac.jp/research/highlight/papers/200904130118.html)
- [Karlin S (2001) Trends Microbiol. "Detecting anomalous gene clusters and pathogenicity islands in diverse bacterial genomes."](https://www.ncbi.nlm.nih.gov/pubmed/11435108) | [pdf](https://eclass.uoa.gr/modules/document/file.php/D473/Βιβλιογραφία/DNA%20Composition/Karlin_2001.pdf)

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

    # Data Output
    write.csv(t(X), file="table.csv", quote=TRUE, row.names=TRUE)
    write.table(t(X), file="table.txt", sep="\t", quote=FALSE, row.names=TRUE, col.names = NA)

    # open current working directory
    system("open .")

`matplot()`関数でプロットする:  

    par(family="mono")

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

----------
## assignment 7
**課題No.7 「Pairwise Sequence Alignment」**

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
## assignment 8
**課題No.8 「Multiple Alignment and Phylogenetic Trees」**

[Exercises on Multiple Alignment and Phylogenetic Trees](http://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter5.html#exercises)

Answer the following questions, using the R package. For each question, please record your answer, and what you typed into R to get this answer.

Q1. Calculate the genetic distances between four protein sequences of interest. Which are the most closely related proteins, and which are the least closely related, based on the genetic distances?

    library("seqinr") # Load the SeqinR package
    # create a function to retrieve several sequences from UniProt
    retrieve_seqs_uniprot <- function(ACCESSION) read.fasta(file = paste0("http://www.uniprot.org/uniprot/",ACCESSION,".fasta"), seqtype = c("AA"), strip.desc = TRUE)[[1]]

    seqnames <- c("Q9YRR4", "Q9YP96", "B0LSS3", "Q6TFL5") # Make a vector containing the names of the sequences
    seqs <- lapply(seqnames,  retrieve_seqs_uniprot) # Retrieve the sequences and store them in list variable "seqs"

    length(seqs) # get the number of elements
    unlist(getAnnot(seqs)) # get sequence annotations

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

Q3. Build a rooted phylogenetic tree of the four proteins, using an outgroup. Which are the most closely related proteins, based on the tree? What extra information does this tree tell you, compared to the unrooted tree in Q2?

    library("seqinr")
    # create a function to retrieve several sequences from UniProt
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

    # read the FASTA-format alignment into R, and calculate the genetic distances between the protein sequences:
    myaln <- read.alignment(file = "myaln.fasta", format = "fasta")
    mydist <- dist.alignment(myaln)
    mydist

    # construct a phylogenetic tree
    library(ape)
    mytree <- nj(mydist)
    mytree <- root(mytree, outgroup = "Q32ZE1", resolve.root = TRUE)
    plot.phylo(mytree, main = "Phylogenetic Tree")

----------
## assignment-9
**課題No.9 「draft report」**

Integrate and edit your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it in PDF format.

これまでの課題（興味あるDNA/タンパク質の配列解析の結果）を統合・編集してレポートのドラフトを作成し、PDFファイルで提出する。

----------
## assignment-10
**課題No.10 「presentation slides」**

https://github.com/haruosuz/DS4GD/tree/master/2018giga#final-presentation

2019-01-15 最終発表のスライド <YOUR_NAME.pdf> を提出する。
発表時間：1人あたり最大5分

生物学的データ（ゲノムDNA配列やタンパク質配列）の解析結果を報告する。解析の例として、DNA配列の統計（長さ、GC含量、連続塩基組成、塩基組成の局所変動）、ペアワイズ配列アラインメント（ドットプロット、グローバル/ローカル・アラインメント）、多重配列アライメントと系統樹、公共データベース・ウェブツールによる解析などが含まれる。

Submit your PDF presentation slides for your final presentation 最終発表 Tuesday 2019-01-15.
Five minutes will be allocated for each presentation, including presentation and discussion.

Report your main findings on analyses of biological data (e.g. genome DNA sequences and protein sequences) you're interested in. The analyses can include DNA sequence statistics (length, GC Content, DNA words, and local variation in base composition), pairwise sequence alignment (dotplot, global/local alignment), multiple alignment and phylogenetic trees, public database and web tools, etc.

----------
## Sequence similarity search
**配列類似性検索**

[(Rで)塩基配列解析](http://www.iu.a.u-tokyo.ac.jp/~kadota/r_seq.html)
「2-1. 配列解析基礎」坊農秀雅 (DBCLS)
[講義資料](http://www.iu.a.u-tokyo.ac.jp/~kadota/bioinfo_ngs_sokushu_2014/20140905_2-1_bono.pdf)

----------
## UniProtKB Swiss-Prot protein sequence database
**[Swiss-Prot](https://ja.wikipedia.org/wiki/Swiss-Prot)タンパク質配列データベース**

### Downloading data
データのダウンロード

<ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/> をブラウザ（Firefox または Chrome）で開く。  
*uniprot_sprot.fasta.gz* を右クリックし、「リンクのURLをコピー (Copy Link)」する。

Open the URL <ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/> with your browser (Firefox or Chrome).  
Right click the link *uniprot_sprot.fasta.gz* and select "Copy Link Address".

![https://moshbox.jp/?p=27311](https://moshbox.jp/be/wp-content/uploads/2017/03/Terminal_Commands-01.png)

    # change shell to bash
    bash

ディレクトリを作成する:  

    # make directories
    mkdir -p ~/projects/data/uniprot/uniprot_sprot

ディレクトリを移動する:  

    # change directories
    cd ~/projects/data/uniprot/uniprot_sprot/

圧縮ファイル（*uniprot_sprot.fasta.gz*）を`wget`または`curl`でダウンロードする:  

    # download data with wget and curl
    #wget -b ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz
     curl -O ftp://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/uniprot_sprot.fasta.gz

`tail -f`でファイル出力を監視する（Control-Cで動作中のプロセスを停止）:  

    # Use `tail -f` to constantly monitor files (use Control-C to stop)
    tail -f wget-log

`gunzip`コマンドでファイルを展開する:  

    # decompress files with the command gunzip
    gunzip -c uniprot_sprot.fasta.gz > uniprot_sprot.fasta

### Inspecting data
データの検査 

`ls -lh`でファイルサイズを確認する:  

    # ls -lh reports human-readable file sizes
    ls -lh

[`head`](http://codezine.jp/unixdic/w/head)で先頭部分を表示する:  

    # look at the top of a file with head
    head -n 3 uniprot_sprot.fasta

Extract [FASTA headers](http://www.uniprot.org/help/fasta-headers).

`grep`で、[FASTA](https://ja.wikipedia.org/wiki/FASTA)形式ファイルのヘッダ（`>`で始まる行）にマッチする行を抽出する（Control-Cで動作中のプロセスを停止）:  

    # use grep to extract lines matching the pattern "^>" (use Control-C to stop)
    grep "^>" uniprot_sprot.fasta

Pipe the standard output to the next command with the pipe character (`|`).

[パイプ](https://ja.wikipedia.org/wiki/パイプ_%28コンピュータ%29)でプログラムの入出力をつなぐ。

    grep "^>" uniprot_sprot.fasta | head -n 2

配列の数をカウントする:  

    # wc -l outputs the number of lines
    grep "^>" uniprot_sprot.fasta | wc -l

### [BLAST](https://github.com/haruosuz/bioinfo/blob/master/references/README.blast.md)

[変数に値を設定する](https://shellscript.sunone.me/variable.html#変数に値を設定する):  

    # create a variable and assign it a value
    DB="uniprot_sprot.fasta"
    echo $DB

`makeblastdb`コマンドで、BLAST用に DB の index を作成する:  

    # Building a BLAST database http://www.ncbi.nlm.nih.gov/books/NBK279688/

    # アミノ酸配列をBLAST用にフォーマット
    makeblastdb -in $DB -dbtype prot -hash_index -parse_seqids

BLAST検索に使うquery配列の取得

`blastdbcmd`コマンドで、[自家製BLAST用DBから必要な配列エントリ取得](https://bonohu.wordpress.com/2014/08/08/yetanother-blastdbcmd/):  

    # Extracting data from BLAST databases with blastdbcmd https://www.ncbi.nlm.nih.gov/books/NBK279689/
    # >sp|P05833|REPA_ECOLX Protein RepA OS=Escherichia coli OX=562 GN=repA PE=3 SV=1
    blastdbcmd -db $DB -entry all -outfmt "%i %t" | awk '/P05833|REPA_ECOLX/ {print $1}' | \
     blastdbcmd -db $DB -entry_batch - > myquery.fasta

BLASTの実行:  

    # Running BLAST
    blastp -db $DB -query myquery.fasta

    blastp -db $DB -query myquery.fasta -outfmt 7 -out blastp-out.txt -evalue 1e-10 -num_threads 4

`blastdbcmd`コマンドで、ヒットした配列をBLAST用DBから取得:  

    # Extracting data from BLAST databases with blastdbcmd
    grep -v '#' blastp-out.txt | awk '{print $2}' | uniq | head -n 10 | blastdbcmd -db $DB -entry_batch - > mysubject.fasta

### [Multiple Alignment and Phylogenetic trees](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#multiple-alignment-and-phylogenetic-trees)
多重配列アライメントと系統樹

    # Multiple Sequence Alignment using MAFFT
    mafft mysubject.fasta > myalign.fasta

- [2018-04-03 MAFFT・RAxML・FigTreeを組み合わせて分子系統解析を行う](https://togotv.dbcls.jp/20180403.html)
- [2015-04-13 MAFFTを使ってマルチプルアラインメントを行う](http://doi.org/10.7875/togotv.2015.035)

![](http://www2.tba.t-com.ne.jp/nakada/takashi/phylogeny/fig/sv2/sv7.jpg)

[SeaView](http://www2.tba.t-com.ne.jp/nakada/takashi/phylogeny/seaview2.html)でアライメントを表示する。

[SeaView](http://doua.prabi.fr/software/seaview) is a multiplatform, graphical user interface for multiple sequence alignment and molecular phylogeny.

![](https://weblogo.berkeley.edu/img/weblogo-fig1.png)

[WebLogo](http://weblogo.berkeley.edu/logo.cgi)で配列の保存度を表示する。

[WebLogo](https://weblogo.berkeley.edu/) generates sequence logos indicating sequence conservation.

![http://cse.naro.affrc.go.jp/takezawa/r-tips/r/02.html](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/image/Mac.gif)

[作業ディレクトリ](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/06.html)の変更と確認:  

    WorkingDirectory <- "~/projects/data/uniprot/uniprot_sprot"

    # Set and Get Working Directory
    setwd(WorkingDirectory)
    getwd()

    # List the Files in a Directory
    dir()

    # 多重アライメントのファイルをRに読み込む
    # Reading a multiple alignment file into R
    library(seqinr)
    myaln <- read.alignment(file = "myalign.fasta", format = "fasta")

    # タンパク質配列間の遺伝的距離を計算する
    # Calculating genetic distances between protein sequences
    mydist <- dist.alignment(myaln)

    # 無根系統樹の構築
    # Building an unrooted phylogenetic tree
    library(ape)
    mytree <- nj(mydist)
	par(family="mono")
    plot.phylo(mytree, type = "unrooted") # type = "phylogram", "cladogram", "fan", "unrooted", "radial"

    # 有根系統樹
    # Building a rooted phylogenetic tree
    library(phangorn); mytree <- midpoint(mytree) # midpoint rooting
    plot.phylo(ladderize(mytree, right = FALSE), main = "Phylogenetic Tree")

    # Saving a phylogenetic tree as a Newick-format tree file
    write.tree(mytree, file="mytree.newick")

    # open current working directory
    system("open .")

[SeaView](http://doua.prabi.fr/software/seaview)で系統樹を表示する。

[SeaView Version 4: A Multiplatform Graphical User Interface for Sequence Alignment and Phylogenetic Tree Building](https://academic.oup.com/mbe/article/27/2/221/970247)

![](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/mbe/27/2/10.1093/molbev/msp259/2/m_molbiolevolmsp259f01_3c.gif?Expires=1545572639&Signature=fOWaS-pdA~W-WnKyf1YvpUrcbrK6B0FVW5WBmrE~BczkdAgkModbmfuC7hKvNqBjJExgGZzAJt-~usX0g38ApCVbJxYzQzr1AIgjIgztMI6v3c6U~MSWbckpj63YACB5Z8vd60XJe3kC8pnle5~x2ImDyUTWGjQutx4X6kck0-gpOQ1-o4jiEVYx-1ulL63-r0lM8K~MtN5AE1NgdElTvvLa0ui6YLME5u2gf17Y8U~onACmCPbf42K-RZg4mFDOJw0pe0O6qI~oTdSUoS0DTfackKrz5V6qujwERSCdR2778J9fTOxyz2jSpWVgtTxZTpTOQT3npMZvnztYAmZ~Cg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

----------

