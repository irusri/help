# Requirements

#### BLAST

Here are the required Perl packages for BLAST plugin.

```text
This is perl 5, version 26, subversion 1 (v5.26.1) or higher

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



