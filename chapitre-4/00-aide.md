### Utilisation de l'aide 
9 catégories de page de manuel
- Commandes shell (1)
- Appels système (2) 
- Appels de bibliothèque (3)
- Fichiers spéciaux (4)
- Format des fichiers et conventions (5)
- Jeux (6)
- Divers (7)
- Commandes de gestion du système (8)
- Sous-programmes du noyau (9)

##### (1), (5) et (8) sont les categories phares a retenir
#### commande man
```
man cd 
```
#### Rechercher le manuel d'une commande 
```
man -k <keyword>
```
Exemple :
```
man -k passwd
```
#### Convertir le manuel d'une commande en fichier Postscript
```
man -t cd > cd.ps
```
#### Visualiser un fichier Postcript
```
evince file.ps
```
- Option ``` -i <number> ``` : pour specifier l'index de la page a afficher 
- Option ``` -w ``` : pour ouvrir le fichier en mode previsualisation 
#### imprimer le fichier Postcript
```
lp file.ps -P 2-3
```
- Option ``` -P ``` : permet de specifier les pages a imprimer 
#### Aide interne à une commande avec l'option --help
```
cd --help 
```
#### Informations brieves sur une commande 
```
info tree 
```

```
whatis tree
```

```
whereis tree
```
