### Définition
Une variable permet d'associer une clé (son nom) à une valeur, en mémoire.
  - Toute valeur de variable est considérée comme une chaine de caractères

#### Déclaration : aucun typage donc une simple affectation suffit
```
var="Hello"
```
#### Utilisation : nécessite le caractère $
```
echo $mavariable
```
ou 
```
echo ${mavariable}
```
Cette dermiere peut etre utile dans le cas ou on souhaite concatener deux variables. par exemple :
```
echo ${var1}_${var2}
```
#### Substitution des commandes 
```
$command
```
Exemple :
```
echo Today is $(date +%A).
```
#### Portée d'une variable : par défaut locale
- Disponible que pour l'instance de Bash
- Pas accessible par les autres programmes
#### Variable d'environnement : accessible par tout les programmes au sein d'un même environnement
Pour cela il faut utiliser la commande : export + la référence de la variable
```
var="Hello"
```
```
export var
```
#### Variables de paramètres 
- Variable locale utile en scripting 
- Permet l'enregistrement des arguments 

```
read -sr ROOT_PASSWORD
```
```
echo $ROOT_PASSWORD
```
