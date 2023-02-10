## Combinaison 
#### Concaténation deux fichiers
```
cat file1 file2 
```
#### Jointure ou fusion de colonnes
```
join -<num_col_file1> num -<num_col_file2> num file1 file2
```
- Option ```-t``` : permet d'ajouter un délimiteur. Par exemple :
```
join -t ':' -1 1 -2 2 file1 file2
```
- Option ```-i``` : permet d'ignorer la casse 
#### Regroupement ligne par ligne
```
paste file1 file2 
```
## Transformation 
#### Convertion des tabulations en espaces
```
expand file
```
- Option ```-t``` : permet de définir le nombre d'espaces
#### Convertion des espaces en tabulations
```
unexpand -a file 
```
#### Trier les lignes d'un fichier
Les types de tri :
- d : dictionnaire
- n : numérique 
- M : ordre chronologique
```
sort file
```
- Option ```-k``` : permet de spécifier la colonne et le type de tri. par exemple : 
```
sort -k 7d -k 3n file
```
#### Découper un fichier
```
split -l <nombre_de_lignes> prefix
```
- Option ```-C```: permet de découper en octects
- Option ```-b```: permet de découper en bits
#### Traduire les caractères sur un fichier
Exemple : transformer les M majuscules en miniscules sur un fichier
```
tr M m < file 
```
#### Eliminer les doublons sur un fichier trier
```
sort file | uniq   
```
## Formatage
#### Découper en fonction des mots
Exemple : 100 caractères max par ligne 
```
fmt -w 100 file
```
- Option ```-w``` : permet de préciser le nombre de mots par ligne
#### Numéroter les lignes d'un fichier
Exemple : numéroter toutes les lignes 
```
nl -b a file
```
Pour ne pas numéroter les lignes vides utiliser la commande suivante :
```
nl -b t file
```
- Option ```-n``` : permet de choisir l'alignement du numérotage (ln ou rn ou rz)

## Visualiser un fichier texte
#### Visualiser les premières lignes
```
head -n 20 file
```
#### Visualiser les dernières lignes
```
tail -n 20 file
```
- Option ```-f``` : permet de vérifier les modifications sur un fichier en temps réel
#### Visualiser page par page 
```
less /var/log/message
```
- Utiliser la touche ```espace``` pour naviguer par page
- utiliser la combinaison de touche ```esc``` + **v**
- /<mot_recherché> : faire une recherche 
- ?<mot_recherché> : faire une recherche inversée 
- q : quitter

## Résumer
#### extraire des colonnes 
Exemple : la commande suivante permet d'extraire la colonne 1 en utilisant comme délimiteur ':'
```
cut -d':' -f 1 /etc/passwd
```
#### Compter 
Compter le nombre de lignes
```
wc -l file 
```
Compter le nombre de mots
```
wc -w file 
```
Déterminer la taille du ficher en octect
```
wc -c file 
```
