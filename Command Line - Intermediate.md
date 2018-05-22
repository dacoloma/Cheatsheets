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
# C program
## Compiling
```shell
gcc -o hello hello.c
```
## Running
```shell
./hello
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNjE1ODc3MjgsNzI0OTQ1NjA4LC00Nj
c2MTQxNDQsLTE0NjcwNzYzMTgsLTE2MjQ1MTQ5MjEsLTczMTQy
NzIwOCwtMTU0OTgwODc3NCwyNDI0MTMyNjAsMTI4MjEwNzA5My
wtMTMxMDIzMjkxOF19
-->