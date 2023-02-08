### GREP
Syntaxe : grep [options] regexp file
- Option ```-c``` : permet d'afficher le décompte des lignes correspondantes 
- Option ```-i``` : permet d'ignorer la casse
- Option ```-E``` : identique à la commande ```egrep```. Elle utilise la syntaxe étendue

### SED (solution d'édition de fichier ligne par ligne)
Syntaxe : sed [options] command file 
- substitution : sed s/modèle/remplacement/drapeau(x) file  
Exemple : 
Remplacer par hello les lignes commençant et se terminant par # 
```
sed 's/^#$/hello/' file
```
Remplacer tous les A majuscules en a minuscules en utilisant le drapeau **g** (global)
```
sed 's/A/a/g' file
```
- Option ```-i``` : permet de sauvegarder directement
