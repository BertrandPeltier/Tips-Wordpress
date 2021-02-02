# Ajouter un favicon manuellement

Ajouter les lignes suivantes dans `functions.php` :
```php
// ADD FAVICON //
function my_favicon(){
	?>
	<link rel="icon" type="image/png" sizes="32x32" href="url-favicon">
	<?php
	}
	  add_action('wp_head', 'my_favicon');
```
