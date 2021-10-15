# Input files

All the input files such as `FASTA`, `Generic Feature Format Version 3 (GFF3) `and `Tab-separated values (TSV)` files should be placed inside the data directory which is inside the geniesys folder. GFF3 and FASTA files are required to setup the database and other files are recommended but not mandatory.

`ls geniesys/data`

```
gene.gff3
genome.fa
cds.fa
transcript.fa
protein.fa
```

**Here are some of the guidelines for prepare initial input files. **

1.) `GFF3` files should follow the standard `GFF3` specifications listed [here](https://github.com/The-Sequence-Ontology/Specifications/blob/master/gff3.md). Here is the example of a `GFF3` file that can be included inside the data file.

`head gene.gff3`

```
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

2.) FASTA files should follow the standard FASTA format preferably a clear sequence ID without special characters. Here is an example of a FASTA file.\
\
`head genome.fa`

```
>Chr1 
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

3.) gene description or transcript description should be tab delimited file. First column is the gene ID for the `gene_description.tsv`  file and the transcript ID for the `transcript_description.tsv` file and the second column should be the description for gene or transcript respectively. The file should be named as `gene_description.tsv` or`transcript_description.tsv.` Following you can find an example of a description file.

`head gene_description.tsv`

```
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
```

`head transcript_description.tsv`

```

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

4.) `GO`, `Kegg` and `Pfam` annotation can be loaded into the GenIE-Sys website. You can make them as tab delimited files. The first column should be the gene ID and the second column should be the `GO`, `Kegg` or `Pfam` . ID and description separated by the hypen (**-**). If there are several descriptions associated with one gene id, you can use the semicolon (**;**) to separate the corresponding annotation ID and Description (`ID1-Description1;ID2-Description2`). These files should be named as `gene_kegg.tsv`, `gene_go.tsv` and `gene_pfam.tsv`. Here are some of the examples of annotation files.

`head gene_go.tsv`

```
AT1G06190	GO:0006353-transcription termination, DNA-dependent
AT1G06620	GO:0055114-oxidation-reduction process;GO:0016491-oxidoreductase activity
AT2G46660	GO:0055114-oxidation-reduction process;GO:0020037-heme binding;GO:0016705-oxidoreductase activity, acting on paired donors, with incorporation or reduction of molecular oxygen;GO:0005506-iron ion binding
AT5G02290	GO:0006468-protein phosphorylation;GO:0004672-protein kinase activity
AT3G21700	GO:0007264-small GTPase mediated signal transduction;GO:0005525-GTP binding
AT2G16040	GO:0046983-protein dimerization activity
AT3G58440	GO:0005515-protein binding
AT5G44790	GO:0046872-metal ion binding;GO:0030001-metal ion transport;GO:0000166-nucleotide binding
AT2G34630	GO:0008299-isoprenoid biosynthetic process
```

`head gene_kegg.tsv`

```

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
```

`head gene_pfam.tsv`

```
AT1G06620	PF14226-non-haem dioxygenase in morphine synthesis N-terminal;PF03171-2OG-Fe(II) oxygenase superfamily
AT3G27910	PF01344-Kelch motif
AT2G34630	PF00348-Polyprenyl synthetase
AT2G03270	PF13245-Part of AAA domain;PF13087-AAA domain
AT2G25590	PF05641-Agenet domain
AT5G25130	PF00067-Cytochrome P450
AT2G32280	PF06749-Protein of unknown function (DUF1218)
```

5.) There is a space for loading best blast IDs into GenIE-Sys website. As an example if you have best BLAST hits from model plant species that can be loaded into the database. These files should be named as `gene_arabidopsis.tsv, gene_spruce.tsv` or `gene_populus_tsv.` Here are some examples of the best blast annotation files.

`head gene_populus.tsv`

```
AT4G38320	Potri.014G006000;Potra003982g23967
AT4G25700	Potri.017G145700;Potra000924g07477
AT4G11300	Potri.003G132100;Potra000613g04660
AT5G61090	Potri.014G040100;Potra003452g21711
AT3G26570	Potri.008G186601;Potra002618g19588
AT3G13950	Potri.006G223800;Potra001531g12715
AT3G12170	Potri.006G056400;Potra002594g19498
AT5G43175	Potri.002G119200;Potra002863g20178
```

`head gene_spruce.tsv`

```
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

[Here](ftp://plantgenie.org/Data/GenIESys/input_files/) you can find some of the examples of input files that we can use to generate GenIE-Sys website for PLantGenIE core species (_Populus tremula, Populus trichocarpa, Picea abies, Eucalyptus grandis and Arabidopsis thaliana_).

```
ftp://plantgenie.org/Data/GenIESys/input_files/
```

Following shows the example of expression file format we use is the geniesys.

```
gene_id	sample_name	dataset	expression
Potra2c499s35830	Female mature leaf (Genotype 202)	sex	11.485859
Potra2c499s35830	Male mature leaf (Genotype 207)	sex	38.15796
Potra2c499s35830	Female mature leaf (Genotype 213.1)	sex	5.70359
Potra2c499s35830	Male mature leaf (Genotype 221)	sex	27.727529
Potra2c499s35830	Female mature leaf (Genotype 226.1)	sex	4.554956
Potra2c499s35830	Male mature leaf (Genotype 229.1)	sex	8.86191
Potra2c499s35830	Male mature leaf (Genotype 229)	sex	9.736108
Potra2c499s35830	Male mature leaf (Genotype 235)	sex	9.915396
Potra2c499s35830	Female mature leaf (Genotype 236)	sex	0
Potra2c499s35830	Female mature leaf (Genotype 239)	sex	11.865896
Potra2c499s35830	Female mature leaf (Genotype 244)	sex	15.638645
Potra2c499s35830	Male mature leaf (Genotype 303)	sex	5.584787
```

Following shows the example of network file format we use is the geniesys.

```
dataset	source	target	type	irp_score	nc_score	nc_sdev
aspleaf	Potra2c499s35830	Potra2n10c20315	Directed	0.286377	0.638776	0.431892
aspleaf	Potra2c499s35830	Potra2n10c20477	Directed	0.267369	0.619623	0.467934
aspleaf	Potra2c499s35830	Potra2n14c27073	Directed	0.261255	0.646634	0.44341
aspleaf	Potra2c499s35830	Potra2n15c28503	Directed	0.235742	0.628397	0.488165
aspleaf	Potra2c499s35830	Potra2n15c28913	Directed	0.246521	0.681161	0.416157
aspleaf	Potra2c499s35830	Potra2n16c29690	Directed	0.200386	0.647241	0.50554
aspleaf	Potra2c499s35830	Potra2n18c32618	Directed	0.261308	0.66005	0.428262
aspleaf	Potra2c499s35830	Potra2n19c33381	Directed	0.453916	0.798063	0.200826
aspleaf	Potra2c499s35830	Potra2n1c1338	Directed	0.275956	0.674358	0.400909
aspleaf	Potra2c499s35830	Potra2n1c1722	Directed	0.239664	0.645548	0.464229
```
