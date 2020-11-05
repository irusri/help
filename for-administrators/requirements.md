# Requirements

{% hint style="success" %}
**We recommended using Firefox or Google Chrome web browsers for the testing of the GenIE-Sys. Please do not use Microsoft Edge or Internet Explorer.**
{% endhint %}

{% hint style="warning" %}
You do not need to install any of the software packages listed below when you use the Docker-based installation for the GenIE-Sys. This is only relevant for standalone Apache-based installation approach. 
{% endhint %}

User should know how to open the terminal and installation of Docker software.

Dokcer  
Git

To run GenIE-Sys we recommend your host supports the following

* PHP version 5.2+
* MySQL version 5.6+ or MariaDB version 10.0+

To fulfil the above requirements, we have tested the GenIE-Sys under the following infrastructures.

* MAMP/LAMP
* Apache, PHP and MySQL standalone servers

#### BLAST

Here are the required Perl packages for BLAST plugin. Manual installation of these plugins needed only when you use the MAMP based installation.

```text

# verison of the Perl
Perl v5.2 or higher is needed

# required packages
               Bio::Coordinate     *   "VERSION: 1.007001"
                Bio::FeatureIO     *   "VERSION: 1.6.905"
       Bio::SearchIO::blastxml     *   "VERSION: 1.70"
                           DBI     *   "VERSION: 1.643"
                       GD::SVG     *   "VERSION: 0.33"
```

You can use the following command to test the version of the Perl and the installed packages.

```text
$perl -h
$for M in `perldoc -t perllocal|grep Module |sed -e 's/^.*" //'`; do V=`perldoc -t perllocal|awk "/$M/{y=1;next}y" |grep VERSION |head -n 1`; printf "%30s %s\n" "$M" "$V"; done |sort
```



