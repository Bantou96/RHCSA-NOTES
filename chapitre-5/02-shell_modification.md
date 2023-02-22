### Changer l'environnement shell 
- ```/etc/profile``` : script de login pour tout les shell et tout les utilisateurs 
- ```~/.profile``` : script de login pour tout les shell d'un utilisateur specifique 
- ```/etc/bashrc``` : script de login pour le shell bash de tout les utilisateurs 
- ```~/.bashrc``` : script de login pour le shell bash d'un utilisateur specifique

### Exemple de modification du fichier ```~/.bashrc```
```
# parametrer la longueur de l'historique en modifiant les variables HISTSIZE et HISTFILESIZE
HISTSIZE=1000
HISTFILESIZE=2000

# afficher la date et l'heure lorsqu'on lance la commande history
HISTTIMEFORMAT="%F %T "

# eliminer les lignes dupliquer ou les lignes commencant par un espace dans l'historique
HISTCONTROL=ignoreboth

# permettre l'ajout au fichier d'historique sans pour autant ecraser le contenu
shopt -s histappend

# creer une alias de commande qui permet de lire un fichier de configuration sans afficher les lignes commentees
alias sc="grep ^[^#] $1"

# creer des alias permettant d'avoir des sorties colorees (nous aurons besoin d'installer 'exa')
alias ll='exa -l'
alias lla='exa -abghHliS'
alias llt='exa --long --tree'

# creer une fonction qui permet de creer un ou plusieurs repertoire et puis se deplacer dans le repertoire
mcd() {
  mkdir -pv $1 && cd $1
}

# definir vim comme editeur par defaut
export EDITOR=/usr/bin/vim

# ajouter un chemin pour chercher les commandes a executer 
export PATH=$PATH:/mnt/bin

# changer la langue en francais
export LANG=fr_FR.UTF-8

# modifier le prompt
PS1='[\u@\h \t \w]$ '
```
### Supprimer les modifications avec les commandes suivantes 
```
unset
```
```
export -n 
```
```
unalias
```
