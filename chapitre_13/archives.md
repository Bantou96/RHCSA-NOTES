### Utilitaire ```tar```
#### les options courantes 
- Creer un fichier d'archive : ```--create || -c```
- Lister le contenu d'une archive : ```--list || -t```
- Extraire une archive : ```--extract || -x```
- Afficher les fichiers en cours d'archivage ou d'extraction : ```--verbose || -v```
- Nom du fichier d'archive a creer ou a ouvrir : ```--file || -f```
- Conserver les permissions d'origine du fichier : ```--preserve-permissions || -p```
- Activer la prise en charge du contexte SELinux : ```--selinux```
#### Les options de compression pour selectionner un algorithme
- Determiner automatiquement l'algorithme a utiliser : ```--auto-compress || -a```
- Algorithme de compression gzip (.tar.gz) : ```--gzip || -z```
- Algorithme de compression bzip2 (.tar.bz2) : ```--bzip2 || -j```
- Algorithme de compression xz (.tar.xz) : ```--xz || -J```
- Algorithme de variante LZ (.tar.Z) : ```--compress || -Z```
#### Commandes 
- Creer une archive 
```
tar -cf backup.tar file1.log file2.log file3.log
```
- Lister le contenu des archives 
```
tar -tf backup.tar
```
- Extraire le contenu des archives 
```
tar -xf backup.tar
```
- Extraire le contenu des archives en preservant les permissions
```
tar -xpf backup.tar
```
- Creer une archive compressee avec gzip (Exemple : creer un backup de /etc)
```
tar -czf /root/etc_backup.tar.gz /etc 
```
- Creer une archive compressee avec bzip2 (Exemple : creer un backup de /var/log)
```
tar -cjf /root/log_backup.tar.bz2 /var/log 
```
- Creer une archive compressee avec xz (Exemple : creer un backup de /etc/ssh)
```
tar -cJf /root/sshconfig.tar.xz /etc/ssh 
```
- Afficher la taille avec gzip et xz 
```
gzip -l file.tar.gz || xz -l file.xz
```
