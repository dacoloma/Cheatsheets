# Command Line - Intermediate
## chmod
```shell
chmod u=rwx myfile
```
```shell
chmod u-x myfile
```
```shell
chmod g,o=u myfile
```

## Kerberos ticket
> https://blog.devensys.com/kerberos-principe-de-fonctionnement/
> https://web.mit.edu/kerberos/krb5-1.11/doc/user/tkt_mgmt.html
### kinit
### klist
## find 
### Find matching pattern file(s)
```shell
find . -iname "*pat*"
```
### Search & destroy
```shell
find . -iname *pat* -delete
```
### Counting directories and files
```shell
find  . -depth | wc -l
```

## diff / patch
```shell
diff -u fileA fileB > sw.diff
patch fileC sw.diff
```
## file
## Magic files
## ifconfig
### MAC addresses 
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

https://vim.rtorr.com/
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYyNzE4OTA5MCwtNjc1Nzc5MDc4LC0xMD
YxNTg3NzI4LDcyNDk0NTYwOCwtNDY3NjE0MTQ0LC0xNDY3MDc2
MzE4LC0xNjI0NTE0OTIxLC03MzE0MjcyMDgsLTE1NDk4MDg3Nz
QsMjQyNDEzMjYwLDEyODIxMDcwOTMsLTEzMTAyMzI5MThdfQ==

-->