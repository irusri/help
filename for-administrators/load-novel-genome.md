# Load novel genome

We can install novel genome to GenIE-Sys using either Graphical User Interface \(GUI\) or Command Line Interface \(CLI\).

{% tabs %}
{% tab title="Using Graphical User Interface \(GUI\)" %}
Once you have placed all the required files into the data folder according the previous section. You will be able to see the annotation tab similar to the following screenshot.

![Annotation tab in the admin panel of the GenIE-Sys website](../.gitbook/assets/screenshot-2020-10-26-at-14.51.16.png)

If you miss some of the files described in the previous section, you will be able to see the tab similar to the following screenshot.

![](../.gitbook/assets/screenshot-2020-10-26-at-14.48.09.png)

Please make sure to upload the correct files and in format into the data folder. Once you have uploaded all required files, now it's time to parse them into the suitable formats right before loading into the database.

\*\*\*\*



\*\*\*\*
{% endtab %}

{% tab title="Using Command Line Interface \(CLI\) " %}
Creating a new database using CMD

Due to the increasing number of species in PlantGenIE we use a standard naming convention to easily identify and maintain the databases. For example: `[website name]_[species name]_[version number]`

[![https://github.com/irusri/geniesys/blob/master/docs/images/genie\_databases.png?raw=true](https://github.com/irusri/geniesys/blob/master/docs/images/genie_databases.png?raw=true)](https://raw.githubusercontent.com/irusri/geniesys/master/docs/images/genie_databases.png)

Log into the MySQL server and create a database.

```text
#Create a database:
CREATE DATABASE new_database;
```

You can download the empty database [here](https://raw.githubusercontent.com/irusri/scripts/master/dump.sql). Then load the database into the newly created database using the following commands.

```text
git show HEAD~1:scripts/dump.sql > dump.sql
mysql -u newuser -p newpassword new_database < dump.sql
```

Log into the MySQL server to create user and grant permissions.

```text
#Create MySQL user:
CREATE USER newuser@'localhost' IDENTIFIED BY 'newpassword';

#User permissions:
GRANT SELECT ON new_database.* TO newuser@'localhost';
GRANT INSERT,UPDATE,DELETE ON new_database.genebaskets TO newuser@'localhost';
GRANT INSERT,UPDATE,DELETE ON new_database.defaultgenebaskets TO newuser@'localhost';
```

`newuser, newpassword and new_database` should be included in the plugins/settings.php similar to following example.

```text
//Define the databasename names
$db_species_array=array("new_database"=>"new genome",...
//Define the databasename and background colours
$db_species_color_array=array("new_database"=>"#86c0a6",....
//Define the username, password and host here
$db_url=  array ('genelist'=>'mysqli://newuser:newpassword@localhost/'.$selected_database); 
//Define the base url with trailing slash
$GLOBALS["base_url"]='http://localhost:3000/';
```

\*\*\*\*
{% endtab %}
{% endtabs %}



### 

