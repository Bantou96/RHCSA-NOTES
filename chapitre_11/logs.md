### Gestion des logs avec systemd
- ``` rsyslog ``` : envoie les logs vers ``` /var/log ```
- ``` systemd-journald ``` : envoie les logs vers le datastore principal
### Datastores
- Fichier d'ecriture des evenements en cours de maniere non permanente (par defaut) : ``` /run/log/journal ```
- Fichier d'ecriture des evenements en cours de maniere permanente : ``` /etc/systemd/journald.conf ```
### Syslog
Le protocol syslog est utilise par les deux daemons : systemd-journald et rsyslog. les composants du protocol syslog sont :
- Facility : Sous systeme qui genere le message
- Priority : Urgence du message 
### Generer ds logs fictifs (exemple pour sshd)
- Creation d'un drop-in file en specifiant la "facility" local6 (sachant que les facilities local0..local6 sont libres par defaut)
```
echo SyslogFacility local6 >> /etc/ssh/sshd_config/99-logging.conf
```
- Redirection des logs sshd vers un fichier specifique 
```
echo 'local6.*  /var/log/sshd.log' >> /etc/rsyslog.d/99-sshd.conf
```
- Generation de logs avec ```logger```
```
logger -p local6.info "I am an info message using local6"
```
### Commandes journalctl
- Afficher le journal 
```
journalctl
```
- Afficher le journal sous forme inversee
```
journalctl -r
```
- Afficher le journal sous forme dynamique 
```
journalctl -f 
```
- Affiner la recherche dans le journal. Exemple afficher les evenements sshd avec la facility error ayant lieu dans les 30 dernieres minutes 
```
journalctl -p err -u sshd --since $(date "+%R" -d "30 minutes ago")
```
- Lister les redemarrages du systeme
```
journalctl --list-boots
```
### TimeZones et NTP
- Afficher les informations de la timezone actuelle
```
timedatectl
```
- Lister les timezones ou une timezone specifique
```
timedatectl list-timezones | grep -i paris
```
- Changer la timezone
```
timedatectl set-timezone Europe/Paris
```
- Activer le protocol ntp
```
timedatectl set-ntp true
```
- Fichier de gestion du ntp : ``` /etc/chrony.conf ```
```
chronyc sources -v 
```

