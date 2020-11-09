# Créer un thème enfant

 https://wpformation.com/theme-enfant-wordpress/

## Créer un dossier

 `/wp-content/themes/`**nom_du_theme_enfant**

## Créer 2 fichiers

### functions.php
 Ajouter les lignes :
 
    <?php
    /**
    ** activation theme
    **/
    add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
    function theme_enqueue_styles() {
    wp_enqueue_style( 'parent-style', get_template_directory_uri() . '/style.css' );

    }

### style.css
Ajouter les lignes :

    /*
    Theme Name: xxx
    Description: xxx
    Author: xxx
    Author URI: xxx
    Template: Nom exact du thème parent (attention aux majuscule)
    Version: xxx
    */
