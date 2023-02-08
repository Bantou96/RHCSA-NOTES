### Gestion de la proprieté d'un fichier
- Affichage des droits (nom & groupe)
```
ls -l 
```
- Affichage des droits (uid & guid)
```
ls -n 
```

### Modification de la proprieté d'un fichier
```
chown [options] [newowner][:newgroup] file
```
```
chgrp -o [newgroup] file
```
l'option ``` -R ``` permet d'effectuer la modification sur un répertoire. 

### Droits d'accés POSIX
- Fichier pipe/socket : permet de gérer la communication inter-processus
- Périphérique bloc : écriture bloc par bloc (exemple disque dur)
- Périphérique caractère : communication bit à bit

### Les permissions
Read - write - execute (rwx)  --> user - group - others (ugo = a)
- Modifier les permissions
```
chmod [mode] file
```
Exemple de mode : u+x ; g-r ; a=rw ; 777 ; 744 ; +t (sticky bit)
- Droits spéciaux
SUID & SGID (Set user/group ID)
  - Pour les exécutables, activer le mode u+s ou g+s
  - Pour le sticky bit, ajouter le mode +t (permet de restreindre les droits de suppression)
 
résumé de la totalité des permissions : sst rwx rwx rwx ou 7777

il peut arriver que le suid soit en majuscule (S) cela veut dire le droit d'exécution n'est inclu. 

NB : les attaques sushi permettent de faire une élevation de privilége
- Activer le SUID par exemple pour la commande mkfs
- Puis faire une copie bit à bit 
```
dd if=/bin/su of=mkfs
```
