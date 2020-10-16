# BLAST

**Overview**

The BLAST \(Basic Local Alignment Search Tool\) tool compares input sequences with datasource to identify homologous sequence matches.

**Basic Usage**

Paste your sequence \(with or without a FASTA header\) into the query input text box. Transcript sequence can be extracted by type in a gene ID into the Load example text box or upload a sequence file \(Less than 100 MB\)with the upload file function. Then click and select the desired dataset from the lists of available BLAST databases and click the BLAST! Button at the bottom of the page.

BLAST plugin uses standard default NCBI BLAST options. However users can change the following advanced options:

| **Option**         | **Description** |
| :--- | :--- |
| Scoring matrix | Substitution matrix that determines the cost of each possible residue mismatch between query and target sequence. See BLAST [substitution matrices](http://www.ncbi.nlm.nih.gov/blast/html/sub_matrix.html) for more information. |
| Filtering | Whether to remove low complexity regions from the query sequence. |
| E-value cutoff | The maximum expectation value of retained alignments. |
| Query genetic code | Genetic code to be used in blastx translation of the query. |
| DB genetic code | Genetic code to be used in blastx translation of the datasets. |
| Frame shift penalty | Out-of-frame gapping \(blastx, tblastn only\) \[Integer\] default = 0. |
| Number of results | The maximum number of results to return. |

  
**BLAST results**

BLAST Results page will be automatically reloaded until the search results are successfully retrieved. BLAST results are organized into a table containing Query ID, Hit ID, Average bit score \(top\), Average e-value \(lowest\), Average identity \(av. similarity\) and Links. Clickable BLAST results display the corresponding region of identified homology within the JBrowse tool, where the matching region is shown.

**Implementation**

BLAST search tool is implemented using NCBI Blast \(v2.2.26\) and a backend PostgresSQL Chado database. We use PHP, JavaScript, XSL, Perl and d3js, Drupal libraries to improve Open Source GMOD Bioinformatic Software Bench server to provide a graphical user interface.

