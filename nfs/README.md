# Créer un serveur nfs
## Côté serveur
## 1.Installation serveur nfs 
    -su
    -apt update
    -apt install nfs-kernel-server
## 2.Créer un répertoire d'exportation nfs
    -mkdir -p /mnt/nfs_share | spécifier le nom du répertoire de montage nfs
    -chown -R personne:nogroup /mnt/nfs_share/ | suppreéssion de restrictions dans les authorisations du répertoire
    -chmod 777 /mnt/nfs_share/ | donner les permisssions, ici c'est lecture, écriture, exécution
## 3.Accorder l'accès au partage aux systèmes clients
    -vim /etc/exports
    -/mnt/nfs_share 10.0.0.228/8(rw,sync,no_subtree_check) | rw : Signifie Lecture/Écriture,sync : nécessite que les modifications soient écrites sur le disque avant d'être appliquées, No_subtree_check : Élimine la vérification des sous-arbres.
## 4. Exporter le répertoire de partage 
    -exportfs -a
    -ystemctl restart nfs-kernel-server
## 5.Autoriser l'accès nfs via le pare-feu
    -ufw allow from 10.0.0.229/8 to any port nfs
    -ufw enable
    -ufw status
# Côté client
## 1.Installation
    -su
    -apt update
    -apt install nfs-common
## 2.Créer un point de montage NFS sur le client
    -mkdir -p /mnt/nfs_clientshare
## 3.Monter le partage NFS sur le système client
    -ifconfig
    -mount 10.0.0.229:/mnt/nfs_share  /mnt/nfs_clientshare
## 4.Tester du du partage nfs
#### créer dans le repertoire de partage
    -cd /mnt/nfs_share/
    -touch cour1.txt cour2.txt cour3.txt
#### revenir au système client nfs
    -ls -l /mnt/nfs_clientshare/
