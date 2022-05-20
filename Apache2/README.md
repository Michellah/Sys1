# Créer un serveur apache2

## 1.objectif: Installation apache2
## action: 
### Sur le terminal    
    -su | il faut se connecter en tant que root
    -apt-get update
    -apt-get install apache2
## 2.objectif: Configuration d'apache2
## action: 
### Sur le terminal:
    -/etc/init.d apache2 status | regarder la statut si c'est active
    -cd /etc/apache2 | entrer dans apache2
    -ls 
    -nano apache2.conf | pour modifier dans apache2.conf,ecrire "ServerName 127.0.0.1 ou localhost" en bas de "ServeurRoot "
    -ctrl x | pour enregistrer les modifications
    -/etc/init.d/apache2 restart | redémarer aprês chaque modification
    -/etc/init.d apache2 status | regarder la statut si c'est active
### Sur le navigateur:
    ecrire l'adresse ip Ip 127.0.0.1 ou localhost
### Revenir sur le terminal:
    -nano apache2.conf | on peut configurer "/var/www/"
    -ls
    -cd sites.enabled
    -ls -al 
    -nano 000-default.conf | enlever le # devant serverAdmin
    -/etc/init.d/apache2 restart | redémarer
    -/etc/init.d apache2 status | regarder la statut si c'est active
    -cd /var/www/html
    -ls
    -nano index.html | modifier ce que vous voulez
    -mv index.html test.html
