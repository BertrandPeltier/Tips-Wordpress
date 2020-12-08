# Changer URL de connexion

* Créer un nouveau fichier de login (avec le nom que l'on veut)
* Copier-coller le code du fichier wp-login.php
* Remplacer chaque instance "wp-login" par le nom du nouveau fichier
* Supprimer wp-login.php
* Mettre à sa place le nouveau fichier

# Custom avec du CSS

* Ajouter un dossier `custom-login` dans le thème enfant dans lequel on place le fichier CSS `login-style.css`.

* Dans le fichier functions.php du thème enfant ajouter les lignes de codes suivantes (permet de lier le fichier CSS à la page de connexion) :
```php
//prise en compte de ma nouvelle feuille de style par mon thème enfant
function my_login_stylesheet() {
	wp_enqueue_style( 'custom-login', get_stylesheet_directory_uri() . '/login/login-style.css' );
   }
   add_action( 'login_enqueue_scripts', 'my_login_stylesheet' );
```
