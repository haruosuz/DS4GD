https://github.com/haruosuz/DS4GD/

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [INSDC](#insdc)
  - [NCBI Genome List](#ncbi-genome-list)
  - [NCBI Datasets](#ncbi-datasets)
  - [seqinr](#seqinr)
- [BLAST](#blast)
  - [UniProt BLAST](#uniprot-blast)
  - [NCBI BLAST](#ncbi-blast)
    - [BLAST_2_SEQUENCES](#blast_2_sequences)
    - [blastp](#blastp)
    - [tblastn](#tblastn)
  - [Query Sequences](#query-sequences)
- [MEGA](#mega)
- [Chunk options](#chunk-options)
- [Compile Report](#compile-report)
- [assignment 1](#assignment-1)
  - [R_DSD_10](#r_dsd_10)
[R_assignOps](#r_assignOps)
[R_built-in](#r_built-in)
[R_data.frame](#r_dataframe)
[R_factor](#r_factor)
[R_indexing](#r_indexing)
[R_list](#r_list)
[R_matrix](#r_matrix)
[R_object](#r_object)
[R_operator](#r_operator)
[R_options](#r_options)
[R_plot](#r_plot)
[R_quit](#r_quit)
[R_quotes](#r_quotes)
[R_read.table](#r_readtable)
[R_typeof](#r_typeof)
[R_vector](#r_vector)
- [Genome signature](#genome-signature) ゲノムの特徴
- [](#)

https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md

----------
## INSDC

[International Nucleotide Sequence Database Collaboration](https://www.ddbj.nig.ac.jp/insdc-e.html)
[塩基配列データベース構築の国際協調](https://www.ddbj.nig.ac.jp/insdc.html)

<img src="https://www.ddbj.nig.ac.jp/assets/images/center/insdc_shoukai.gif" alt="https://www.ddbj.nig.ac.jp/about/insdc.html" width=25%>

- [RefSeq Frequently Asked Questions (FAQ) - RefSeq Help - NCBI Bookshelf](https://www.ncbi.nlm.nih.gov/books/NBK50679/)
  - [What is the difference between RefSeq and GenBank?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_is_the_difference_between_1)
  - [What causes the version number of a RefSeq record to change?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_causes_the_version_number)
  - [What updates to RefSeq records need a simple version number change and which require a new accession number?](https://www.ncbi.nlm.nih.gov/books/NBK50679/#RefSeqFAQ.what_updates_to_refseq_records)
- VERSION
  - [DDBJ flat file format](https://www.ddbj.nig.ac.jp/ddbj/flat-file-e.html#VERSION)
This line consists of an accession number and a version number, like “AB123456.1”, in which the digit(s) after the period is a version number.
The data open to public for the first time is version number as “1”. The reason for adding VERSION is that since a released sequence sometimes revised by the submitter, the accession number alone cannot specify the sequence in question causing the user a trouble. The number is increased by one every time when a revised sequence is made public. And accession number will NOT be changed generally.
  - [DDBJ 公開形式 Flat file](https://www.ddbj.nig.ac.jp/ddbj/flat-file.html#VERSION)
アクセッション番号とバージョン番号で構成されています。
はじめて公開されたデータは、バージョン番号は “1” が記載されています。当該エントリの配列が訂正・更新された場合には、バージョン番号が更新されます。通常、配列が訂正・更新された場合にアクセッション番号が変更されることはありません。

----------
### NCBI Genome List
[NCBI](https://ja.wikipedia.org/wiki/国立生物工学情報センター)の[ゲノムリスト](http://bonohu.jp/blog/genome-list.html)

- Retrieving genome sequence data via the NCBI website  
NCBIのウェブサイトからゲノム配列データを取得する。  
  - At the top of the NCBI website (http://www.ncbi.nlm.nih.gov/genome/browse/), you will see a search box, and you can type the Organism name or Accession of the sequence that you are looking for in this search box, and then click on the "Search" button to search for it. For example, if you want to find the sequence for [Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2), the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), you would type just Organism name "SARS-CoV-2" in the search box and press "Search".  
ゲノムブラウザ [Entrez Genome browser](http://www.ncbi.nlm.nih.gov/genome/browse/)上部の検索ボックスに [ 生物名 (Organism Name) または 識別子 (Accession) ] を入力して、「Search」ボタンを押す。例えば、[新型コロナウイルス感染症 (COVID-19)](https://ja.wikipedia.org/wiki/新型コロナウイルス感染症_%282019年%29)の原因となる[SARSコロナウイルス2](https://ja.wikipedia.org/wiki/SARSコロナウイルス2) "SARS-CoV-2" を検索する。  
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2), you will see the number of hits to "SARS-CoV-2" in each of the NCBI databases: "Overview (1); Viruses (92)". When you click on "Viruses", it will show all the strains.  
[ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/overview/SARS-CoV-2)、検索ボックス下の「Overview (1); Viruses (92)」のうち、「Viruses」をクリックすると、SARS-CoV-2に属する株が表示される。  
  - [On this page](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2), you will find "Severe acute respiratory syndrome coronavirus 2" in the **Organism Name** column. In the **Replicons** column, "NC_045512.2/MN908947.3" indicates the [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the RefSeq and GenBank (a member of the INSDC) databases, respectively.  
[ここで](https://www.ncbi.nlm.nih.gov/genome/browse/#!/viruses/SARS-CoV-2)、**Organism Name**列には "Severe acute respiratory syndrome coronavirus 2" が記載されている。**Replicons**列の "NC_045512.2/MN908947.3" は、RefSeq/GenBankデータベースの配列の[アクセッション番号](https://www.ddbj.nig.ac.jp/documents/accessions.html)を示す。

----------
### NCBI Datasets
A one-stop shop for finding, browsing, and downloading genomic data

https://www.ncbi.nlm.nih.gov/datasets/

- Retrieving genome sequence data from the NCBI website.  
NCBIのウェブサイトからゲノム配列データを取得する。  
  - [On this page](https://www.ncbi.nlm.nih.gov/datasets/), Click on the **Genome** tab.  
[このページ](https://www.ncbi.nlm.nih.gov/datasets/)で、 **Genome** タブをクリックする。
  - [On this page](https://www.ncbi.nlm.nih.gov/datasets/genome/), you will see a search box [ Enter a search term ], and you can "Enter one or more taxonomic names" that you are looking for in this search box, and then press Enter to search for it. For example, if you want to find the sequence for [Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2), the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), you would type just taxonomic name "SARS-CoV-2" in the search box and press Enter.  
[このページ](https://www.ncbi.nlm.nih.gov/datasets/genome/)で、検索ボックス [ Enter a search term ] に生物分類群（タクサ）名を入力してEnterキーを押す。例えば、[新型コロナウイルス感染症 (COVID-19)](https://ja.wikipedia.org/wiki/新型コロナウイルス感染症_%282019年%29)の原因となる[SARSコロナウイルス2](https://ja.wikipedia.org/wiki/SARSコロナウイルス2) "SARS-CoV-2" を検索する。  
  - [On this page](https://www.ncbi.nlm.nih.gov/datasets/genome/?taxon=2697049), under **Assembly**, you will see genome sequences; of which, click "ASM985889v3" as an example.  
[このページ](https://www.ncbi.nlm.nih.gov/datasets/genome/?taxon=2697049)で、 **Assembly** の下に、ゲノム配列データが表示される。このうち、例えば、"ASM985889v3"をクリックする。  
  - [On this page](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_009858895.2/), under **Chromosomes**, you will see [Accession Number](https://www.ddbj.nig.ac.jp/acc_def-e.html) for the GenBank and RefSeq databases (here, "MN908947.3" and "NC_045512.2", respectively).  
[このページ](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_009858895.2/)で、 **Chromosomes** の下に、GenBankとRefSeqデータベースの[アクセッション番号](https://www.ddbj.nig.ac.jp/documents/accessions.html)が示されている（ここでは、"MN908947.3" と "NC_045512.2"）。  

[Genome assembly ASM985889v3](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_009858895.2/)

Taxon | Severe acute respiratory syndrome coronavirus 2

| GenBank    | RefSeq     | Size (bp) | GC content (%) |
|:-----------|:------------|:-------|:---|
| MN908947.3 | NC_045512.2 | 29,903 | 38 |

**References**
- 2022/07/21 [Easy Access to Data with NLM's NCBI Datasets! - YouTube](https://www.youtube.com/watch?v=L4vn1426Pu8)
- Apr 5, 2024 [小野 浩雅 ONO, Hiromasa on X: "NCBI Datasets はゲノムデータに関するデータベースです。ゲノムデータの検索、閲覧、取得をワンストップで行うことができます。また、ゲノムデータに付随するアノテーション情報へのアクセスも容易で、配列データを用いて直接BLAST検索することもできます。"](https://twitter.com/h_ono/status/1776147714742317376)
- 2024.03.28 [NCBI Datasetsを使ってゲノムデータを検索、閲覧、取得する | TogoTV](https://doi.org/10.7875/togotv.2024.029) 11:46

----------
### seqinr

Retrieving genome sequence data from the NCBI database using SeqinR  
SeqinRパッケージを用いて、NCBIデータベースからゲノム配列データを取得する  

```
# Load the seqinr package
# seqinrパッケージを読み込む
library(seqinr)

# Store the accession number of the sequence data to be retrieved from the database in the variable "ACCESSION"
# データベースから取得する配列データのアクセッション番号を変数"ACCESSION"に格納する
ACCESSION <- "NC_045512" # RefSeq
ACCESSION <- "MN908947" # GenBank

# Create URL to access the sequence data
# 配列データにアクセスするためのURLを作成する
filename <- paste0("https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=",ACCESSION,"&rettype=fasta&retmode=text")
#filename <- paste0("http://togows.org/entry/nucleotide/",ACCESSION,".fasta")

# Print the variable content
# 変数の中身を表示する
ACCESSION
filename

# Retrieve the sequence data using the `seqinr::read.fasta()` function, and store it in the list variable "seqs"
# SeqinRパッケージの`read.fasta()`関数を用いて、配列データを取得し、"seqs"というリスト変数に格納する
seqs <- read.fasta(file=filename, seqtype="DNA", strip.desc=TRUE)

# Extract the 1st element from the list:
# リスト内の1番目の要素を取り出す。  
seq1 <- seqs[[1]]

# Get sequence annotations
# 配列のアノテーションを取得する
getAnnot(seq1)
```

----------
## BLAST
BLAST (Basic Local Alignment Search Tool)

Use the web browser Google Chrome. Using other web browsers (such as Safari) may result in different behavior.  
ウェブブラウザとしてGoogle Chromeを使用する。他のウェブブラウザ（例：Safariなど）を使用すると、異なる動作が生じる可能性がある。  

### UniProt BLAST
https://www.uniprot.org/blast/

![https://www.ebi.ac.uk/training/online/courses/uniprot-exploring-protein-sequence-and-functional-info/how-to-use-uniprot-tools-clone/](https://www.ebi.ac.uk/training/online/courses/uniprot-exploring-protein-sequence-and-functional-info/wp-content/uploads/sites/100/2022/07/Screenshot-2022-07-22-at-14.33.12.png)

EMBL-EBI Training > On-demand training > online_tutorial > UniProt [BLAST sequence similarity searching](https://www.ebi.ac.uk/training/online/courses/uniprot-exploring-protein-sequence-and-functional-info/how-to-use-uniprot-tools-clone/blast-sequence-similarity-searching/)

- Select the **BLAST** tab of the toolbar at the top of the page.  
ページの上部にあるツールバーの**BLAST**タブを選択する。
- Enter either *UniProt IDs* or *protein or nucleotide sequence(s) in FASTA format*.  
*UniProt IDs* または *FASTA形式のタンパク質または核酸配列* を入力する。
- [Optional settings](https://www.uniprot.org/help/blast-submission)
  - Target database: UniProtKB Swiss-Prot
  - E-Threshold: 0.00001
  - Hits: 50
- Click the **Run BLAST** button.  
**Run BLAST**ボタンをクリックする。
- [Tool results](https://www.uniprot.org/tool-dashboard)
- Check the box on the left side of the "Entry", click the "Add" button to execute "Add NN entries to the basket".
「Entry」の左側をチェックし、「Add」ボタンをクリックして、ヒットした配列をバスケットに追加する。
- Click on the image (Basket) located at the top right of the "BLAST results | UniProt" page.  
「BLAST results | UniProt」ページの右上にある画像（Basket）をクリックする。  
- Click on "Download" below "My Basket". Select "No" under "Compressed".  
「My Basket」の下にある「Download」をクリックする。"Compressed"の下で「No」を選択する。  

### [NCBI BLAST](https://blast.ncbi.nlm.nih.gov/)

#### BLAST_2_SEQUENCES
Blast 2 sequences: aligning two protein or nucleotide sequences

- [FEMS Microbiol Lett. 1999 "BLAST 2 Sequences, a new tool for comparing protein and nucleotide sequences"](https://pubmed.ncbi.nlm.nih.gov/10339815/)
- Barry Hall (2017) [Phylogenetic Trees Made Easy: A How-To Manual (5th edition)](https://github.com/haruosuz/DS4GD/blob/master/2021/CaseStudy.md#ptme5)
(p.48) Other Ways to Find Sequences of Interest (Beware! The Risks Are High)
- Query the NCBI Protein database by searching on the words [**ebgC Bacteroides**](https://www.ncbi.nlm.nih.gov/protein/?term=ebgC%20Bacteroides).
- Test the homology between
*Escherichia coli* EbgC protein (accession number [NP_417548.1](https://www.ncbi.nlm.nih.gov/protein/NP_417548.1))
and *Bacteroides* EbgC protein (accession number [EFI39110.1](https://www.ncbi.nlm.nih.gov/protein/EFI39110.1))
using [Protein BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastp&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome).
  - Checking the **Align two or more sequences** box will display two text boxes for entering queries.
  - Enter the accession number **NP_417548.1** into the upper search box.
  - Enter the accession number **EFI39110.1** into the lower search box.
  - Click on **+ Algorithm parameters**, change **Expect threshold** from 0.05 to 100, and then click the **BLAST** button.
  - The result shows an E value of 1.8 (above the limit of 1e-3 for homologs). Thus, despite having the same name, the *Bacteroides* EbgC sequences are not homologs of the *Escherichia coli* EbgC sequence.

#### blastp
[Protein BLAST: search protein databases using a protein query](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastp&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)

Here are the steps for running BLASTP:

- Click on the protein accession number (e.g., `/protein_id="AGI42838.1"`) from the GenBank page: 
https://www.ncbi.nlm.nih.gov/nuccore/KC241982
```
Canine circovirus isolate UCD1-1698, complete genome
GenBank: KC241982.1

LOCUS       KC241982                2063 bp    DNA     circular VRL 04-APR-2013

     CDS             1..912
                     /note="Rep"
                     /product="putative replication associated protein"
                     /protein_id="AGI42838.1"
```
- [On this page](https://www.ncbi.nlm.nih.gov/protein/AGI42838.1), select [Run BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE=Proteins&PROGRAM=blastp&BLAST_PROGRAMS=blastp&QUERY=AGI42838.1&LINK_LOC=protein&PAGE_TYPE=BlastSearch).
- Under **Choose Search Set**, select the **Database** "UniProtKB/Swiss-Prot (swissprot)".
- Click on **Algorithm parameters** and set the parameters as follows:
   - General Parameters
     - Max target sequences: 5000
     - Expect threshold: 1e-20
   - Scoring Parameters
     - Matrix: BLOSUM62
     - Gap Costs: Existence: 11 Extension: 1
- Click the **BLAST** button to execute.
- On this page *BLAST ® » blastp suite » results*, 
  - The results are displayed in a table under **Sequences producing significant alignments** in the **Descriptions** tab. For example, the **Accession** column lists the accession and version numbers of the hit sequences　(`subject acc.ver`).
  - Click **Download**, and select **Hit Table (text)** or **Hit Table (csv)**.

#### tblastn
[tblastn: search translated nucleotide databases using a protein query](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=tblastn&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)

- Click on the protein accession number (e.g., `/protein_id="ADF36634.1"`) from the GenBank page: 
https://www.ncbi.nlm.nih.gov/nuccore/GU479466
```
Neisseria gonorrhoeae strain 5289 plasmid pEP5289, complete sequence
GenBank: GU479466.1

LOCUS       GU479466               42004 bp    DNA     circular BCT 06-APR-2020

     CDS             complement(6730..8664)
                     /note="tetracyclin resistance protein"
                     /product="TetM"
                     /protein_id="ADF36634.1"
```
- [On this page](https://www.ncbi.nlm.nih.gov/protein/ADF36634.1), select [Run BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE=Proteins&PROGRAM=blastp&BLAST_PROGRAMS=blastp&QUERY=ADF36634.1&LINK_LOC=protein&PAGE_TYPE=BlastSearch).
- Click on the [tblastn](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=tblastn&PAGE_TYPE=BlastSearch&BLAST_SPEC=&LINK_LOC=blasttab&LAST_PAGE=blastp&QUERY=ADF36634.1).
- You can also **Enter Query Sequence** into the form field.
- Click on **Algorithm parameters**, and select/change values as follows:
  - Max target sequences: 5000
  - Expect threshold: 1e-20
- Click on **BLAST** button to execute.

#### blastn
[Nucleotide BLAST: search nucleotide databases using a nucleotide query](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&PAGE_TYPE=BlastSearch)

- Query nucleotide sequence https://www.ncbi.nlm.nih.gov/nuccore/NC_001477
```
Dengue virus 1, complete genome
NCBI Reference Sequence: NC_001477.1
```
- [On this page](https://www.ncbi.nlm.nih.gov/nuccore/NC_001477), click **[Run BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE=Nucleotides&PROGRAM=blastn&QUERY=NC_001477.1&DATABASE=nr&MEGABLAST=on&BLAST_PROGRAMS=megaBlast&LINK_LOC=nuccore&PAGE_TYPE=BlastSearch)**.
- Alternatively, you can paste or enter the nucleotide sequence directly into the **"Enter Query Sequence"** field.
- Click **“Algorithm parameters”** and set the parameters as follows:
  - Max target sequences: 5000
  - Expect threshold: 1e-20
- Click the **BLAST** button to execute.

### Query Sequences

Here are examples of protein sequences as queries for a BLAST search:

https://rest.uniprot.org/uniprotkb/Q9CD83.fasta
```
>sp|Q9CD83|PHBS_MYCLE Chorismate pyruvate-lyase OS=Mycobacterium leprae (strain TN) OX=272631 GN=ML0133 PE=3 SV=1
MTNRTLSREEIRKLDRDLRILVATNGTLTRVLNVVANEEIVVDIINQQLLDVAPKIPELE
NLKIGRILQRDILLKGQKSGILFVAAESLIVIDLLPTAITTYLTKTHHPIGEIMAASRIE
TYKEDAQVWIGDLPCWLADYGYWDLPKRAVGRRYRIIAGGQPVIITTEYFLRSVFQDTPR
EELDRCQYSNDIDTRSGDRFVLHGRVFKNL
```

https://rest.uniprot.org/uniprotkb/A0PQ23.fasta
```
>tr|A0PQ23|A0PQ23_MYCUA Chorismate pyruvate-lyase OS=Mycobacterium ulcerans (strain Agy99) OX=362242 GN=MUL_2003 PE=4 SV=1
MLAVLPEKREMTECHLSDEEIRKLNRDLRILIATNGTLTRILNVLANDEIVVEIVKQQIQ
DAAPEMDGCDHSSIGRVLRRDIVLKGRRSGIPFVAAESFIAIDLLPPEIVASLLETHRPI
GEVMAASCIETFKEEAKVWAGESPAWLELDRRRNLPPKVVGRQYRVIAEGRPVIIITEYF
LRSVFEDNSREEPIRHQRSVGTSARSGRSICT
```

----------
## MEGA
MEGA: Molecular Evolutionary Genetics Analysis software

https://www.megasoftware.net/

Download MEGA X

| OS              |                 | Version         |
|:----------------|:----------------|:----------------|
| Windows / macOS | Graphical (GUI) | MEGA X (64-bit) |

Documentation
[Online Manual](https://www.megasoftware.net/web_help)
First Time User

[walkthrough tutorial](https://www.megasoftware.net/web_help_10/Introduction.htm)
Introduction

- [Mega Basics](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/MEGA_Basics.htm)
  - Opening (activating) a Data File for Analysis | Example 1.2: "Drosophila_Adh.meg" file
- [Aligning Sequences](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Aligning_Sequences.htm)
  - Opening an Alignment | Example 2.1: "hsp20.fas" file
  - Aligning Sequences by ClustalW | Example 2.2: "hsp20.fas" file
  - Aligning Sequences Using Muscle | Example 2.3: "Chloroplast_Martin.meg" file
  - Obtaining Sequence Data from the Internet (GenBank)
- [Estimating Evolutionary Distances](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Estimating_Evolutionary_Distances.htm)
  - Estimating Evolutionary Distances Using Pairwise Distance | Example 3.1: "Drosophila_Adh.meg" file
  - Compute the Proportion of Amino Acid Differences | Example 3.3: "Drosophila_Adh.meg" file
- [Building Trees from Sequence Data](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Building_Trees_From_Sequence_Data.htm)
  - Building a Neighbor-Joining (NJ) Tree | Example 4.1: "Crab_rRNA.meg" file
  - Printing the NJ Tree (For Windows users) | Example 4.2a:   
  - Printing the NJ Tree (For Mac users) | Example 4.2b:
- [Testing Tree Reliability](https://www.megasoftware.net/web_help_10/Part_I_Getting_Started/A_Walk_Through_MEGA/Testing_Tree_Reliability.htm)
  - Bootstrap Testing for a Neighbor-Joining Tree | Example 5.1: "Chloroplast_Martin.meg" file

Site Links
[Videos](https://www.megasoftware.net/videos)
Instructional Videos

- Author: Barry Hall
  - [Choosing and Acquiring Sequences Part 1](https://youtu.be/raaOgtvMJWw) Choosing and Acquiring the Sequences for a Phylogenetic Tree
  - [Choosing and Acquiring Sequences Part 2](https://youtu.be/cVdmH7nNboE) Aligning Coding Sequences
  - [Reconstructing Ancestral Sequences](https://youtu.be/djju9WFMvn0)

### PTME5
Barry G. Hall (2017) Phylogenetic Trees Made Easy: A How-To Manual (5th edition)
- 慶應義塾大学 Keio University https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma990025818970204034
- [Table of Contents](https://global.oup.com/ushe/product/phylogenetic-trees-made-easy-9781605357102?cc=jp&lang=en&#fragment-4)
- [Student Resources](https://learninglink.oup.com/access/hall-5e-student-resources)
Click a link **PTME5e Companion Files** to download the package appropriate to your OS (Linux, Mac, Win).

### R/MEGA

8th Aug, 2017
https://www.researchgate.net/post/Does-anybody-have-a-pipeline-created-or-experience-of-taking-Phylogenetic-trees-from-MEGA-to-Rggtree
Does anybody have a pipeline created or experience of taking Phylogenetic trees from MEGA to R(ggtree)?

https://support.bioconductor.org/p/41863/
Packages reproducing phylogenetic tree from output of MEGA
|
You can save the tree from MEGA in newick format.
APE is an R package that reads newick format and has a lot of options
to
plot phylogenetic trees.

----------
## Chunk options

![https://rmarkdown.rstudio.com/lesson-3.html](https://d33wubrfki0l68.cloudfront.net/4b052d1dc45c9fb6f95caaca375636f792713192/c4043/lesson-images/code-1-options.png)

https://rmarkdown.rstudio.com/lesson-3.html
Chunk Options
- include = FALSE prevents code and results from appearing in the finished file. R Markdown still runs the code in the chunk, and the results can be used by other chunks.
- echo = FALSE prevents code, but not the results from appearing in the finished file. This is a useful way to embed figures.
- message = FALSE prevents messages that are generated by code from appearing in the finished file.

https://r4ds.had.co.nz/
R for Data Science
- https://r4ds.had.co.nz/r-markdown.html
  - https://r4ds.had.co.nz/r-markdown.html#code-chunks
    - https://r4ds.had.co.nz/r-markdown.html#chunk-options

2021/05/15
https://rpubs.com/ktgrstsh/755893
R Markdown 入門 (Tokyo.R #91)
コードチャンク

2017年2月17日
https://kazutan.github.io/kazutanR/Rmd_intro.html
R Markdown入門 | Rチャンク(chunk)の基本 | Rチャンク オプション
- echo(コード部の表示・非表示)
- eval(コード部の評価・非評価)
- include(レポートに組み込むか否か)

----------
## Compile Report

https://rmarkdown.rstudio.com/articles_report_from_r_script.html
Compiling Reports from R Scripts
|
If you are using RStudio then you can also create a report using the Compile Report command (Ctrl+Shift+K).

Jan 17, 2017
https://www.youtube.com/watch?v=4xwaH9CR2TY
How to Compile a Report in RStudio - YouTube

13 April 2020
http://www.dry-lab.org/blog/2020/easy-report-from-r-script.html
An easy way to transform your R script into a nice report – Blog of Andrés Aravena
|
clicking the Compile Report button

![http://www.dry-lab.org/blog/2020/easy-report-from-r-script.html](http://www.dry-lab.org/images/cmb2/R_compile_report.png)

2016年12月05日
https://qiita.com/wakuteka/items/86b0ea5ef8428229babd#3-compile-report
3. Compile Report

![https://qiita.com/wakuteka/items/86b0ea5ef8428229babd](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F12353%2Fdc0b5da6-c3fe-08b0-e0b4-0a8186f6f453.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&w=1400&fit=max&s=8ff668aa377d1baa3b329e36cf09ff30)

https://rpubs.com/kohske/595
Rスクリプトからレポート生成

https://kohske.github.io/R/rstudio/
Rstudioで楽々ドキュメント生成 | Rスクリプトからノートブックの作成

編集画面の[Compile Notebook]というボタンをクリックします。

![https://kohske.github.io/R/rstudio/](https://kohske.github.io/R/rstudio/pics/notebook_compile.png)

2018/05/11
https://www.kyoritsu-pub.co.jp/book/b10003938.html
再現可能性のすゝめ
―RStudioによるデータ解析とレポート作成―
[ためし読み](https://www.yondemill.jp/contents/53229?view=1)
目次 | 4.8　Rスクリプトからレポート生成

![https://www.kyoritsu-pub.co.jp/book/b10003938.html](https://hondana-image.s3.amazonaws.com/book/image/10003938/normal_300fa3ec-db93-4420-a5ce-042046371dc0.jpg)

メディアセンター (https://www.lib.keio.ac.jp/sfc/) よりご利用いただけます。オンライン閲覧の場合、閲覧後は毎回右上の「閲覧終了」ボタンをクリックして、ほかの方に利用をお譲りください。
[Maruzen eBook Library](https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma9926579997904034)

----------

----------
## assignment 1

----------

https://akiyoko.hatenablog.jp/entry/2014/11/07/042801
Windows で R（統計解析ツール）を使う - 
R の使い方を手っ取り早く理解するためにまず、ドットインストールの「R言語入門」（全13回）の動画をひと通り全部見てみました。
動画時間は全部で 35分ほど。
手を動かすのも合わせて、一時間ほどでチェックし終えることができました。

January 2017
https://r4ds.had.co.nz/
R for Data Science

https://www.r-project.org/help.html
R: Getting Help with R

----------

https://support.rstudio.com/hc/en-us/articles/200549016-Customizing-the-RStudio-IDE
Pane Layout

https://r4ds.had.co.nz/workflow-scripts.html
The script editor is a great place to put code you care about. Keep experimenting in the console, but once you have written code that works and does what you want, put it in the script editor.

https://www.uvm.edu/~rsingle/other/R-intro.pdf
Introductory Guide to R
|
1.4 R commands. Case sensitivity.
Technically R is a function language with a very simple syntax. It is case sensitive, so A and a are different variables.
|
2.2 Vectors and Assignments
It is useful to know that R discriminates, for the names of the objects, the upper-case characters from the lower-case
ones (i.e., it is case-sensitive), so that x and X can be used to name distinct objects (even under Windows).
```
a <- 1; A <- 10
ls()
A
a
```

----------
### R_DSD_10

Data Science Dojo [Control Statements: For Loop, If, Else - Introduction to R Programming - Part 10](https://www.youtube.com/watch?v=QEzWBLb9xa4&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=11)

```
> income$average.income
[1]  85000 112000  60000  68000  78000  82000  90000  72000  82000

> income.level
[1] "low-med" "high"    "low-med" "low-med" "low-med" "low-med" "high"    "low-med"
[9] "low-med"
```

The dollar sign `$` is used to specify a single variable (`average.income`) within a data frame (`income`).
`average.income` and `income.level` are variable/object names where lowercase words were separated with `.`.

References:
- https://r4ds.had.co.nz/workflow-basics.html#whats-in-a-name
Object names must start with a letter, and can only contain letters, numbers, `_` and `.`.
- https://www.r-bloggers.com/dataframes-and-the-tidyverse/
To specify a single variable within a data frame or tibble, use the dollar sign `$`. R has another way of doing this, using column numbers, but using the dollar sign will make it much easier to understand your code if someone else needs to use it, or if you come back to look at it months after writing it.

----------
### R_assignOps

[R: Assignment Operators](https://stat.ethz.ch/R-manual/R-devel/library/base/html/assignOps.html)
The operators <- and = assign into the environment in which they are evaluated. The operator <- can be used anywhere, whereas the operator = is only allowed at the top level (e.g., in the complete expression typed at the command prompt) or as one of the subexpressions in a braced list of expressions.

[What are the differences between "=" and "<-" assignment operators in R? - Stack Overflow](https://stackoverflow.com/questions/1741820/what-are-the-differences-between-and-assignment-operators-in-r)

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/28.html
28. 演算子
```
<<-	永続代入
<-，->	代入
=	代入
```

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/32.html
32. ローカル変数と永続代入<<-

----------
### R_built-in

https://www.statmethods.net/management/functions.html
Quick-R: Built-in Functions

https://study.com/academy/lesson/built-in-functions-in-r-programming.html
Built-In Functions in R Programming | Study.com

https://www.javatpoint.com/r-built-in-functions
R Built-in Functions - javatpoint

https://cran.r-project.org/doc/manuals/r-release/R-intro.html#Accessing-builtin-datasets
7.3 Accessing builtin datasets

----------
### R_data.frame

Data Science Dojo [Data Frames - Introduction to R Programming - Part 6](https://www.youtube.com/watch?v=ORbcLfYbvxs&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=6)

2022-03-10
https://cran.r-project.org/doc/manuals/R-lang.html#Data-frame-objects
2.3.2 Data frame objects
|
Data frames are the R structures which most closely mimic the SAS or SPSS data set, i.e. a “cases by variables” matrix of data.
A data frame is a list of vectors, factors, and/or matrices all having the same length (number of rows in the case of matrices). 

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
202 | Chapter 8: A Rapid Introduction to the R Language
|
When accessing a single column from a dataframe, R’s default behavior is to return this as a vector—not a dataframe with one column. Sometimes this can cause problems if downstream code expects to work with a dataframe. To disable this behavior, we set the argument drop to FALSE in the bracket operator:
```
> d[, "start", drop=FALSE]
```

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
216 ■ 8 章 R 言語入門
|
データフレームから単一の列にアクセスするとき、R のデフォルトの動作は、これを 1 つの列を持つ データフレームとしてではなく、ベクトルとして返す。次に実行されるコードがデータフレームを入力 として期待している場合は問題となる。この動作を無効にするには、ブラケット演算子を使って引数 drop を FALSE に設定する。
```
> d[, "start", drop=FALSE]
```

2020/03/21
https://www.cyberer.net/2020/03/r-lists-and-data-frames.html#toc_headline_8
CYBERer.NET: R - 入門本編 6章 リストとデータフレーム
|
「データフレーム」は関係データベースのテーブルのようなデータ構造だ。クラス data.frame を持つリストであるが、ただのリストに比べてコンポーネントになり得るオブジェクトにいくつかの制限が設けられている。

----------
### R_factor

Data Science Dojo [Using Factors - Introduction to R Programming - Part 8](https://www.youtube.com/watch?v=a_N6Q0O5T3s&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=8)

http://www.okadajp.org/RWiki/?因子Tips大全

https://r4ds.had.co.nz/data-import.html#readr-factors
11.3.3 Factors
|
R uses factors to represent categorical variables that have a known set of possible values. 

https://r4ds.had.co.nz/factors.html
15 Factors
|
In R, factors are used to work with categorical variables, variables that have a fixed and known set of possible values. They are also useful when you want to display character vectors in a non-alphabetical order.
Historically, factors were much easier to work with than characters. As a result, many of the functions in base R automatically convert characters to factors. 

https://r4ds.had.co.nz/vectors.html#factors-1
20.7.1 Factors
|
Factors are designed to represent categorical data that can take a fixed set of possible values. Factors are built on top of integers, and have a levels attribute:

http://monashbioinformaticsplatform.github.io/2015-09-28-rbioinformatics-intro-r/01-supp-factors.html
Factors are used to represent categorical data. Factors can be ordered or unordered and are an important class for statistical analysis and for plotting.
Factors are stored as integers, and have labels associated with these unique integers. While factors look (and often behave) like character vectors, they are actually integers under the hood, and you need to be careful when treating them like strings.

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 191
|
Factors and classes in R
|
Another kind of vector you’ll encounter are factors. Factors store categorical variables, such as a treatment group (e.g., “high,” “medium,” “low,” “control”), strand (forward or reverse), or chromosome (“chr1,” “chr2,” etc.).

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 205
|
8.2.3.2 R の因子とクラス 
|
他にも作業中に出会う可能性のあるベクトルに因子がある。因子はカテゴリーを表す変数を収めたベクトルである。たとえば処理群(「高」、「中」、「低」、「対照」など)、鎖(「正鎖」または「相補鎖」)、あるいは染色体(「chr1」、「chr2」など)である。

https://www.cyberer.net/2020/08/r-ordered-and-unordered-factors.html
CYBERer.NET: R - 入門本編 4章 順序付き因子と順序無し因子
|
因子 (factor) は、質的変数を R で表現する方法である。質的変数には、順序尺度と名義尺度があるが、R ではそれぞれに対して順序付き因子と順序無し因子が対応する。因子ではない数値ベクトルは、量的変数 (間隔尺度や比例尺度) とみなされる。R では順序無し因子、順序付き因子、因子ではない数値ベクトルは、モデル構築において異なる取り扱い (各尺度として適切な取り扱い) がされるようになっている。

2020-04-24
https://stat.ethz.ch/pipermail/r-announce/2020/000653.html
R 4.0.0 is released

https://stat.ethz.ch/R-manual/R-devel/doc/html/NEWS.html
CHANGES IN R 4.0.0
|
R now uses a ‘⁠stringsAsFactors = FALSE⁠’ default, and hence by default no longer converts strings to factors in calls to data.frame() and read.table().

----------
### R_indexing

https://cran.r-project.org/doc/manuals/R-lang.html#Indexing
3.4 Indexing
|
R contains several constructs which allow access to individual elements or subsets through indexing operations. 

http://www.intro2r.info/unit2/subsetting-and-indexing.html
Subsetting and Indexing
|
Subsetting in R is fast and incredibly powerful.
There are three subsetting operators: [, [[, $.

une 27th, 2020
https://www.datacamp.com/community/tutorials/subsets-in-r
R Subsetting: How to Subset & Select DataFrame Rows & Columns in R - DataCamp

https://www.r-bloggers.com/2017/02/dataframes-and-the-tidyverse/
To specify a single variable within a data frame or tibble, use the dollar sign $. R has another way of doing this, using column numbers, but using the dollar sign will make it much easier to understand your code if someone else needs to use it, or if you come back to look at it months after writing it.

https://r4ds.had.co.nz/transform.html#select
5 Data transformation
|
5.4 Select columns with select()

https://r4ds.had.co.nz/tibbles.html#subsetting
10 Tibbles
|
10.3.2 Subsetting
|
So far all the tools you’ve learned have worked with complete data frames. If you want to pull out a single variable, you need some new tools, $ and [[. [[ can extract by name or position; $ only extracts by name but is a little less typing.

2013-11-19
https://stats.idre.ucla.edu/r/modules/subsetting-data/
Subsetting Data | R Learning Modules

https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/installr.html#a-brief-introduction-to-r
index

----------
### R_list

http://www.okadajp.org/RWiki/?リストTips大全

https://r4ds.had.co.nz/vectors.html#vector-basics
There are two types of vectors:

1. Atomic vectors, of which there are six types: logical, integer, double, character, complex, and raw. Integer and double vectors are collectively known as numeric vectors.

2. Lists, which are sometimes called recursive vectors because lists can contain other lists.

The chief difference between atomic vectors and lists is that atomic vectors are homogeneous, while lists can be heterogeneous.

https://jennybc.github.io/purrr-tutorial/bk00_vectors-and-lists.html
A list is actually still a vector in R, but it’s not an atomic vector.

2018年4月16日
https://blog.sgnet.co.jp/2018/04/r-vectorlist.html
[R] vectorとlistの関係
|
ただし、ただ"vector"と言った場合は"atomic vector"、"list"と言った場合は"generic vector"を指しているみたい。

2012-09-21
http://takenaka-akio.org/doc/r_auto/list.html
リストにオブジェクトをしまう
|
ベクトルは、同じ型のデータをまとめて並べたデータ構造です。 これに対し、リストはどのような型のデータでもしまえるデータ構造です。 ベクトルでもリスト自身でもデータフレームでも統計解析関数が返す複雑なオブジェクトでも、なんでも格納できます。 自動化した処理の結果をいくつもまとめておいて、最後にまとめて処理したいなどという場合にも便利でしょう。 なお、データフレームもリストの一種です。
リストの要素の指定
リストの要素は、[　] や [[ ]] に要素の位置を与えて指定できます。 [　]を使った場合は「指定した要素を含むリスト」、 [[ ]]を使った場合は「要素そのもの」を指すことに注意が必要です。
[　] や [[ ]]、$ による要素の指定方法は、 データフレームの場合と同様ですね。 これはデータフレーム自体がリスト（の一種）なので当然です（ is.list(data.frame()) は TRUE を返す）。

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/23.html
23. リスト
|
R にはデータの種類としてベクトルや行列，配列などが用意されている（ 1 や 'a' も長さ 1 のベクトル）が，リストはこれら異なる構造のデータを集めて 1 個のオブジェクトにしたものである．異なった型のベクトルを 1 個のリストにまとめてもよいし，リストの要素としてリストを用いても構わない．
```
コマンド	機能
x[1]	x の第 1 成分を取り出す（中身はリスト）
x[[1]]	x の第 1 成分を取り出す（中身はリスト中の要素）
```
 リスト要素へのアクセス
上記のように，[[ と ]] の間に要素の番号を指定することによって，リストの要素を取り出すことが出来る．[ と ] の間に要素の番号を指定することでもリストの要素を取り出すことは出来るが，この場合はベクトルとしてアクセスを行っていることになる．よって，要素を取り出したいのではなくてリストの一部分を抽出する場合は，ベクトルの場合と同様，[ と ] を使えばよい．ただし返り値はリストとなる．

----------
### R_matrix

2023-08-24
https://homerhanumat.github.io/r-notes/matrix-indexing.html
7.2 Matrix Indexing
|
We use the sub-setting operator `[` to pick out parts of a matrix. For example, in order to get the element in the second row and third column of `numbersMat`, ask for:
```
numbersMat[2,3]
```

2019.06.15
https://stats.biopapyrus.jp/r/basic/matrix.html
行列 | R による行列の演算
|
行列から要素を取り出すとき、角括弧を利用して、行数と列数を指定して行う。
```
x <- matrix(c(1:16), nrow = 4, ncol = 4)
x
x[3, 2]
```

----------
### R_object

[A brief introduction to R](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/installr.html#a-brief-introduction-to-r)
All variables (scalars, vectors, matrices, etc.) created by R are called objects.

[05. オブジェクトと代入（付値）](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/05.html)
R が作ったり操作した実体はオブジェクト（object）と呼ばれる．変数，数の配列，文字列関数，データ，関数その他全てがそれにあたる．

----------
### R_operator

https://cran.r-project.org/doc/manuals/R-lang.html#Operators
3.1.4 Operators

https://www.ucl.ac.uk/~uctqiax/PUBLG100/2015/faq/operators.html
Operators in R | Introduction to Quantitative Methods

|Operator|Description|
|:---------|:---------|
|( )|Round brackets (also known as "parenthesis") are used primarily when calling a function in R.|
|[ ]|The square brackets are used for indexing into a vector, matrix, array, list or dataframe.|

https://www.statmethods.net/management/operators.html
Quick-R: Operators
|
Arithmetic Operators
|
Logical Operators
```
# An example
x <- c(1:10)
x[(x>8) | (x<5)]
```

https://stat.ethz.ch/R-manual/R-devel/library/base/html/Logic.html
Logical Operators


http://cse.naro.affrc.go.jp/takezawa/r-tips/r/28.html
28. 演算子
|
演算子一覧
|
$ と [[ ]] は主にリストの要素にアクセスする場合（例：mylist$element , mylist[[1]] ）に用いられ，[ ] は主にベクトルの要素にアクセスする場合（例 ： x[2] ）に用いられる．

|演算子|機能|
|:---------|:---------|
|$|リストの要素にアクセスする場合|
|[ ，[[|データの一部分，要素，（ [ → ベクトルの要素にアクセス，[[  → リストの要素にアクセス）|


http://cse.naro.affrc.go.jp/takezawa/r-tips/r/42.html
42. データへのアクセス方法
|
このデータフレーム x にアクセスする方法を紹介する．

|コマンド|機能|
|:---------|:---------|
|x$列名，x["列名"]，x[["列名"]]|列データ（例えば SEX や WEIGHT ）にアクセスする．|

----------
### R_options

https://stat.ethz.ch/R-manual/R-devel/library/base/html/options.html
R: Options Settings

https://www.burns-stat.com/the-options-mechanism-in-r/
The digits option controls how many digits are printed (by default):
The default value is 7.  We can change it:

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 179
|
Significant Digits, print(), and Options in R
|
By default, R will print seven significant digits

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 193
|
有効桁、print()、R のオプション
|
デフォルトでは、R は 7 桁の有効桁を表示する

```
sqrt(3.5)
print(sqrt(3.5), digits=10)
getOption('digits')
options(digits=9)
help(options)
```

----------
### R_plot

https://dotinstall.com/lessons/basic_r/28113
#13 グラフを描いてみよう | R言語入門 - プログラミングならドットインストール

R-Tips [67. 相関係数と無相関検定](http://cse.naro.affrc.go.jp/takezawa/r-tips/r/67.html)
```
 cor(x, y, method="spearman")          # 単なる相関係数
 cor.test(x, y, method="pearson")      # 無相関かどうかの検定
```

----------
### R_quit

奥村 晴彦
Last modified: 2019-04-22 14:21:33
https://oku.edu.mie-u.ac.jp/~okumura/stat/first.html
Rの初歩
|
終了のしかた
|
終了するには，［閉じる］ボタンをクリックします。または，Rのコンソールに
`> q()`
と打ち込むのが伝統的な方法です。q はquit（終わる）の頭文字です。すると，標準的な設定では，
`作業スペースを保存しますか？`
または
`Save workspace image? [y/n/c]:`
と聞いてきますので，作業スペース（現在の状態）を保存して終了するなら y（はい），保存しないで終了するなら n（いいえ），終了をキャンセルする（終了しない）なら c（キャンセル）と答えます。通常は n（いいえ）と答えます。

----------
### R_quotes

https://stat.ethz.ch/R-manual/R-devel/library/base/html/Quotes.html
Single and double quotes delimit character constants. They can be used interchangeably but double quotes are preferred (and character constants are printed using double quotes), so single quotes are normally only used to delimit character constants containing double quotes.

https://stackoverflow.com/questions/20572436/are-double-and-single-quotes-always-interchangeable-in-r
Are double "" and single '' quotes (always) interchangeable in R? - Stack Overflow

----------
### R_read.table

https://stat.ethz.ch/R-manual/R-devel/library/utils/html/read.table.html
Data Input

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
Working with and Visualizing Data in R | 195
|
Large Genomics Data into R: colClasses, Compression, and More
|
data.table package
fread() function

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.3 R でのデータの扱いとその可視化 ■ 209
|
大規模なゲノムデータを R に読み込む: colClasses とデータ圧縮
|
data.table パッケージ
fread() 関数

```
> d <- read.csv("Dataset_S1.txt")
```

https://heavywatal.github.io/rstats/readr.html
readr: 高速で柔軟なテーブル読み込み - Heavy Watal

2020.02.01
https://stats.biopapyrus.jp/r/tidyverse/readr.html
readr | readr パッケージによるデータの読み込みと書き出し、文字列パース


Data Science Dojo [Read and Write Data - Introduction to R Programming - Part 5](https://www.youtube.com/watch?v=vbVRhr8qexQ&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=6)
https://youtu.be/vbVRhr8qexQ?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&t=105

https://r4ds.had.co.nz/workflow-projects.html#paths-and-directories
8.3 Paths and directories
|
Paths and directories are a little complicated because there are two basic styles of paths: Mac/Linux and Windows.

https://so-zou.jp/robot/tech/numerical-analysis/r/file/#no3
パスの区切り
```
Windowsではパスの区切りにバックスラッシュ (\) を用いますが、それをそのまま文字定数に含めると

> a <-read.table("dir\sample.txt")
エラー:  ""dir\s" で始まる文字列の中で '\s' は文字列で認識されないエスケープです

のようなエラーとなります。よってバックスラッシュをバックスラッシュでエスケープして (\\) と記述するか、スラッシュ (/) に置き換えます。
```

2018/09/28
https://opur.club/post/2018/09/28/about-paths/
Path（パス）
|
Mac や Linux と共通の表記になりますので，スラッシュを使用することを推奨します。
```
C:/Users/username/Documents/rclub.R
```


https://darumalab.github.io/bootcamp/2017-07-14-import/
R言語 データの読み込み- R Importing Data
|
日本語のファイルを読み込む時にエラーが発生する場合
```
dat1 <- read.table(file = file.choose(), header = TRUE, sep = ",", 
    fileEncoding = "CP932")
```

2021-01-25
[第23章 Rのエンコーディング問題 | Rで計量政治学入門](https://shohei-doi.github.io/quant_polisci/encoding-r.html)
23.1 なぜ文字化けが起こるのか
|
23.1.1 エンコーディング
|
実用上、日本語で文字化けが起こる問題の大半は
WindowsではShift-JISあるいはCP932で、
LinuxやMacなどのUNIX系ではUTF-8で
エンコーディングしていることに起因しています。

2018-01-25 [RでCSVファイルの入出力（CP932文字コード指定など） | kitamix](https://kitamix.net/archives/save-cdv-file-in-r/1096)

2015-08-23
[文字化けこわい、こわくない？ - cucumber flesh](https://uribo.hatenablog.com/entry/2015/08/23/004222)
日本語エンコーディング表形式のファイル
|
WindowsとMac（UNIX）でエンコードが異なるので注意が必要。大抵の場合、ファイルの出処がWindowsならcp932（いわゆるSJIS）、MacならUTF8を引数fileEncodingで指定すれば大丈夫。

----------
### R_typeof

[R Language Definition](https://cran.r-project.org/doc/manuals/R-lang.html#Objects)
2 Objects
|
R objects are often coerced to different types during computations. There are also many functions available to perform explicit coercion.

[Data Types and Structures – Programming with R](https://swcarpentry.github.io/r-novice-inflammation/13-supp-data-structures/)


https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 191
|
Type Coercion in R
|
Because all elements in a vector must have homogeneous data type, R will silently coerce elements so that they have the same type.

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 205
|
R における型の強制変換
|
ベクトルのすべての要素は均一のデータ型でなければならないため、R は同じ型を持つよ うに要素の型変換を強制する。

[R の強制型変換と NA の取り扱い - 株式会社ホクソエムのブログ](https://blog.hoxo-m.com/entry/2017/04/24/000000)
強制型変換
R のベクトルは、1つだけしか型を持つことができません。1
したがって、異なる型の要素を結合してベクトルを作成しようとすると、型を統一するために、型の自動変換が行われます。これが強制型変換です。
強制型変換にはルールがあります。結合しようとする要素の型の中で、最も柔軟性の高い型に変換されます。
型の柔軟性は次の通りです。
```
logical < integer < double < complex < character
(論理値型 < 整数型 < 倍精度小数点型 < 複素数型 < 文字列型)
```

----------
### R_vector

Data Science Dojo [Working with Vectors - Introduction to R Programming - Part 7](https://www.youtube.com/watch?v=h6Mrzjrkycs&list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx&index=7)

https://r4ds.had.co.nz/vectors.html
20 Vectors | R for Data Science

https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/188bto4/alma99218100004031
Bioinformatics data skills
|
R Language Basics | 189
|
Vector types
|
R’s vectors must contain elements of the same type.
Numeric
Integer
Character
Logical
|
Table 8-3. R’s vector types

https://www.oreilly.co.jp/books/9784873118635/
バイオインフォマティクスデータスキル
|
8.2 R 言語の基礎 ■ 203
|
8.2.3.1 ベクトル型
|
R のベクトルは同じ型の要素だけが含まれていなければならない。
|
実数型(Numeric)
整数型(Integer)
文字型(Character)
論理型(Logical)
|
表 8-3 R のベクトル型

2017.06.13
https://stats.biopapyrus.jp/r/basic/vector.html
ベクトル | R のベクトル操作と演算
|
R のベクトルは、数学のベクトルとほぼ同じ概念である。数学では 1 つのベクトルに複数の要素を含めると同様に、R では 1 つのベクトルに複数の値を代入できる。

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/16.html
16. 種々のベクトル
|
論理型ベクトル
|
論理値を要素とするベクトルを論理型ベクトルと呼ぶ．正式名（TRUE，FALSE）でも略記名（T，F）でも指定できる．論理型ベクトルに対する論理演算子として，& (論理積) ， | (論理和) ，! (否定) ，xor (排他的論理和) があり，これらを用いると要素毎の演算を行なう．

http://cse.naro.affrc.go.jp/takezawa/r-tips/r/14.html
14. ベクトル計算
|
ベクトルを集合と見立てて集合演算を行うことも出来る．
```
union(x, y)	和集合
intersect(x, y)	積集合
setdiff(x, y)	差集合
```

----------
## GenomeBento

- http://wiki.lifesciencedb.jp/mw/GenomeBentoProject
- https://github.com/ktym/GenomeBento/

![http://togotv.dbcls.jp/togopic.2013.18.html](https://dbarchive.biosciencedbc.jp/data/togo-pic/image/201306_genome_bento.png)

----------
## Evolution

- [Endosymbiotic evolution and the tree of genomes](https://www.nature.com/scitable/content/endosymbiotic-evolution-and-the-tree-of-genomes-14665098/)
- [Smith DR, Keeling PJ. Mitochondrial and plastid genome architecture: Reoccurring themes, but significant differences at the extremes. Proc Natl Acad Sci U S A. 2015 Aug 18;112(33):10177-84.](https://pmc.ncbi.nlm.nih.gov/articles/PMC4547224/) | Nucleotide Composition. | Genome Size.

![https://www.nature.com/scitable/content/endosymbiotic-evolution-and-the-tree-of-genomes-14665098/](https://www.nature.com/scitable/content/ne0000/ne0000/ne0000/ne0000/14665098/U1.cp2.3_nrg1271-i2.jpg)

----------

## Genome signature
**ゲノムの特徴**

- [Coutinho TJ et al. (2015) "Homology-independent metrics for comparative genomics."](https://www.ncbi.nlm.nih.gov/pubmed/26029354)
- [Dutta C, Paul S. (2012) "Microbial lifestyle and genome signatures."](https://www.ncbi.nlm.nih.gov/pubmed/23024607)
- [g-language documents](https://github.com/gaou/g-language/wiki/Documents) | 
[Nucleotide composition analysis](https://github.com/gaou/g-language/wiki/restgenomeanalysisenglish#nucleotide-composition-analysis) | 
[塩基組成の解析](https://github.com/gaou/g-language/wiki/restgenomeanalysisjapanese#塩基組成の解析)
- http://bioinfo.ie.niigata-u.ac.jp/?ゲノムサインとその生物学的な意味の解明

**細菌とアーキアにおけるゲノムサイズとGC含量**  
**Genome Size and GC Content in Bacteria and Archaea**  

- [Martinez-Gutierrez et al. PLoS Genet. 2022 May 23;18(5):e1010220. "Genome size distributions in bacteria and archaea are strongly linked to evolutionary history at broad phylogenetic scales"](https://pubmed.ncbi.nlm.nih.gov/35605022/)
- [Westoby et al. Ecol Evol. 2021 Mar 16;11(9):3956-3976. "Cell size, genome size, and maximum growth rate are near-independent dimensions of ecological variation across bacteria and archaea"](https://pubmed.ncbi.nlm.nih.gov/33976787/)
- [Almpanis A et al.  Microb Genom. 2018 Apr;4(4). "Correlation between bacterial G+C content, genome size and the G+C content of associated plasmids and bacteriophages."](https://www.ncbi.nlm.nih.gov/pubmed/29633935)
- [Bohlin J et al. Environ Microbiol Rep. 2014 Jun;6(3):278-86. "Positive correlations between genomic %AT and genome size within strains of bacterial species."](https://pubmed.ncbi.nlm.nih.gov/24983532/) | [Wiley Online Library Open Access](https://search.lib.keio.ac.jp/permalink/81SOKEI_KEIO/uccs31/cdi_proquest_miscellaneous_1542648747)
- [McCutcheon JP et al. PLoS Genet. 2009 Jul;5(7):e1000565. "Origin of an alternative genetic code in the extremely small and GC-rich genome of a bacterial symbiont."](https://www.ncbi.nlm.nih.gov/pubmed/19609354)
- [Nakabachi A et al. Science. 2006 Oct 13;314(5797):267. "The 160-kilobase genome of the bacterial endosymbiont Carsonella."](https://pubmed.ncbi.nlm.nih.gov/17038615/)
![](https://www.science.org/cms/10.1126/science.1134196/asset/63cc1e1c-b0ae-457c-ab79-0c368942ab7e/assets/graphic/314_267_f1.jpeg)

[Relationship between genome size and GC content for sequenced Bacterial and Archaeal genomes.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2704378/figure/pgen-1000565-g001/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/core/lw/2.0/html/tileshop_pmc/tileshop_pmc_inline.html?title=Click%20on%20image%20to%20zoom&p=PMC3&id=2704378_pgen.1000565.g001.jpg" width=50%>

**至適増殖温度とアミノ酸・コドン使用**  
**Optimal Growth Temperature and Amino Acid and Codon Usage**  

- [Zeldovich et al. PLoS Comput Biol. 2007 Jan 12;3(1):e5. "Protein and DNA sequence determinants of thermophilic adaptation"](https://pmc.ncbi.nlm.nih.gov/articles/PMC1769408/)

[Correlation between the Sum F of Fractions of Ile, Val, Tyr, Trp, Arg, Glu, and Leu (IVYWREL) Amino Acids in 86 Proteomes and the OGT of Organisms T opt](https://pmc.ncbi.nlm.nih.gov/articles/PMC1769408/figure/pcbi-0030005-g001/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/core/lw/2.0/html/tileshop_pmc/tileshop_pmc_inline.html?title=Click%20on%20image%20to%20zoom&p=PMC3&id=1782037_pcbi.0030005.g001.jpg" width=50%>

- [Lynn et al. Nucleic Acids Res. 2002 Oct 1;30(19):4272-7. "Synonymous codon usage is subject to selection in thermophilic bacteria"](https://pmc.ncbi.nlm.nih.gov/articles/PMC140546/)

[Variation in codon usage within and between genomes.](https://pmc.ncbi.nlm.nih.gov/articles/PMC140546/figure/gkf546f2/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/core/lw/2.0/html/tileshop_pmc/tileshop_pmc_inline.html?title=Click%20on%20image%20to%20zoom&p=PMC3&id=140546_gkf546f2.jpg" width=50%>

**好塩菌と非好塩菌のアミノ酸使用**  
**Amino Acid Usage in Halophiles Halophiles and Non-Halophiles**  

- [Paul et al. (2008) Genome Biol. "Molecular signature of hypersaline adaptation: insights from genome and proteome composition of halophilic prokaryotes"](https://pmc.ncbi.nlm.nih.gov/articles/PMC2643941/)

Figure 1 [Grouping of halophiles and non-halophiles according to their standardized amino acid usage.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2643941/figure/F1/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/core/lw/2.0/html/tileshop_pmc/tileshop_pmc_inline.html?title=Click%20on%20image%20to%20zoom&p=PMC3&id=2643941_gb-2008-9-4-r70-1.jpg" width=50%>

**ウイルスと宿主のアミノ酸・コドン使用**  
**Amino Acid and Codon Usage in Viruses and Hosts**  

- [Bahir et al. (2009) "Viral adaptation to host: a proteome-based analysis of codon usage and amino acid preferences"](https://pmc.ncbi.nlm.nih.gov/articles/PMC2779085/)

Figure 3 [Amino acid distribution and codon usage in viruses infecting taxonomy-unified hosts. ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2779085/figure/f3/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/core/lw/2.0/html/tileshop_pmc/tileshop_pmc_inline.html?title=Click%20on%20image%20to%20zoom&p=PMC3&id=2779085_msb200971-f3.jpg" width=50%>

Figure 6 [Similarity in GC content and codon usage between pairs of viruses and hosts.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2779085/figure/f6/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/core/lw/2.0/html/tileshop_pmc/tileshop_pmc_inline.html?title=Click%20on%20image%20to%20zoom&p=PMC3&id=2779085_msb200971-f6.jpg" width=50%>

**プラスミドと宿主染色体のGC含量**  
**GC Content of Plasmids and Host Chromosomes**  

- [Yano et al. (2019) "Reconsidering plasmid maintenance factors for computational plasmid design"](https://www.sciencedirect.com/science/article/pii/S2001037018301685)

Fig. 5. [Plot of G + C contents of 209 plasmids and their host chromosomes.](https://www.sciencedirect.com/science/article/pii/S2001037018301685#f0025)
 The G + C contents of plasmids tend to be lower than (and are correlated with) those of the host chromosomes.

![](https://ars.els-cdn.com/content/image/1-s2.0-S2001037018301685-gr5.jpg)

**コドン使用に基づく高発現遺伝子の予測**  
**Predicting Highly Expressed Genes Based on Codon Usage**  

- [Karlin et al. (2001) J Bacteriol "Characterizations of Highly Expressed Genes of Four Fast-Growing Bacteria"](https://pubmed.ncbi.nlm.nih.gov/11489855/)

FIG. 1 [Genes of ≥100 codons in the four fast-growing bacteria. Each gene is represented by a single point. Its position is determined by its bias relative to all genes B(g|C) and by its bias relative to the RP genes B(g|RP).](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC95378/figure/F1/)

<img alt="" src="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC95378/bin/jb1710100001.jpg" width=50%>

**GC含量、連続塩基組成、アミノ酸・コドン使用に基づく外来性遺伝子クラスターの検出**  
**Detecting Exogenous Gene Clusters Based on GC Content, Oligonucleotide Composition, and Amino Acid and Codon Usage**  

- [Karlin S (2001) Trends Microbiol. "Detecting anomalous gene clusters and pathogenicity islands in diverse bacterial genomes."](https://www.ncbi.nlm.nih.gov/pubmed/11435108) | [pdf](https://eclass.uoa.gr/modules/document/file.php/D473/Βιβλιογραφία/DNA%20Composition/Karlin_2001.pdf)

Fig. 1. [The contrasts are displayed for 20 and 50 kb sliding window plots of G+C content, genomic signature profiles, codon usage biases and amino acid anomalies for eight different bacterial species.](https://www.sciencedirect.com/science/article/pii/S0966842X01020790#FIG1)

![](https://ars.els-cdn.com/content/image/1-s2.0-S0966842X01020790-gr1.jpg)

----------

https://github.com/haruosuz/codon/blob/master/README.md#temperature

https://github.com/haruosuz/mgsa/blob/master/references/mgsa.tools.md#growth-rate

----------


