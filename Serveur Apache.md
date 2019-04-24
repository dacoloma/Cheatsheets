# Apache 
(work in progress)
Debugger le fichier de config 
```bash
$ /usr/sbin/apache2ctl configtest
```
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
```
### Configuration

```
<VirtualHost *:443>
...
# Activation du SSL
SSLEngine On

# Activation de tous les protocoles sécurisés (TLS v1.0, v1.1 et TLS v1.2) tout en désactivant les protocoles non sécurisés (SSL v2, SSL v3)
SSLProtocol All -SSLv3 -SSLv2

# On active les méthodes de chiffrement, et on désactive les méthodes de chiffrement non sécurisés (par la présence d'un !)
SSLCipherSuite HIGH:!aNULL:!MD5:!ADH:!RC4:!DH:!RSA

# Le navigateur devra choisir une méthode de chiffrement en respectant l'ordre indiquée dans SSLCipherSuite
SSLHonorCipherOrder on

# Chemin vers le certificat SSL de votre nom de domaine
SSLCertificateFile "/etc/ssl/www-nom-domaine-fr/www-nom-domaine-fr.cer"

# Chemin vers la clée privée du certificat SSL de votre nom de domaine
SSLCertificateKeyFile "/etc/ssl/www-nom-domaine-fr/www-nom-domaine-fr.key"

# Chemin vers le certificat SSL racine, puis vers le certificat SSL intermédiaire. Attention : L'ordre est important.
SSLCACertificateFile "/etc/ssl/www-nom-domaine-fr/certificat-racine.cer"
SSLCACertificateFile "/etc/ssl/www-nom-domaine-fr/certificat-intermediaire.cer"
...
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ3OTk0NTY2MywtNTg4OTc5MjQwLC0xMD
Q4NTc5NzE3LDczMDk5ODExNl19
-->