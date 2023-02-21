### Changer l'environnement shell 
- ```/etc/profile``` : script de login pour tout les shell et tout les utilisateurs 
- ```~/.profile``` : script de login pour tout les shell d'un utilisateur specifique 
- ```/etc/bashrc``` : script de login pour le shell bash de tout les utilisateurs 
- ```~/.bashrc``` : script de login pour le shell bash d'un utilisateur specifique

### Exemple de modification du fichier ```~/.bashrc```
```
HISTFILESIZE=1000

HISTTIMEFORMAT="%F %T "

export LESS="-X"

alias skip_comment="grep ^[^#] $1"

mcd() {
  mkdir -pv $1 && cd $1
}

export EDITOR=vim

export PATH=$PATH:/mnt/bin

export LANG=fr_FR.UTF-8

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
