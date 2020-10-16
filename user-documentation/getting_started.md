
Getting Started
=============

------------
Overview of GenIE-Sys
------------

The Genome Integrative Explorer System (GenIE-Sys) is dedicative in-house system to facilitate external groups in setting up their own web resource for searching, visualizing, editing, sharing and reproducing their genomic and transcriptomic data while using project raw data( ```GFF3,FASTA,FASTQ ```) as an input.

**GenIE-Sys has its basic content stored in text files. MySQL database server is required to load the genomic data and integrate with GenIE-Sys plugins.**

GenIE-Sys will support cutting-edge genomic science, providing easily accessible, reproducible, and shareable science. The increasingly large size of many datasets is a particularly challenging aspect of current and future genomics based research; it is often difficult to move large datasets between servers due to constraints of time and finance. It is also important to keep the experimental datasets private among the group members until the project goals are accomplished or until after publication. In other words, it must provide a high level of security to ensure that the genomic web resource remains private without requiring the moving of data to unknown remote servers. Therefore, a locally hosted GenIE-Sys installation represents a more secure, less expensive and time consuming resource to implement.

In Addition, Researchers who are not specialized in bioinformatics or have limited computers skills are not currently able to gain maximal insight from the biological data typically produced by genomics projects. In order to overcome this limitation, GenIE-Sys will provide an ideal gateway with simple graphical user interfaces to those who have limited skills in bioinformatics.

Web resources such as <a target="_blank" href="http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3245001/">Phytozome(Goodst et al., 2012) </a>, <a target="_blank"  href="http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3355756/">iPlant( Goff. et al.,2011)</a>, <a  target="_blank" href="https://academic.oup.com/nar/article/31/1/224/2401365/The-Arabidopsis-Information-Resource-TAIR-a-model">TAIR (Rhee et al., 2003)</a> and <a target="_blank"  href="http://www.plantphysiol.org/content/158/2/590">PLAZA (Proost et al., 2011)</a>. These collections of tools and services have been sources of inspiration to be and have contributed my desire to develop the GenIE-Sys as well as, and importantly, developing an understanding of their limitations to end users. None of these resources allow users to easily setup their own web resource without submitting their data to the resource developers and making them publicly available.


------------------
Requirements
------------------

**We recommended using Firefox or Google Chrome web browsers for testing of the GenIE-Sys. Please do not use Microsoft Edge or Internet Explorer.**

To run GenIE-Sys we recommend your host supports the following

* PHP version 5.4+
* MySQL version 5.6+ or MariaDB version 10.0+

To fulfil the above requirements, we have tested the GenIE-Sys under the following infrastructures.
* MAMP/LAMP
* Apache, PHP and MySQL standalone servers
* Docker (recommended for development purpose)


