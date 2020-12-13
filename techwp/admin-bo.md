# Interdire l'accès du back-office aux abonnés

Ajout de code dans le fichier `functions.php` du thème :

```php
    // Rediriger les non-administrateurs vers la page d'accueil À partir de l'administration
    function wpm_admin_redirection() {
        //Si on essaye d'accéder à L'administration Sans avoir le rôle administrateur
        if ( is_admin() && ! current_user_can( 'administrator' ) ) {
            // On redirige vers la page d'accueil
            wp_redirect( home_url() );
            exit;
        }
    }
    add_action( 'init', 'wpm_admin_redirection' );
```