# HTTPS et SSL (sans plugin)

## réglage général (Dashboad Wordpress) :
Mettre `https` à la place de `http` pour l'url du site et le dossier WP.

## .htaccess
Editer (ou créer un fichier .htaccess) et rajouter en ligne 1 :

```
#BEGIN redirection vers HTTPS 
<IfModule mod_rewrite.c>
RewriteEngine on
RewriteCond %{HTTP:X-Forwarded-Proto} !https
RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
```

```
# Protéger .htaccess et .htpasswds
<Files ~ "^.*\.([Hh][Tt][AaPp])">
order allow,deny
deny from all
satisfy all
</Files>
```

## wp-config.php
Dans le fichier wp-config rajouter en lign 1 :
```
/** Forcer le passage en https */
define('FORCE_SSL_ADMIN', true);  
if( strpos($_SERVER['HTTP_X_FORWARDED_PROTO'], 'https') !== false )
{
     $_SERVER['HTTPS'] = 'on';
}
```

Définir l'url du site et le dossier WP :
```
/** Définir l'URL par défaut */
define('WP_HOME', 'https://monsite.com');
define('WP_SITEURL', 'https://monsite.com/backoffice');
```
