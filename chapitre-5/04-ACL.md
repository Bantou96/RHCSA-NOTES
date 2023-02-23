### ACL
- Le besoin est d'étendre les droits POSIX
- Prérequis : vérifier si la fonctionnalité ACL est supportée
  - Exécuter la commande : ``` grep ACL /boot/config-* ```
  - Regarder si la ligne ``` CONFIG-FS-POSIX-ACL=y ``` est présente
  - Ajout la fonctionnalité ACL dans le fichier ``` /etc/fstab ``` pour la partition ``` /home ```

### Fonctionnement
- Afficher les ACL
```
getfacl <file>
```
- Créer ou modifier une ACL
```
setfacl -m [d:][permission, permission, ....] <file>
```
Exemple : 
```
setfacl -m u:user:rw- <file>
```
l'option ``` -d ou d:o::r-- ``` permet de faire hériter l'ACL à tous les fichiers d'un repertoire spécifique. Elle est souvent combinée avec l'option ``` -R ``` (récursif)
- Supprimer une ACL
Pour supprimer toutes les ACL
```
setfacl -b <file>
```
Pour supprimer les permissions par défaut
```
setfacl -k <file> 
```
Pour supprimer une ACL spécifique
```
setfacl -x u:user <file>
```
- Configuration d'un masque (droit maximal)
Exemple : mask : r-x ; user : rw- ; #effective : r--
```
setfacl -m m::r-x file
```
### Umask
Par défaut :
- file : 0666
- directory : 0777
- Afficher l'umask
```
umask -S
```
ou 
```
umask -p
```
- Modififer l'umask (soustraire la valeur préciser dans la commande). Exemple :
```
umask 0022
```
### Hierarchie 
Droits POSIX --> mask --> ACL user --> ACL group.
