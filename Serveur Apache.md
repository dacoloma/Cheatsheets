# Apache

## Securité SSL/TLS
Vérifier que Apache écoute le port 443.
```bash
$ netstat -tanpu | grep "LISTEN" | grep "443"
```

Debugger le fichier de config 
```bash
$ /usr/sbin/apache2ctl configtest
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNDg1Nzk3MTcsNzMwOTk4MTE2XX0=
-->