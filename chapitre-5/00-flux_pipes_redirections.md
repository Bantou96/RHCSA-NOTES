### Flux
- entrée standard (stdin) : [0]
- sortie standard (stdout) : [1]
- sortie d'erreur standard (stderr) : [2]

### Redirections
- stdout vers un nouveau fichier : ```> file```
- stdout à la suite d'un fichier : ```>> file```
- stderr vers un nouveau fichier : ```2> file``` 
- stderr à la suite d'un fichier : ```2>> file```
- stdout + stderr : ```&> file``` ou ```> file 2>&1```
- Rediriger stdout et stderr sans ecraser le fichier :  ou ```&>> file``` ou ```>> file 2>&1```
- stdin depuis un fichier : ```< file```
- stdin à partir d'une chaine de caractères : ```<< file``` 
- stdin et stdout vers et depuis le même fichier : ```<> file``` 
- Supprimer les messages d'erreur stderr en les redirigeant vers /dev/null : ```2> /dev/null```

Exemples :
- rediriger la sortie de la commande **ls** vers un fichier
```
ls > directory_list.txt
```
- rediriger les erreurs de la commande find vers /dev/null(fichier de peripherique vide)
```
find / -size +100M 2> /dev/null
```
- rediriger les erreurs et la sortie standard de la commande find vers un fichier specifique 
```
find / -size +100M &> 100MB_plus_files.txt
```
ou
```
find / -size +100M > 100MB_plus_files.txt 2>&1
```
- Donner en entrée une chaine de caractère
  - Exemple : Utiliser le mot EOF(End Of File) pour indiquer la fin de saisi.
```
cat > file << EOF
>Bonjour
>je suis ravi de vous partager
>mes notes pour la préparation de la certification RHCSA
>EOF
```  
### Pipes
- le caractère | : permet de rediriger la sortie standard d'une commande vers l'entrée standard d'une autre commande
  - Exemple : la commande suivante permet de rediriger la sortie de la commande ***ls*** vers l'entrée de la commande ***grep***
```
ls | grep doc
``` 
### La commande tee
Elle permet d'afficher le resultat de la commande vers le terminal et en meme temps faire la redirection vers un fichier specifique 
- Exemple : Afficher les informations du systeme sur le terminal et en meme temps faire la redirection vers un fichier 
```
hostnamectl | tee my_system.txt
```
- Option ```-a``` : permet de faire l'ajout sur un fichier existant (la commande tee sans option ecrase le contenu du fichier existant)
- Exemple : Ajout des informations reseau dans le fichier my_system.txt
```
ip a | tee -a my_system.txt
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
