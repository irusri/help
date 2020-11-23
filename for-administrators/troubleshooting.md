# Troubleshooting

GenIE-Sys can easily be installed without an effort. Unfortunately, there is always space for problems due to multiple server setups and PHP versions. In this section, we try to answer the most frequent issues in order to install GenIE-Sys as effortless as possible. Please send us an email if you still get trouble with installation or updates: `contact@geniesys.org`

### Running from Command Line

If you want to use PHP’s built-in server \(**not recommended**\), just use the following lines to install GenIE-Sys. This is only for the initial test installation, in order to make a fully functional website you have to install Webserver packages such as MAMP or LAMP.

```text
git clone --recursive https://github.com/irusri/geniesys.git
cd geniesys
php -S localhost:3000
```

You should now be able to access GenIE-Sys at: `http://localhost:3000` in your browser.

### Sub-folder permissions

The Webserver runs in a different group than your user account on most servers. Following subfolder permissions will necessary to grant write access from GenIE-Sys.:

```text
chgrp -R www-data geniesys
chmod -R 775 geniesys/genie_files
```

Please make sure that the root folder is also readable by the webserver.

### Broken subpages

Whenever you have problems\(can not open or a server error\) with subpages, you can try the following steps.

* Make sure that the .htaccess file is present inside GenIE-Sys folder.
* mod\_rewrite should be enabled on your server.
* You need to check the .htaccess. You can test this by adding some extra characters into your .htaccess. If this cause an “Internal Server Error”, the file gets loaded. Otherwise, you need to enable AllowOverride all in your Web server configuration file. An example of `GenIE-Sys/.htaccess` the file is shown below.

```text
RedirectMatch 403 ^.*/genie_files/
ErrorDocument 403 &nbsp;
RewriteEngine on
Options -Indexes
ServerSignature Off
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond $1#%{REQUEST_URI} ([^#]*)#(.*)\1$
RewriteRule ^([^\.]+)$ %2?page=$1 [QSA,L]
ErrorDocument 404 /notfound.html
```

Please make sure that you are using PHP 5.4 or higher.

### Example input files

`head input/example.gff3`

```text
Potra000001	leafV2	gene	9066	10255	.	-	.	ID=Potra000001g00001;Name=Potra000001g00001;potri=Potri.004G180000,Potri.004G180200
Potra000001	leafV2	mRNA	9066	10255	.	-	.	ID=Potra000001g00001.1;Parent=Potra000001g00001;Name=Potra000001g00001;cdsMD5=71c5f03f2dd2ad2e0e00b15ebe21b14c;primary=TRUE
Potra000001	leafV2	three_prime_UTR	9066	9291	.	-	.	ID=Potra000001g00001.1.3pUTR1;Parent=Potra000001g00001.1;Name=Potra000001g00001.1
Potra000001	leafV2	exon	9066	9845	.	-	.	ID=Potra000001g00001.1.exon2;Parent=Potra000001g00001.1;Name=Potra000001g00001.1
Potra000001	leafV2	CDS	9292	9845	.	-	2	ID=Potra000001g00001.1.cds2;Parent=Potra000001g00001.1;Name=Potra000001g00001.1
Potra000001	leafV2	CDS	10113	10236	.	-	0	ID=Potra000001g00001.1.cds1;Parent=Potra000001g00001.1;Name=Potra000001g00001.1
Potra000001	leafV2	exon	10113	10255	.	-	.	ID=Potra000001g00001.1.exon1;Parent=Potra000001g00001.1;Name=Potra000001g00001.1
Potra000001	leafV2	five_prime_UTR	10237	10255	.	-	.	ID=Potra000001g00001.1.5pUTR1;Parent=Potra000001g00001.1;Name=Potra000001g00001.1
Potra000001	leafV2	gene	13567	14931	.	+	.	ID=Potra000001g00002;Name=Potra000001g00002;potri=Potri.004G179800,Potri.004G179900,Potri.004G180100
Potra000001	leafV2	mRNA	13567	14931	.	+	.	ID=Potra000001g00002.1;Parent=Potra000001g00002;Name=Potra000001g00002;cdsMD5=df49ed7856591c4a62d602fef61c7e37;primary=TRUE
```

`head annotation_file.txt`

```text
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
```

### Updates

**Manual updates**

GenIE-Sys can be updated manually using the latest ZIP file from [GitHub](https://github.com/irusri/geniesys/archive/master.zip). Please backup your older version of `geniesys/plugins/settings.php` and `geniesys/genie_files` before you do the latest update. First, unzip the genie.zip file from your download folder and move into the Web Server server. Finally copy the `geniesys/plugins/settings.php` and `geniesys/genie_files` into the latest version of GenIE-Sys.

**Updates using Git**

Here is the easy way to update GenIE-Sys using git submodules:

```text
cd geniesys
git checkout master
git pull
git submodule foreach --recursive git checkout master
git submodule foreach --recursive git pull
```

### Browse extentions

There are  some browser extentions which can cause problems to the GenIE-Sys and plugins. We suggest you to test the GenIE-Sys with private mode browser \(incognito mode\) without any extentions or plugins installed.

### **Enable read/write for MySQL installed via MAMP \(on Mac\):**

1. open "MAMP" use spotlight
2. click "Stop Servers"
3. edit ~/.my.cnf \(using vi or your favourite editor\) and add the following lines:

   $ vi ~/.my.cnf

> ```text
> [mysqld_safe]
> [mysqld]
> secure_file_priv="/Users/username/"
> ```

1. click "Start Servers" \(in MAMP window\)

### More problems?

Please contact us:`contact@geniecms.org`

