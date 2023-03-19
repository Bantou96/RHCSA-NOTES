### Verification de la configuration reseau
- Obtenir l'adresse MAC
```
ip link show
```
- Obtenir l'adresse IP
```
ip addr show || ip addr show eth0
```
- Obtenir l'etat des interfaces 
```
ip -br addr || ip -br addr eth0
```
- Obtenir les statistiques 
```
ip -s link show || ip -s link show eth0
```
- Afficher la table de routage
```
ip route show
```
- Tester la connectivite
```
ping -c4 <ip-addr> || ping <ip-addr>
```
- Tracer les routes traversees
```
tracepath <ip-addr> || traceroute <ip-addr>
```
L'outil ```MyTraceroute``` fournit des informations beaucoup plus optimisees. La commande suivante est tres importante pour debogger 
```
mtr <ip-addr>
```
On peut creer un rapport avec la commande suivante :
```
mtr --report <ip-addr>
```
- Verifier les sockets (Exemple: socket ecoutant sur les ports udp et tcp)
```
ss -plunt
```
On peut aussi utiliser la commande ```netstat```
```
netstat -plunt
```
#### Modifier l'addresse ip d'une interface specifique
```
ip addr add <ip-addr>/mask dev eth0
```
#### Supprimer l'addresse ip 
```
ip addr delete <ip-addr>/mask dev eth0
```
### NetworkManager 
Sur RHEL9 on introduit l'approche creation de profile appliquee a une interface. L'outil permettant de le faire est le network manager. il existe plusieurs manieres d'apporter des modifications a savoir :
- nmcli (nous ferons focus sur le mode cli)
- nmtui
- web console
- ansible
Le fichier qui contient les profiles crees est : ``` /etc/Networkmanager/system-connections ```
- Afficher les connexions gerees par le NetworkManager 
```
nmcli connection show 
```
- Afficher les connexions actives 
```
nmcli con show --active 
```
- Ajouter un profile applique a une interface
```
nmcli con add con-name "My profile" type ethernet ifname eth0 ipv4.method manual \
ipv4.addresses <ip-addr> ipv4.dns <dns-ip1> ipv4.gateway <gw>
```
- Modifier un profil
```
nmcli con mod "My profile" +ipv4.dns <dns-ip2> con.autoconnect yes
```
- Activer le profil
```
nmcli con up "My profile"
```
- Afficher le profil 
```
nmcli con show "My profile" | less 
```
- Afficher les informations d'une interface
```
nmcli dev show eth0
```
- Recharger un profil
```
nmcli con reload "My profile"
```
- Supprimer un profil 
```
nmcli con delete "My profile"
```
- Afficher les permissions generales de l'utilisateur
```
nmcli gen permissions
```
### configurer le hostname et la resolution de nom
Fichiers importants : ```/etc/hostname```, ```/etc/hosts``` et ```/etc/nsswitch.conf```
- Afficher les informations de la machine
```
hostnamectl status 
```
- Afficher le hostname 
```
hostname
```
- Changer le hostname de maniere non permanente
```
hostname <new-name>
```
- Changer le hostname de maniere permanente
```
hostnamectl set-hostname <new-name>
```
- Traduire une ip en nom de domaine et vice-versa
```
host <domain-name> || host <ip-addr>
```
```
nslookup <domain-name> || nslookup <ip-addr>
```
```
dig <domain-name> || dig <ip-addr>
```
