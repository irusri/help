
------------------------
Install with MAMP/XAMPP 
------------------------

  
Most Mac users will probably try GenIE-Sys with MAMP/LAMP.  

[![](https://github.com/irusri/geniesys/blob/master/docs/images/mamp.png?raw=true )](http://www.mamp.info/en/downloads/)

Installing MAMP is just a matter of downloading the app from the MAMP website and running the installer. It will install a MAMP app in your Applications folder.

[![](https://github.com/irusri/geniesys/blob/master/docs/images/mamp-02.png?raw=true)](http://www.mamp.info/en/downloads/)

By starting the MAMP app you are also starting your Apache and MySQL server. You should now be able to reach your local server at ```http://localhost:8888```.

By default, MAMP uses port 8888 for Apache and port 8889 for MySQL. It is convenient to change the MySQL and Apache ports to 3306 and 80 respectively to use default MySQL and Apache ports.

[![](https://github.com/irusri/geniesys/blob/master/docs/images/mamp_settings.png?raw=true)](http://www.mamp.info/en/downloads/)

**Download GenIE-Sys**

[![](https://github.com/irusri/geniesys/blob/master/docs/images/download.png?raw=true)](https://github.com/irusri/geniesys/archive/master.zip)

**Copy GenIE-Sys to MAMP Web server**

You will find the source of GenIE-Sys in your download folder. So you just need to Copy GenIE-Sys folder into corresponding ```~/Applications/MAMP/htdocs/``` folder.

That is basically what you need to do in order to install GenIE-Sys on your Mac's local server. You should now be able to access it at: ```http://localhost:[port number]/geniesys``` in your browser. Now you can see the essential website up and running. However to configure it correctly please update the configuration file as described in the next section.


## Configuration file

We should update the settings file(```geniesys/plugins/settings.php```) right after the installtion. Especially the base URL depending on your webhost. For example:

```php
/*Define your base url with trailing slash*/
$GLOBALS["base_url"]='http://localhost:[port number]/geniesys/';

OR

$GLOBALS["base_url"]='http://localhost:[port number]';

```




