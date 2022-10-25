[生命動態のデータサイエンス / DATA SCIENCE FOR GENOME DYNAMICS](https://sol.sfc.keio.ac.jp/courses/4061)

----------

# Case Study
**ケーススタディ**

## Table of Contents
- [assignment 0](#assignment-0) 選抜課題
- [assignment 1](#assignment-1) 課題1 「Introduction to R」
- [assignment 2](#assignment-2) 課題2 「Installing R packages」
- [assignment 3](#assignment-3) 課題3 「DNA Sequence Statistics (1)」
- [assignment 4](#assignment-4) 課題4 「DNA Sequence Statistics (2)」
- [assignment 5](#assignment-5) 課題5 「Dotplot」
- [assignment 6](#assignment-6) 課題6 「Pairwise Sequence Alignment」
- [assignment 7](#assignment-7) 課題7 「Interim report」
- [assignment 8](#assignment-8) 課題8 「Guest speaker (1)」
- [assignment 9](#assignment-9) 課題9 「Guest speaker (2)」
- [assignment 10](#assignment-10) 課題10 「Choosing and Acquiring Sequences」
- [assignment 11](#assignment-11) 課題11 「Multiple Alignment and Phylogenetic trees」
- [assignment 12](#assignment-12) 課題12 「Draft report」
- [assignment 13](#assignment-13) 課題13 「Final report」

----------
## assignment 0
**選抜課題**

本授業で解析したい興味あるオブジェクト（DNA、タンパク質、その他のテキスト配列など）を述べてください。課題のタイトルと参考文献も明記してください。

Please describe objects (DNA, protein, and other textual sequences, etc.) you're interested in. Please also state your project title and references.

----------
## assignment 1
**課題1 「Introduction to R」**

**my_datasciencedojo_r.R**

Watch the following videos and write your comments or questions.
- [Introduction to R Programming - Data Science Dojo](https://www.youtube.com/playlist?list=PL8eNk_zTBST8j2BU5HYFQogdCjtrHyQAx)

[Example answer]
```
I watched the videos Part 2 to Part 11 of "Introduction to R Programming".
My questions are as follows:
1. What is the difference between Data Frames and Lists in R?
2. What is the difference between factor and character vectors?
```

----------
### R_built-in

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_built-in

----------
### R_factor

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_factor

----------
### R_indexing

https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#r_indexing

----------
## assignment 2
**課題2 「Installing R packages」**

[Installing R packages](https://github.com/haruosuz/r4bioinfo/blob/master/R_Avril_Coghlan/README.md#installing-r-packages)

**my_setup_packages.R**

回答例:  
```
# Example answer:  

> # Print the versions of these packages:
> packageVersion("tidyverse")
[1] ‘1.3.1’
> packageVersion("seqinr")
[1] ‘4.2.8’
> packageVersion("zoo")
[1] ‘1.8.9’
> packageVersion("ape")
[1] ‘5.5’
> packageVersion("phangorn")
[1] ‘2.7.1’
> packageVersion("phytools")
[1] ‘0.7.90’
> packageVersion("ggseqlogo")
[1] ‘0.1’
> packageVersion("microseq")
[1] ‘2.1.4’
> 
> packageVersion("Biostrings")
[1] ‘2.58.0’
> packageVersion("msa")
[1] ‘1.22.0’
> packageVersion("DECIPHER")
[1] ‘2.18.1’
> packageVersion("ggtree")
[1] ‘2.4.2’

> # Print the version of R running:        
> R.version.string
[1] "R version 4.0.5 (2021-03-31)"
> 
> # Print version information about R, the OS and attached or loaded packages.
> sessionInfo()
R version 4.0.5 (2021-03-31)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Big Sur 10.16

```

----------
## assignment 3
**課題3 「DNA Sequence Statistics (1)」**

**my_assignment_chapter1_dna1.R**

----------
## assignment 4
**課題4 「DNA Sequence Statistics (2)」**

**my_assignment_chapter2_dna2.R**

----------
## assignment 5
**課題5 「Dotplot」**

**my_assignment_chapter4_align_dotplot.R**

----------
## assignment 6
**課題6 「Pairwise Sequence Alignment」**

**my_assignment_chapter4_align_pairwise.R**

----------
## assignment 7
**課題7 「Interim report」**

これまでの課題を選択・結合・編集して中間報告書を作成する。  
Select, combine, and edit the previous assignments to create an interim report.  

**my_interim_report.R**

----------
## assignment 8
**課題8 「Guest speaker (1)」**

What are the advantages or disadvantages of suffix arrays compared to hash tables?

----------
## assignment 9
**課題9 「Guest speaker (2)」**

You saw an application of pairwise DNA-protein alignment to differential gene expression analysis. 
Another interesting application of DNA-protein alignment is in analyzing data from metagenomic studies. 
Sequenced reads obtained from a metagenomic sampling are often aligned against protein databases (e.g. SwissProt) for functional profiling of the sample.

Suppose the sequence below is one such read in fasta format (in a typical experiment, there are 100s of millions of reads). 
obtained from a soil sample.
```
>sample
CATGCTGCAGGTTCTTACGGCATCCGCGTTCGCCTTCAGCCACGGGCTAA
CGACATAGCGAATGCCATCGGGCCGTTTGCCGCGATTATCGATATTCTCG
CAACGGGGCAAATCAA
```
1. Use an alignment tool of your choice to align these reads to the SwissProt database. (one easy/quick option is to use the online version of blastx)
2. What result did you get? 
3. What other alignment tools are there that allow nucleotide-protein alignment?

----------
## assignment 10
**課題10 「Choosing and Acquiring Sequences」**

Use [BLAST (Basic Local Alignment Search Tool)](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#blast) to identify and acquire multiple (>3) homologous sequences that are to be included on phylogenetic trees.

Submit database accessions or a multi-FASTA file (a text file containing multiple sequences in FASTA format) in [SOL](https://sol.sfc.keio.ac.jp/).

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip
**my_ds4gd_tree.R**

Edit the following R code (`database` `ACCESSIONs`):
```
database <- "ncbi_protein"
  ACCESSIONs <- c("NP_001393", "WP_011012522", "WP_001040724", "NP_001952", "WP_011013157", "NP_387993")
```
or
```
database <- "uniprot"
  ACCESSIONs <- c("P68104", "Q8U152", "P33166", "P13639", "P61877", "P80868")
```

Running the script **my_ds4gd_tree.R** will generate the following output files.
- myAA.fasta: unaligned sequences
- myAlign.fasta: aligned sequences
- myAlignTrim.fasta: trimmed aligned sequences

----------
## assignment 11
**課題11 「Multiple Alignment and Phylogenetic trees」**

次のURLからRスクリプトをダウンロードする。  
Download the R script from the following URL.  
https://github.com/haruosuz/DS4GD/raw/master/2021giga/scripts_ds4gd.zip
**my_assignment_chapter5_msa_tree.R**

RStudioでRスクリプトを開く。**Compile Report**コマンドでPDFまたはHTML形式のレポートを作成する。そのレポートを課題として提出する。  
Open an R script in RStudio. Create report in PDF or HTML format using the **Compile Report** command. Submit the report as your assignment.  

[**Compile Report**](https://github.com/haruosuz/DS4GD/blob/master/2020/CaseStudy.md#compile-report)

----------
## assignment 12
**課題12 「Draft report」**

Submit a draft report to be used for the final presentation.

----------
## assignment 13
**課題13 「Final report」**

Update the draft report based on the questions and comments at the final presentation, and submit it as a final report.

----------





