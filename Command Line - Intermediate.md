# chmod
```shell
chmod u=rwx myfile
```
```shell
chmod u-x myfile
```
```shell
chmod g,o=u myfile
```

# Kerberos ticket
> https://blog.devensys.com/kerberos-principe-de-fonctionnement/
> https://web.mit.edu/kerberos/krb5-1.11/doc/user/tkt_mgmt.html
## kinit
## klist
# find 
## Find matching pattern file(s)
```shell
find . -iname "*pat*"
```
## Search & destroy
```shell
find . -in
## Counting directories and files
```shell
find  . -depth | wc -l
```

# diff / patch
```shell
diff -u fileA fileB > sw.diff
patch fileC sw.diff
```
# file
# Magic files
 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMjkzNzA2NjgsLTE2MjQ1MTQ5MjEsLT
czMTQyNzIwOCwtMTU0OTgwODc3NCwyNDI0MTMyNjAsMTI4MjEw
NzA5MywtMTMxMDIzMjkxOF19
-->