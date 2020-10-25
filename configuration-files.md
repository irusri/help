# Configuration files

There are two configuration file associated with GenIE-Sys. One file for storing the database information \(`geniesys/plugins/settings.php`\) and other one  \(`geniesys/plugins/config.json`\)for storing the sequence files and blast indices.

Here is the brief explanation to the`geniesys/plugins/settings.php`file that we use with GenIE-Sys.

```text
/*Define your base url with trailing slash*/
$GLOBALS["base_url"]='http://localhost:[port number]/geniesys/';

OR

$GLOBALS["base_url"]='http://localhost:[port number]';
```

Here is the example of`geniesys/plugins/settings.php`file that we use with GenIE-Sys.

```text
global $db_species_array;
$db_species_array=array($db_name=>"species 1"); 


/*Here you can listed background colors correspond to each species. */
global $db_species_color_array;
$db_species_color_array=array("new_database"=>"#86c0a6");

/*You dont need to change anything here*/
$db_key_array=array_keys($db_species_array);
$db_values_array=array_values($db_species_array);

if(isset($_COOKIE['genie_select_species'])) {
    $selected_database=$_COOKIE['genie_select_species'];
} else {
    $selected_database=$db_key_array[0];
	$_COOKIE['genie_select_species']=$db_key_array[0];
}

/*Please state the mysql username and password for above databases. It's important to grant only SELECT permissio to all the tables except defaultgenebaskets and genebasket tables*/
global $db_url;
$db_url=  array ('genelist'=>'mysqli://geniecmsuser:geniepass@localhost/'.$selected_database);

/*Define your base url with trailing slash*/
$GLOBALS["base_url"]='http://localhost:'.$_SERVER['SERVER_PORT'].'/geniesys/';

//Settings SQL modes here, allows for disabling the default STRICT_TRANS_TABLES  which prevents PHP from inserting '' in auto_increment fields.
$db_settings['modes'] = "ONLY_FULL_GROUP_BY,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION";

```

Here is the brief explanation to the`geniesys/plugins/config.json`file that we use with GenIE-Sys.

```text
	"datasets":[
		{
			"number": 1,
			"group_name": " Group name",
			"dataset_path":"Path to the BLAST database",
			"molecule_type":"This could be either nucleotide or protein",
			"user_friendly_name":"Friendly username shows to the user"
		}
		]
		
		
```

Here is the example of`geniesys/plugins/config.json`file that we use with GenIE-Sys.

```text

	"selection_box":[{"height":420,"width":400}],	 
	"datasets":[
		{
			"number": 1,
			"group_name": "Genomes",
			"dataset_path":"data/blast/genome",
			"molecule_type":"nucleotide",
			"user_friendly_name":"Arabidopsis thaliana Genomes"
		},{
			"number": 2,
			"group_name": "Transcripts",
			"dataset_path":"data/blast/transcript",
			"molecule_type":"nucleotide",
			"user_friendly_name":"Arabidopsis thaliana Transcripts"
		},{
			"number": 3,
			"group_name": "CDS",
			"dataset_path":"/data/blast/cds",
			"molecule_type":"nucleotide",
			"user_friendly_name":"Arabidopsis thaliana CDS"
		},{
			"number": 4,
			"group_name": "Protein",
			"dataset_path":"data/blast/protein",
			"molecule_type":"protein",
			"user_friendly_name":"Arabidopsis thaliana protein"
		}
	],
	"default_jbrowse_dataset_directory":"Fptr"
	} 
```

