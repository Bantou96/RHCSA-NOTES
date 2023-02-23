### Politique d'identification sur un noyau linux 
- Processes --> process IDs (PIDS)
- Users --> user IDs (UIDS)
- Groups --> group IDs (GIDS)
- Files --> Index nodes (inodes)

### UID ranges 
- UID 0 --> super User (root)
- UID 1-200 --> System account UIDs statically assigned to system process
- UID 201-999 --> Sytem process that do not own file on this system (dynamically)
- UID 1000+ --> range regular users

### Repertoires de gestion des utilisateurs
- ```/etc/passwd``` : informations sur les comptes utilisateurs
- ```/etc/group``` : informations sur les groupes 
- ```/etc/shadow``` : informations sur les mots de passe 
- ```/etc/sudoers``` : informations sur les groupes super utilisateur
- ```/etc/login.defs``` : informations sur la politique de mot de passe globale utilisee
  
### Commandes pour afficher les proprietes d'un utilisateur (uid, gid, groups, shell ...)
```
id 
```
ou
```
id <user>
```
Note : ```gid``` represente le groupe principal de l'utilisateur et dans ```groups``` on retrouve le groupe principal et les groupes secondaires s'ils existent.

La commande ```whoami``` fournit just le nom de l'utilisateur 

### Commandes pour rechercher un utilisateur ou un groupe dans l'annuaire 
- Les informations utilisateurs sont stockees dans le fichier ```/etc/passwd```
```
grep <user> /etc/passwd
```
- Les champs dans le fichier ```/etc/passwd```. la valeur ```x``` represente le mot de passe qui est gere par un autre fichier 
```
user:x:uid:gid:comment:working-directory:shell
```
- Pour effectuer une recherche dans l'ensemble des annuaires (en cas d'integration avec AWS ou Windows AD). utiliser la commande suivante :
```
getent passwd <user>
```
- Les informations concernant les groupes sont stockees dans le fichier ```/etc/group```
```
grep <group> /etc/group
```
- Si on souhaite voir les proprietes d'un groupe il faut afficher le contenu de ```/etc/sudoers```
```
grep <group> /etc/sudoers
```

### Les commandes super utilisateur
- Pour lancer une commande avec les droits 'sudoers'
```
sudo <command>
```
- Pour se connecter en tant que root
```
su - root || su  
```
Le tiret permet d'enroller les variables d'environnement lors de la nouvelle connexion 
- Pour se connecter avec un utilisateur specifique (il faut que cet utilisateur fasse parti des 'sudoers') 
```
su - <user> || sudo -i 
```
la commande ``` sudo bash ``` fait la meme chose mais permet en plus de conserver le repertoire de travail 

Le repertoire de gestion des 'sudoers' est : ``` /etc/sudoers.d ```

### Ajouter un nouvel utilisateur 
```
sudo useradd <user> --uid <value> --gid <value> --groups <value> --create-home --home /home/<directory> --shell /bin/bash 
```
ou en plus simple 
```
sudo useradd <user> -u <value> -g <value> -G <value> -m -d /home/<directory> -s /bin/bash 
```
- Option ``` --uid || -u ``` : permet de specifier l'uid de l'utilisateur 
- Option ``` --gid || -g ``` : permet de specifier le groupe principal de l'utilisateur
- Option ``` --groups || -G ``` : permet de specifier le ou les groupes secondaires de l'utilisateur 
- Option ``` --create-home || -m ``` : permet de creer le repertoire de l'utilisateur 
- Option ``` --home || -d ``` : permet de specifier le repertoire utilisateur a creer

### Modifier les proprietes d'un utilisateur
```
usermod <user> -c <comment> -g <principal-group> -aG <secondary-group> -L (lock user) -U (unlock user)  
```
Ces options peuvent etre utilisees une par une selon le besoin.

### Supprimer un urilisateur 
```
userdel -r <user>
```
L'option ``` -r ``` permet de supprimer le repertoire de travail. 

Pour rechercher les repertoires dont les utilisateurs ont ete supprimes. utiliser la commande suivante 
```
find / -nouser -o -nogroup 2>/dev/null
```

### Gestion des groupes 
- ```groupadd``` --> permet de creer un groupe
- ```groupmod``` --> permet de modifier un groupe
- ```groupdel``` --> permet de supprimer un groupe
- ```newgrp```   --> permet de changer le groupe principal  
- ```groups```   --> afficher les groupes

- Pour chercher un groupe dans l'ensemble des annuaires 
```
getent group <group-name>
```
- Pour trouver par exemple la valeur maximal du gid des groupes systemes 
```
grep SYS_GID_M /etc/login.defs
```

### Gestion des mots de passe 
Les mots de passe sont stockes dans ```/etc/shadow```

- Les champs : 
```
user:$hashing-algorithm$salt$password-hash:epoch:mindays:maxdays:warning:inactivity:expire-date
```
- Pour $hashing-algorithm :

$1= MD5 hashing algorithm ; $5=SHA-256 Algorithm ; $6=SHA-512 Algorithm

- Pour modifier ces derniers pour un utilisateur specifique, utiliser la commande ```chage``` 
```
chage -m <value-mindays> -M <value-maxdays> -W <value-warning> -I <value-inactivity> -E <expire-date> <user>  
```
- Pour lister les changements
```
chage -L <user>
```
- Pour forcer un utilisateur a changer son mot de passe
```
chage -d 0 <user>
```

La commande ```date``` peut servir pour calculer la valeur du expire date
```
date -d "+30 days" +%F
```
```
chage -E $(date -d "+30 days" +%F) <user>
```
