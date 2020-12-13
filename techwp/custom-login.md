# Changer URL de connexion

* Créer un nouveau fichier de login (avec le nom que l'on veut)
* Copier-coller le code du fichier wp-login.php
* Remplacer chaque instance "wp-login" par le nom du nouveau fichier
* Supprimer wp-login.php
* Mettre à sa place le nouveau fichier

## Custom de l'URL de connexion
Ajout de code dans functions.php du thème enfant et ensuite le custom se fait dans le CSS et le JS :
* Source : [codex Wordpress.org](https://codex.wordpress.org/Customizing_the_Login_Form)
* Link du CSS et du JS :
  ```php
    function my_login_stylesheet() {
    wp_enqueue_style( 'custom-login', get_stylesheet_directory_uri() . '/style-login.css' );
    wp_enqueue_script( 'custom-login', get_stylesheet_directory_uri() . '/style-login.js' );
    }
    add_action( 'login_enqueue_scripts', 'my_login_stylesheet' );
  ```
* Changer les links du logo
  ```php
    function my_login_logo_url() {
        return home_url();
    }
    add_filter( 'login_headerurl', 'my_login_logo_url' );

    function my_login_logo_url_title() {
        return 'Your Site Name and Info';
    }
    add_filter( 'login_headertitle', 'my_login_logo_url_title' );
  ```