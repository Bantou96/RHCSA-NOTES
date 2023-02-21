# Système de fichiers structurés en arborescence
3 types de fichiers :
- Fichiers ordinaires : mémorisation des données des utilisateurs et du système
- Fichiers répertoires : Contient la liste et la référence des fichiers placés sous son contrôle
- Fichiers spéciaux : désignent les périphériques, les tubes et autres support de communication interprocessus 

### Convention de nommage des fichiers 
- Utiliser le caractère (.) pour les fichiers cachés
- Privilégier les miniscules pour le nommage
- Eviter les caractères spéciaux et les blancs (par exemple créer un fichier ```my_file``` plutôt que ```my file```)

### Types de fichiers
- Fichier de type standard : (-)
- Fichier de type répertoire : (d)
- Fichier de périphérique bloc : (b)
- Fichier de périphérique caractère : (c)
- Fichier socket : (s)
- Lien symbolique sur un fichier : (l)  

### Arborescence
- /     --> Racine du système 
- /bin  --> Commande binaires utilisateurs essentielles 
- /boot --> fichiers statiques du démarrage
- /dev  --> fichiers de périphériques
- /etc  --> fichiers de configuration d'un sytème spécifique
- /lib  --> fichiers des bibliothèques partagés et des modules du noyau
- /home --> répertoires personnels des utilisateurs 
- /root --> répertoire personnel de l'admin 
- /mnt  --> point de montage pour les systèmes de fichiers 
- /proc --> système de fichiers virtuel d'informations du noyau et des processus 
- /sbin --> répertoire contenant les exécutables
- /sys  --> fichiers d'état des périphériques 
- /tmp  --> fichiers temporaires
- /var  --> fichiers variables qui changent de maniere dynamique

Utiliser la commande suivante pour afficher l'arborescence
``` 
tree -d | less
```

### Répertoires spéciaux
- Répertoire courant noté .
- Répertoire parent noté ..
- Répertoire utilisateur noté ~
- Répertoire précédent noté -
- Chemin : 
  - Absolu : chemin complet à partir de la racine et commençant toujours par "/"
  - Relatif : chemin partiel d'un répertoire par rapport à l'endroit où l'on se trouve. 
