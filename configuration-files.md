# Configuration files

There are two configuration file associated with GenIE-Sys. One file for storing the database information \(`geniesys/plugins/settings.php`\) and other one  \(`geniesys/plugins/config.json`\)for storing the sequence files and blast indices.

`geniesys/plugins/settings.php`

```text
/*Define your base url with trailing slash*/
$GLOBALS["base_url"]='http://localhost:[port number]/geniesys/';

OR

$GLOBALS["base_url"]='http://localhost:[port number]';
```

`geniesys/plugins/config.json`

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

