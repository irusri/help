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
#head gene_description.tsv
AT3G11260	WUSCHEL related homeobox 5
AT3G09140	hypothetical protein (DUF674)
AT5G01070	RING/FYVE/PHD zinc finger superfamily protein
AT3G18110	Pentatricopeptide repeat (PPR) superfamily protein
ATMG00560	Nucleic acid-binding, OB-fold-like protein
AT3G04800	translocase inner membrane subunit 23-3
AT5G63380	AMP-dependent synthetase and ligase family protein
AT1G04105	hypothetical protein
AT1G09815	polymerase delta 4
AT4G01690	Flavin containing amine oxidoreductase family
AT3G23490	cyanase

#head transcript_description.tsv
AT3G11260.1	WUSCHEL related homeobox 5
AT3G09140.2	hypothetical protein (DUF674)
AT5G01070.1	RING/FYVE/PHD zinc finger superfamily protein
AT3G18110.1	Pentatricopeptide repeat (PPR) superfamily protein
ATMG00560.1	Nucleic acid-binding, OB-fold-like protein
AT3G04800.1	translocase inner membrane subunit 23-3
AT5G63380.1	AMP-dependent synthetase and ligase family protein
AT1G04105.1	hypothetical protein
AT1G09815.1	polymerase delta 4
AT4G01690.1	Flavin containing amine oxidoreductase family
```

4.\) There are other types of annotation can be loaded into GenIE-Sys website. For example if you have kegg, pfam or go annotation. you can make them as tab delimited file followed by gene ID. These files should be names as gene\_kegg.tsv, gene\_go.tsv and gene\_pfam.tsv.  Here are some of the common example of annotation files.

```text
#head gene_go.tsv
AT1G06190	GO:0006353-transcription termination, DNA-dependent
AT1G06620	GO:0055114-oxidation-reduction process;GO:0016491-oxidoreductase activity
AT2G46660	GO:0055114-oxidation-reduction process;GO:0020037-heme binding;GO:0016705-oxidoreductase activity, acting on paired donors, with incorporation or reduction of molecular oxygen;GO:0005506-iron ion binding
AT5G02290	GO:0006468-protein phosphorylation;GO:0004672-protein kinase activity
AT3G21700	GO:0007264-small GTPase mediated signal transduction;GO:0005525-GTP binding
AT2G16040	GO:0046983-protein dimerization activity
AT3G58440	GO:0005515-protein binding
AT5G44790	GO:0046872-metal ion binding;GO:0030001-metal ion transport;GO:0000166-nucleotide binding
AT2G34630	GO:0008299-isoprenoid biosynthetic process

#head gene_kegg.tsv
AT1G06620	-
AT3G27910	-
AT4G22890	-
AT5G54067	-
AT2G34630	2.5.1.85-All-trans-nonaprenyl-diphosphate synthase (geranylgeranyl-diphosphate specific).;2.5.1.1-Dimethylallyltranstransferase.
AT2G03270	3.6.4.13-RNA helicase.;3.6.4.12-DNA helicase.
AT2G25590	-
AT1G43171	-
AT5G25130	-
AT2G32280	-
AT3G15020	1.1.1.37-Malate dehydrogenase.

#head gene_pfam.tsv
AT1G06620	PF14226-non-haem dioxygenase in morphine synthesis N-terminal;PF03171-2OG-Fe(II) oxygenase superfamily
AT3G27910	PF01344-Kelch motif
AT2G34630	PF00348-Polyprenyl synthetase
AT2G03270	PF13245-Part of AAA domain;PF13087-AAA domain
AT2G25590	PF05641-Agenet domain
AT5G25130	PF00067-Cytochrome P450
AT2G32280	PF06749-Protein of unknown function (DUF1218)
```

5.\) There is a space for loading best blast IDs into GenIE-Sys website. As an example if you have best BLAST hits from model plant species that can be loaded into the database. These files should be named as gene\_artha.tsv or gene\_potri\_tsv. Here are some example of best blast annotation files.

```text
#head gene_populus.tsv
AT4G38320	Potri.014G006000;Potra003982g23967
AT4G25700	Potri.017G145700;Potra000924g07477
AT4G11300	Potri.003G132100;Potra000613g04660
AT5G61090	Potri.014G040100;Potra003452g21711
AT3G26570	Potri.008G186601;Potra002618g19588
AT3G13950	Potri.006G223800;Potra001531g12715
AT3G12170	Potri.006G056400;Potra002594g19498
AT5G43175	Potri.002G119200;Potra002863g20178

#head gene_spruce.tsv
AT1G01010	MA_10426365g0010
AT1G01030	MA_18923g0010
AT1G01040	MA_10437243g0020
AT1G01050	MA_93206g0010
AT1G01060	MA_11267g0020
AT1G01070	MA_13078g0020
AT1G01080	MA_482994g0010
AT1G01090	MA_10426096g0010
AT1G01100	MA_10430200g0010
```

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





