### Transfert de fichiers securise avec SFTP
```
sftp remoteuser@remotehost
```
- Quelques commandes sftp
```
sftp> pwd 
sftp> lpwd
sftp> mkdir hostbackup
sftp> cd hostbackup
sftp> put /etc/hosts
sftp> put -r /home/remoteuser/myrepo
sftp> get /etc/file.conf
```
- ```put``` : permet de charger un fichier sur le systeme local dans le repertoire courant
- ```get``` : permet de telecharger un fichier a partir de l'hote distant vers le repertoire courant. cette derniere peut etre fait sans ouverture de session interactive avec la commande suivante
```
sftp remoteuser@remotehost:/path
```
#### A noter que la commande scp est basee sur un protocole historique rcp qui n'a pas ete concu en tenant compte des considerations de securite. SCP presente un probleme d'injection de code connu qui pourrait permettre a un attaquant d'executer des commandes arbitraires sur le serveur distant. Red Hat recommande de ne plus utiliser la commande SCP.

### Synchronisation de fichiers securisee entre des systemes
Les options activees avec rsync -a (mode Archive)
- ```-r || --recursive``` : Synchronise l'arborescence de repertoires complete
- ```-l || --links``` : Synchronise les liens symboliques
- ```-p || --perms``` : Conserve les permissions
- ```-t || --times``` : Conserve les horodatages
- ```-g || --group``` : Conserve la propriete du groupe
- ```-o || --owner``` : Conserve le proprietaire des fichiers 
- ```-D || --devices``` : Conserve les fichiers de peripheriques
- ```-A && -X```: Conserve respectivement les ACL et les contextes de fichier SELinux

- Exemple 1: synchroniser le contenu du repertoire /var/log avec le repertoire /tmp en creant le repertoire log 
```
rsync -av /var/log remoteuser@remotehost:/tmp
```
- Exemple 2: synchroniser le contenu du repertoire /var/log avec le repertoire /tmp sans creer le repertoire log 
```
rsync -av /var/log/ remoteuser@remotehost:/tmp
```
