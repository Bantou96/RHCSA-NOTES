### Fichiers du service ssh
- ``` ~/.ssh/known-hosts || /etc/ssh/ssh_known_hosts ``` : fichier contenant les empreintes des serveurs sur lesquels on s'est deja connecte
- ``` /etc/ssh/*.pub ``` : cles publiques des serveurs distants
- ``` /etc/ssh/ssh_config ``` : fichier de configuration global 
- ``` ~/.ssh/config ``` : fichier de configuration specific a l'utilisateur
- 
### Commandes 
- Connection 
```
ssh <remotehost> || ssh user@remotehost
```
- Generation de cles avec passphrase
```
ssh-keygen || ssh-keygen -f <file_path>
```
- Verification de l'empreinte
```
ssh-keygen -f -l <file_path>
```
- Generation de cles sans passphrase
```
ssh-keygen -N '' -f <file_path>
```
- Partage de la cle publique
```
ssh-copy-id -i <pub_key> user@remotehost
```
- Demarrage du programme ssh-agent
```
eval $(ssh-agent)
```
- Ajout de cles
```
ssh-add || ssh-add <private_key>
```
- Resolution des problemes de connexion 
```
ssh -v user@remotehost
```
- Afficher les utilisateurs connectes
```
w --from
```
### Recommandations
- Desactiver les connexions a distance en tant que root
- Exiger une authentification par cle publique plutot que par mot de passe
