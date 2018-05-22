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
# ifconfig
## MAC addresses 
```shell
ifconfig | grep ether
```
# Compiling a C program
```shell
gcc

-

o hello hello.c
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYzMTAyODI5NSw3MjQ5NDU2MDgsLTQ2Nz
YxNDE0NCwtMTQ2NzA3NjMxOCwtMTYyNDUxNDkyMSwtNzMxNDI3
MjA4LC0xNTQ5ODA4Nzc0LDI0MjQxMzI2MCwxMjgyMTA3MDkzLC
0xMzEwMjMyOTE4XX0=
-->