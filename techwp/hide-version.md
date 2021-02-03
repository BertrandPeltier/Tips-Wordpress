# Masquer la version de WordPress dans le code source :

Ajouter au fichier `functions.php` :

```php
add_filter('the_generator', 'wpm_delete_version');

// On retourne une chaine de caractère vide à la place de la version de WordPress
function wpm_delete_version() {
return '';
}
```
