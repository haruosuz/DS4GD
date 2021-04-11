**[DATA SCIENCE FOR GENOME DYNAMICS](https://github.com/haruosuz/DS4GD/tree/master/2021)**  
[SFC Online Learning System (SOL)](https://sol.sfc.keio.ac.jp/)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題1 「Introduction to R」
- [assignment 2](#assignment-2) 課題2 「Installing R packages」
- [assignment 3](#assignment-3) 課題3 「DNA Sequence Statistics (1)」
- [NCBI Genome List](#ncbi-genome-list)
- [assignment 4](#assignment-4) 課題4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題5 「dotplot」
- [BLAST](#blast)
  - [UniProt BLAST](#uniprot-blast)
- [assignment 6](#assignment-6) 課題6 「Pairwise Sequence Alignment」
- [assignment 7](#assignment-7) 課題7 「Multiple Alignment and Phylogenetic trees」
- [assignment 8](#assignment-8) 課題8
- [assignment 9](#assignment-9) 課題9 「draft report」
- [assignment 10](#assignment-10) 課題10 「final report」

----------
## assignment 0
**選抜課題**

本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

----------
## assignment 1
**課題1 「Introduction to R」**

Watch the following videos and write your comments or questions.
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

以下の動画を見て、疑問点を報告する。
- [Rプログラミングと統計](https://www.youtube.com/watch?v=jjkBsU4AChM&list=PLdNQOrt5fdN8P-vy1i6vep9OP4R1AZcEb)


[回答例]
```
「Rプログラミングと統計 p.3 ~ p.10 を見た。
疑問点は次の通りである。
1. 行列とデータフレームとリストの違いは？
2. NAとNaNの違いが理解できなかった。
```

----------
## assignment 2
**課題2 「Installing R packages」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

Please download the R script (*my_setup_packages.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

回答例:  
```
# Example answer:  

> # Print the versions of these packages:
> packageVersion("tidyverse")
[1] ‘1.3.0’
> packageVersion("seqinr")
[1] ‘4.2.5’
> packageVersion("zoo")
[1] ‘1.8.9’
> packageVersion("ape")
[1] ‘5.4.1’
> packageVersion("phangorn")
[1] ‘2.6.3’
> packageVersion("phytools")
[1] ‘0.7.70’
> packageVersion("msaR")
[1] ‘0.5.0’
> packageVersion("microseq")
[1] ‘2.1.4’
> 
> packageVersion("Biostrings")
[1] ‘2.58.0’
> packageVersion("msa")
[1] ‘1.22.0’
> packageVersion("DECIPHER")
[1] ‘2.18.1’

> # Print the version of R running:
> R.version.string
[1] "R version 4.0.3 (2020-10-10)"
> 
> # Print version information about R, the OS and attached or loaded packages.
> sessionInfo()
R version 4.0.3 (2020-10-10)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Catalina 10.15.7
```

----------
## NCBI Genome List
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

- NCBIのウェブサイトからゲノム配列データを取得する。
  - ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。
例えば、[新型コロナウイルス感染症 (COVID-19)](https://ja.wikipedia.org/wiki/新型コロナウイルス感染症_%282019年%29)の原因となる[SARSコロナウイルス2](https://ja.wikipedia.org/wiki/SARSコロナウイルス2) "SARS-CoV-2" を検索する。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2)、検索ボックス下の「Overview (1); Viruses (92)」のうち、「Viruses」をクリックすると、SARS-CoV-2に属する株が表示される。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2)、列**Organism Name**の"Severe acute respiratory syndrome coronavirus 2"をクリックして開く。
  - [ここで](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732)、**Replicon Info**下のテーブルの列**RefSeq**と列**INSDC**に[アクセッション番号](https://www.ddbj.nig.ac.jp/acc_def.html)が示されている。
アクセッション番号は、"NC_045512.2" (RefSeq) と "MN908947.3" (INSDC) である。

- Retrieving genome sequence data via the NCBI website
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for [Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2), the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), you would type just Organism name "SARS-CoV-2" in the search box and press "Search".
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2), you will see the number of hits to "SARS-CoV-2" in each of the NCBI databases: "Overview (1); Viruses (92)". When you click on "Viruses", it will show all the strains.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2), When you click on the Organism Name "Severe acute respiratory syndrome coronavirus 2", it will bring you to the record for this organism in the NCBI Genome database.
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/86693?genome_assembly_id=757732), you will see the "Replicon Info" of the Organism. 
The NCBI [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the DNA sequences are "NC_045512.2" (RefSeq) and "MN908947.3" (INSDC), respectively.

NCBIからDNA配列を取得する:  
```
# Retrieving a DNA sequence from NCBI
library(seqinr)

ACCESSION <- "NC_045512" # Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)
#ACCESSION <- "NC_001477" # Dengue virus 1

filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
#filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")

seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)
seq1 <- seqs[[1]]
```

Please record what you typed to download DNA sequence data, to make your analysis reproducible.

----------
## assignment 3
**課題3 「DNA Sequence Statistics (1)」**

Please download the R script (*my_assignment_chapter1_dna1.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 4
**課題4 「DNA Sequence Statistics (2)」**

Please download the R script (*my_assignment_chapter2_dna2.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

You can submit your assignment as a HTML document (*my_assignment_chapter2_dna2.html*), created using the [Compile Report](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report) command.

----------
## assignment 5
**課題5 「dotplot」**

Please download the R script (*my_assignment_chapter4_align_dotplot.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## BLAST
[BLAST (Basic Local Alignment Search Tool)](https://ja.wikipedia.org/wiki/BLAST)

### [UniProt BLAST](https://www.uniprot.org/blast/)
- [How to use UniProt tools](https://www.ebi.ac.uk/training/online/course/uniprot-exploring-protein-sequence-and-functional/exploring-uniprotkb-entry/how-use-uniprot-t)
  - ['BLAST' sequence similarity searching](https://www.ebi.ac.uk/training/online/course/uniprot-exploring-protein-sequence-and-functional/how-use-uniprot-tools/blast-sequence-simila)

![](https://www.ebi.ac.uk/training/online/sites/ebi.ac.uk.training.online/files/user/2760/images/UniProt_tutorial/blast_1.png)

- [Severe acute respiratory syndrome coronavirus 2 (2019-nCoV) (SARS-CoV-2)](https://www.uniprot.org/taxonomy/2697049)
  - [Reviewed (16)](https://www.uniprot.org/uniprot/?query=reviewed:yes%20taxonomy:2697049) Swiss-Prot
    - [Spike glycoprotein](https://www.uniprot.org/uniprot/P0DTC2)
    - [Envelope small membrane protein](https://www.uniprot.org/uniprot/P0DTC4)
    - [ORF3b protein](https://www.uniprot.org/uniprot/P0DTF1)
- Select the 'Blast' tab -> 'Advanced'
```
Target database: UniProtKB/Swiss-Prot
E-Threshold: 0.0001
Hits: 50
```
- Click the 'Run Blast' button.

----------
## assignment 6
**課題6 「Pairwise Sequence Alignment」**

Please download the R script (*my_assignment_chapter4_align_pairwise.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 7
**課題7 「Multiple Alignment and Phylogenetic trees」**

Please download the R script (*my_assignment_chapter5_msa_tree.R*) from the following URL.
https://github.com/haruosuz/r4bioinfo/raw/master/R_Avril_Coghlan/scripts.zip

----------
## assignment 8
**課題8


----------
## assignment 9
**課題9 「draft report」**

Integrate and modify your previous assignments (e.g. results of analyzing DNA/protein sequences of interest) in order to produce a draft report, and submit it as a PDF/HTML document.

これまでの課題（興味あるDNA/タンパク質の配列を解析した結果など）を統合・修正してレポートのドラフトを作成し、PDF/HTML形式ファイルで提出する。

https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter_answers.html

----------
## assignment 10
**課題10 「final report」**

Submit your final report as a PDF/HTML document.

----------

