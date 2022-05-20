# Créer un serveur nginx
## 1.Installation serveur nginx
## action:   
    -su | il faut se connecter en tant que root
    -apt-get update -y
    -apt-get install nginx -y
## 2.Verififcation
## action: 
    -nginx -v
    -systemctl status nginx
    -systemctl enable nginx
## 3.Sur le navigateur :
    10.0.0.229
## 4.Modification
    -cd/var/www/html/
    -ls
    -cat index.nginx-debian.html
    -nano /etc/nginx/site-enabled/default
    -cd / | se diriger vers le répertoire root
    -nano /etc/nginx/nginx.conf
    -ls /etc/nginx