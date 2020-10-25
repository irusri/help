# Input files

All the input files such as FASTA, GFF3 and TSV files should be placed inside the data directory.

```text
$ls data
gene.gff3
genome.fa
cds.fa
transcript.fa
protein.fa
```

Here are some of the guidelines for prepare initial input files. 

1.\) GFF3 files should follow the standard GFF3 specification for [Generic Feature Format Version 3 \(GFF3\)](https://github.com/The-Sequence-Ontology/Specifications/blob/master/gff3.md). Here is the example of GFF3 file that can be included inside the data file.

```text
data $head gene.gff3 
##gff-version 3
Chr1    phytozome9_0    gene    3631    5899    .       +       .       ID=AT1G01010;Name=AT1G01010
Chr1    phytozome9_0    mRNA    3631    5899    .       +       .       ID=PAC:19656964;Name=AT1G01010.1;pacid=19656964;longest=1;Parent=AT1G01010
Chr1    phytozome9_0    exon    3631    3913    .       +       .       ID=PAC:19656964.exon.1;Parent=PAC:19656964;pacid=19656964
Chr1    phytozome9_0    five_prime_UTR  3631    3759    .       +       .       ID=PAC:19656964.five_prime_UTR.1;Parent=PAC:19656964;pacid=19656964
Chr1    phytozome9_0    CDS     3760    3913    .       +       0       ID=PAC:19656964.CDS.1;Parent=PAC:19656964;pacid=19656964
Chr1    phytozome9_0    exon    3996    4276    .       +       .       ID=PAC:19656964.exon.2;Parent=PAC:19656964;pacid=19656964
Chr1    phytozome9_0    CDS     3996    4276    .       +       2       ID=PAC:19656964.CDS.2;Parent=PAC:19656964;pacid=19656964
Chr1    phytozome9_0    exon    4486    4605    .       +       .       ID=PAC:19656964.exon.3;Parent=PAC:19656964;pacid=19656964
Chr1    phytozome9_0    CDS     4486    4605    .       +       0       ID=PAC:19656964.CDS.3;Parent=PAC:19656964;pacid=19656964
```

2.\) FASTA file should follow the standard FASTA format preferably a clear sequence ID without special characters. Here is en example of FASTA file.

```text
data $head genome.fa 
>Chr1 CHROMOSOME dumped from ADB: Feb/3/09 16:9; last updated: 2007-12-20
CCCTAAACCCTAAACCCTAAACCCTAAACCTCTGAATCCTTAATCCCTAAATCCCTAAATCTTTAAATCCTACATCCAT
GAATCCCTAAATACCTAATTCCCTAAACCCGAAACCGGTTTCTCTGGTTGAAAATCATTGTGTATATAATGATAATTTT
ATCGTTTTTATGTAATTGCTTATTGTTGTGTGTAGATTTTTTAAAAATATCATTTGAGGTCAATACAAATCCTATTTCT
TGTGGTTTTCTTTCCTTCACTTAGCTATGGATGGTTTATCTTCATTTGTTATATTGGATACAAGCTTTGCTACGATCTA
CATTTGGGAATGTGAGTCTCTTATTGTAACCTTAGGGTTGGTTTATCTCAAGAATCTTATTAATTGTTTGGACTGTTTA
TGTTTGGACATTTATTGTCATTCTTACTCCTTTGTGGAAATGTTTGTTCTATCAATTTATCTTTTGTGGGAAAATTATT
TAGTTGTAGGGATGAAGTCTTTCTTCGTTGTTGTTACGCTTGTCATCTCATCTCTCAATGATATGGGATGGTCCTTTAG
CATTTATTCTGAAGTTCTTCTGCTTGATGATTTTATCCTTAGCCAAAAGGATTGGTGGTTTGAAGACACATCATATCAA
AAAAGCTATCGCCTCGACGATGCTCTATTTCTATCCTTGTAGCACACATTTTGGCACTCAAAAAAGTATTTTTAGATGT
```

3.\) gene description or transcript description should be tab delimited file. First column is the gene or transcript ID and the second column should be the description. The file should be named as gene\_description.tsv or transcript\_description.tsv. Here is  an example of description file.

```text

```

4.\) There are other types of annotation can be loaded into GenIE-Sys website. For example if you have kegg, pfam or go annotation. you can make them as tab delimited file followed by gene ID. These files should be names as gene\_kegg.tsv, gene\_go.tsv and gene\_pfam.tsv.  Here are some of the common example of annotation files.

5.\) There is a space for loading best blast IDs into GenIE-Sys website. As an example if you have best BLAST hits from model plant species that can be loaded into the database. These files should be named as gene\_artha.tsv or gene\_potri\_tsv. Here are some example of best blast annotation files.


