# Apache

## Securité SSL/TLS
### Requirement
Vérifier que Apache écoute le port 443.
```bash
$ netstat -tanpu | grep "LISTEN" | grep "443"
```
Activer le module SSL Apache
```bash
$ sudo a2enmod ssl
```
Activer le module Headers
```bash
$ sudo a2enmod headers
```
Redémarrer le service pour prendre en compte l'activation des modules
```bash
sudo service apache2 restart 
Debugger le fichier de config 
```bash
$ /usr/sbin/apache2ctl configtest
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg5OTU0MzMwNCwtMTA0ODU3OTcxNyw3Mz
A5OTgxMTZdfQ==
-->