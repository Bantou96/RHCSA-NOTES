### Flux
- entrée standard (stdin) : [0]
- sortie standard (stdout) : [1]
- sortie d'erreur standard (stderr) : [2]

### Redirections
- stdout vers un nouveau fichier : >
- stdout à la suite d'un fichier : >>
- stderr vers un nouveau fichier : 2> 
- stderr à la suite d'un fichier : 2>>
- stdout + stderr : &>
- stdin depuis un fichier : <
- stdin à partir d'une chaine de caractères : << 
- stdin et stdout vers et depuis le même fichier : <> 

Exemples :
- rediriger la sortie de la commande **ls** vers un fichier
```
ls > directory_list.txt
```
- Donner en entrée une chaine de caractère
  - Exemple : Utiliser le mot EOF(End Of File) pour indiquer la fin de saisi.
```
cat << EOF
>Bonjour
>je suis ravi de vous partager
>mes notes pour la préparation de la certification LPIC
>EOF
```  
### Pipes
- le caractère | : permet de rediriger la sortie standard d'une commande vers l'entrée standard d'une autre commande
  - Exemple : la commande suivante permet de rediriger la sortie de la commande ***ls*** vers l'entrée de la commande ***grep***
```
ls | grep doc
``` 
### Utilisation et substition d'arguments
- xargs : permet de faire en sorte que la sortie de la première commande soit utiliser comme argument de la deuxième commande
  - Exemple : la commande suivante permet de donner en argument à la commande ***rm***, la sortie de la commande ***ls***
```
ls | xargs rm
```
- backquotes : remplacer de manière itérative la sortie d'une commande 
```
rm `ls`
```
