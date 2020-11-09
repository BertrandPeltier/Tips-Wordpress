# Installation de WP

## Téléchargement, copie des fichiers et installation
 https://fr.wordpress.org/download/

 :warning:Copier les fichiers dans un sous-répertoire, cela augmente la sécurité

 :warning:Mettre un préfixe complexe pour les tables de la BDD, éviter `wp_`

## Post-installation
   
### Menu "Réglages/Général"
 * URL Wordpress : `http://xxx/sous-dossier/`
 * URL du site : `http://xxx`
 * Format date : `j M Y`

### .../Permaliens
 `Titre de la publication`

### index.php
 :warning:**COPIER** le fichier `index.php` à la racine du server

 Editer le fichier puis dans la section

 `/** Loads the WordPress Environment and Template */`

 Modifier la ligne
 
 `require __DIR__ . '/`**sous-dossier**`/wp-blog-header.php';`

### Mettre à jour les permaliens
 Réglages/Permaliens => `Enregistrer les modifications`


  