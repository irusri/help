# Configuration files

We should update the settings file\(`geniesys/plugins/settings.php`\) right after the installtion. Especially the base URL depending on your webhost. For example:

```text
/*Define your base url with trailing slash*/
$GLOBALS["base_url"]='http://localhost:[port number]/geniesys/';

OR

$GLOBALS["base_url"]='http://localhost:[port number]';
```

