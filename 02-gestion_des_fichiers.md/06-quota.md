### Quota
- Vérification de la présence de la fonctionnalité
```
grep QUOTA /boot/config-*
```
- Montage : activer ``` usrquota ``` et ``` grpquota ``` dans le fichier ``` /etc/fstab ```
- 2 types de limitation : Hard et Soft
- Afficher les quotas
```
repquota -a 
```
- Initialiser, vérifier et mettre à jour
Sur tous les points de montage
```
quotacheck -a 
```
ou sur un point de montage spécifique
```
quotacheck /mnt/test 
```
- Editer les quotas 
```
edquota -u user
```

NB : Pour fixer l'éditeur de notre choix. 

Ajouter en fin du fichier ``` /etc/profile ``` ou ``` /home/user/.bashrc ```
```
EDITOR="vim"
export EDITOR
```
