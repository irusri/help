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
#head transcript_description.tsv
Potra000001g00001.1	Germin-like protein subfamily 1 member
Potra000001g00002.1	Germin-like protein
Potra000002g00003.1	uncharacterized protein LOC105113244
Potra000002g35060.1	Pyruvate, phosphate dikinase regulatory
Potra000002g00005.3	Gibberellin 2-beta-dioxygenase
Potra000002g00005.2	Gibberellin 2-beta-dioxygenase
Potra000002g00005.1	Gibberellin 2-beta-dioxygenase
Potra000002g00005.5	Gibberellin 2-beta-dioxygenase
Potra000002g00005.4	Gibberellin 2-beta-dioxygenase
Potra000002g00006.5	DnaJ homolog subfamily

#head gene_description.tsv
Potra000001g00001	Germin-like protein subfamily 1 member
Potra000001g00002	Germin-like protein
Potra000002g00003	uncharacterized protein LOC105113244
Potra000002g35060	Pyruvate, phosphate dikinase regulatory
Potra000002g00005	Gibberellin 2-beta-dioxygenase
Potra000002g00006	DnaJ homolog subfamily
Potra000002g00007	Tyrosyl-DNA phosphodiesterase
Potra000002g31575	uncharacterized protein LOC105115090
Potra000002g31576	conserved unknown protein
Potra000002g31577	conserved unknown protein
```

4.\) There are other types of annotation can be loaded into GenIE-Sys website. For example if you have kegg, pfam or go annotation. you can make them as tab delimited file followed by gene ID. These files should be names as gene\_kegg.tsv, gene\_go.tsv and gene\_pfam.tsv.  Here are some of the common example of annotation files.

5.\) There is a space for loading best blast IDs into GenIE-Sys website. As an example if you have best BLAST hits from model plant species that can be loaded into the database. These files should be named as gene\_artha.tsv or gene\_potri\_tsv. Here are some example of best blast annotation files.

6.\) experiment.tsv

```text
experiment_id	experiment_name	experiment_value	experiment_table	visibility	default selection	tool_category
1	All Affymetrics	affymetrics	expression	false	1	expression
2	AspWood	aspwood	expression	true	0	expression
3	P. tremula exatlas	exatlas	expression	true	0	expression
4	Robinson et al 2014 (Sex)	sex	expression	true	0	expression
5	P. trichocarpa Tissues	log	expression	false	0	expression
6	AspLeaf	aspleaf	network	true	1	network
7	AspWood	aspwood	network	true	0	network
8	exAtlas	exatlas	network	true	0	network
9	AspMetaNet	full	network	true	0	network
10	SwAsp population (buds)	swasp	expression	true	0	expression
11	AspLeaf	leaf_development	expression	true	0	expression
12	Xylem and Leaf	xylem_leaf	expression	true	0	expression
13	Senescence 1	senescence1	expression	false	0	expression
14	Senescence 2	senescence2	expression	true	0	expression
```

Here you can find some of the examples of input files that we used with core species.





