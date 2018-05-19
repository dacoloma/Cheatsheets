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
find . -iname *pat* -delete
```
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
eyJoaXN0b3J5IjpbLTQ2NzYxNDE0NCwtMTQ2NzA3NjMxOCwtMT
YyNDUxNDkyMSwtNzMxNDI3MjA4LC0xNTQ5ODA4Nzc0LDI0MjQx
MzI2MCwxMjgyMTA3MDkzLC0xMzEwMjMyOTE4XX0=
-->