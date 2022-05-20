# Créer un serveur samba
## 1.Installation serveur samba
## action:   
    -su | il faut se connecter en tant que root
    -apt-get update
    -apt-get install samba
## 2.Configuration d'apache2
## action: 
    -nano /etc/samba/smb.conf
    -ajouter:
        [HEIstudent]
        comment = HEIstudent
        browseable = yes
        publics = no
        valids users = hp
        quest = no
        writable = yes
        path = /root/part
    - /etc/init.d/smbd restart | redémarrer 
## 3.Créer un compte samba
## action:
    -adduser michellah
    -smbpasswod -a michellah
    -/etc/init.d/smbd restart | redémarrer

## 4.Sur une autre terminal 
    -smbclient -L 10.0.0.229 -U michellah
    -smbclient //10.0.0.229/part

## 5.Accéder au repertoire de partage
    -ls
    -cd part
    -touch cour.txt   
    -touch lecon.pdf 
    -ls
    -nano cour1ARIL.txt | ajouter quelque chose