# Logout redirect

Ajouter ce code à `functions.php`, la redirection se fera vers la home page du site :

```php
// Logout redirect
add_action('wp_logout','auto_redirect_after_logout');

function auto_redirect_after_logout(){
  wp_safe_redirect( home_url() );
  exit;
}
```


On peut rediriger vers la page que l'on veut, par ex la page de connexion :
"https://monsite.com/login.php"
