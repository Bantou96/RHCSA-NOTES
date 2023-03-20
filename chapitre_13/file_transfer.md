### Transfert de fichiers securise avec SFTP
```
sftp remoteuser@remotehost
```
```
sftp> pwd 
sftp> lpwd
sftp> mkdir hostbackup
sftp> cd hostbackup
sftp> put /etc/hosts
sftp> put -r /home/remoteuser/myrepo
```
