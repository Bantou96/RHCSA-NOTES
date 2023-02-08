## Définition
Une commande est un programme ou une partie d'un programme
- ``` $PATH``` identifie les dossiers dans lesquels sont placés les programmes disponibles
- 2 types de commandes :
  - Commande interne : élément du shell
  - Commande externe : fichier spécifique

## Quelques commandes internes
#### Ouvrir la documentation d'une commande : ```man```
```
man echo
```
#### Changer de répertoire : ```cd```
```
cd /home
```
#### Afficher le répertoire de travail : ```pwd```
```
pwd
```
- Option ```-L``` : permet suivre les liens symboliques utiliser
#### Afficher une chaine de caractère : ```echo```
```
echo Hello
```
- Option ```-n``` : permet de supprimer le retour charriot
- Option ```-e``` : permet d'afficher les séquences d'échappement
#### Lancer un programme en remplacement du shell
```
exec ls
```
#### Afficher le temps d'exécution d'une commande (real, user et sys)
```
time sleep 3
```
#### Afficher les variables d'environnement
```
set
```
#### Stopper l'exécution du bash
```
exit
```
