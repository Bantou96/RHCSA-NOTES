### Gestion des processus 
commandes pour afficher l'arborescence des processus 
```
pstree 
```
#### Les etats des processus
- fork (new process)
- Runnable (R) --> ready 
- Running (R) --> kernel || user 
- Zombie (Z)
- Stopped (T)
- Sleeping (K | D | S | I) --> wait
- Dead (X)

### Affichage des processus 
- Afficher tous les processus de l'utilisateur y compris les processus sans terminal de controle 
```
ps aux
```
- Afficher avec plus de details et plus rapidement (en evitant la recherche d'utilisateur) 
```
ps lax
```
- Utiliser la syntaxe UNIX pour afficher tous les processus 
```
ps -ef 
```
- Utiliser la commande top pour afficher tous les processus
```
top
```
### Execution des taches
- Executer une tache en arriere plan 
```
sleep 1000 & 
```
- Afficher la liste des taches de la session shell
```
jobs
```
- Amener une tache en arriere plan au premier plan 
```
fg %<task-number>
```
- Executer un processus suspendu 
```
bg %<task-number>
```
- Afficher les informations relatives aux taches 
```
ps j
```
### Les signaux
- Lister les noms et les numeros de tous les signaux
```
kill -l 
```
- Supprimer un processus 
```
kill <pid> || kill -SIGTERM <pid>
```
- Forcer la suppression 
```
kill -9 <pid>
```
- Supprimer plusieurs processus en fonction du nom de la commande 
```
killall <cmd-name>
```
- La commande pkill inclut des criteres de selections avances a savoir (UID, GID, Parent, Command, Terminal)
```
pkill -U <user>
```
- Identifier les numeros de processus a supprimer 
```
pgrep -l -u <user>
```
### Activite des processus 
- Afficher la charge moyenne actuelle
```
uptime
```
- determiner le nombre de processeurs presents sur un systeme
```
lscpu
```
