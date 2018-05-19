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
 
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzI0OTQ1NjA4LC00Njc2MTQxNDQsLTE0Nj
cwNzYzMTgsLTE2MjQ1MTQ5MjEsLTczMTQyNzIwOCwtMTU0OTgw
ODc3NCwyNDI0MTMyNjAsMTI4MjEwNzA5MywtMTMxMDIzMjkxOF
19
-->