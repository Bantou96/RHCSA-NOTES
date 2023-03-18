### Systemd (PID 1): composants
- Service --> daemons
- Path    --> watches files
- Mount   --> controls mounts
- Target  --> groups units
- Socket  --> listens on port
- Slice   --> Ressource management
- timer   --> scheduling

#### Commandes pour afficher les composants
```
systemctl list-units --type=<composants> -a 
```
#### Commandes pour afficher les fichiers des composants
```
systemctl list-units-files --type=<composants>
```
#### Verifier si un service est active ou pas 
```
systemctl is-enabled <name.service>  || systemctl is-active <name.service>
```
#### Verifier si un service a echoue ou pas 
```
systemctl is-failed <name.service>
```
#### Activer un service
```
systemctl enable --now <name.service>
```
#### Desactiver un service
```
systemctl disable <name.service>
```
#### Recharger les daemons
```
systemctl daemon-reload
```
#### Recharger et/ou redemarrer un service
```
systemctl reload-or-restart <name.service>
```
#### Demarrer, stoper ou redemarrer un service
```
systemctl start | stop | restart <name.service>
```
#### Verifier le statut d'un service
```
systemctl status <name.service>
```
#### Lister les dependances d'un service
```
systemctl list-dependencies <name.service>
```
#### Masquer un service ou demasquer un service
```
systemctl mask <name.service> || systemctl unmask <name.service>
```
