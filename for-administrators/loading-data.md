---
description: >-
  We have PlantGenIE core species as dummy data for testing GenIE-Sys. If you
  use dummy data you do not need to upload new files into data directory.
---

# Loading dummy data

Once you logged in to the GenIE-Sys web interface there is a tab called Database settings where we can find a tab similar to the following screenshot.

![Database settings tab ](../.gitbook/assets/screenshot-2020-10-26-at-14.12.26.png)

When you did the GenIE-Sys installation using Docker image, the defaults username and password for MySQL server will be. 

username : admin  
password: mypass \(You can change this password using `docker-compose.yml file.`\)

When you did your installation using MAMP server, their default username and password for MySQL server will be.

username: root  
password: root  
  
Now you can create a empty database or create a clone from core species databases. There is also link to view the database in more detail using PHPMyAdmin.

If you wish to load novel genome using different set of FASTA and  GFF3 files other than the core species, you need to place the required files into the data folder describe in the next section of this documentation.  


