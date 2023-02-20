### Globing
- (?) : désigne n'importe quel caractère 
- (*) : désigne n'importe quelle chaine de caractère 
- [...] : désigne n'importe quel caractère dans la chaine

## Commandes essentielles
#### Copier un fichier : ```cp``` 
```
cp file_src file_dest
```
- Option ```-r``` : permet de copier un dossier
- Option ```-i``` : lance une invite demandant la confirmation de copie
#### Creer un backup de configuration
```
cp file.config{,.back}
```
Creer un backup en precisant la date 
```
cp file.config{,.$(date +%F)}
```
#### Renommer et/ou déplacer un fichier : ```mv``` 
```
mv file_src file_dest
```
#### Renommer tout les fichiers .old en .back par exemple 
```
rename .old .back * 
```
#### Créer un fichier vide ou modifier l'horodatage : ```touch```
```
touch new_file
```
#### Creer plusieurs fichiers avec une seule commande 
La commande suivante permet de creer 4 saison d'une serie tele contenant chacune 8 episodes.
```
touch tv_season{1..4}_episode{1..8}.ogg
```
#### Supprimer un fichier : ```rm```
```
rm file
```
- Option ```-r``` : permet de supprimer un dossier
- Option ```-f``` : permet de forcer la suppression
- Option ```-i``` : lance une invite demandant la confirmation de la suppression (peut être très utile dans le cas de la suppression)
- On peut combiner les options en faisant par exemple :
```
rm -rf /directory/file
```
#### Afficher le contenu d'un répertoire : ```ls```
```
ls
```
- Option ```-l``` : permet d'afficher les droits des fichiers. 
  - La commande ```ll``` fait la même chose et ```llt``` (permet d'afficher en plus l'arborescence)
- Option ```-a``` : permet d'afficher tous les fichiers (les fichiers cachés)
- Option ```-i``` : permet d'afficher le numero d'inode
- Option ```-ltr``` : permet de trier par ordre de creation 
#### Afficher l'arborescence : ```tree```
```
tree
```
- Option ```-L <number>``` : permet d'afficher que le niveau specifier. par exemple afficher le premier niveau d'arborescence de la racine 
```
tree -L 1 /
```
- Option ```-d ``` : permet d'afficher que les repertoires

#### Créer un répertoire : ```mkdir```
```
mkdir directory
```
- Option ```-p``` : permet de créer un répertoire parent vide
#### Supprimer un répertoire vide : ```rmdir```
```
rmdir directory
```
#### Créer un lien matériel (le lien est independant du fichier) : ```ln``` 
```
ln file
```
- Option ```-s``` : permet de créer un lien symbolique (le lien est dependant du fichier)
```
ln -s file_src file_dest
```
