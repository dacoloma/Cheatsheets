# Sysadmin (OSX, Debian)
hostnamectl
### Rename hostname permanently
```bash
$ hostnamectl --set-hostname new_name
```
## service
Usage : service *SCRIPT* *COMMAND*
### Get service status
```bash
$ service ssh status
```
### (Re)Start/Stop a service
```bash
$ service ssh start
$ service ssh stop
$ service ssh restart
```
### Service : SSH
Access remote machine
#### Requirement 
```bash
$ apt-get update
#On server-side
$ apt-get install openssh-server
$ service ssh start
#On server-side
$ apt-get install openssh-client
#if ssh service is not running automatically
$ service ssh start
```
#### Open session
```bash
$ ssh user@XX.XX.XX.XX
user@10.11.200.172's password:
```
##### Select a specific port
```bash
# select port 22
$ ssh -p 22 user@XX.XX.XX.XX
user@10.11.200.172's password:
```
> To get the port ssh is listening to, read /etc/ssh/ssh_config file
#### Close session
```bash
$ logout
```
### Service : at
Execute a command/script at a specific time
#### Requirement
```bash
$ apt-get update
$ apt-get install at
# Automatically launch at boot :
$ systemctl enable --now atd.service
```
#### Example
```bash
$ at now + 1 minutes
at> echo "test at service" > test.txt
at>
# Control + d to exit at prompt
# Wait...
```
*[DNS]: Domain Name Server
*[SSH]: Secure Shell
[^1]: The Domain Name Server. Comme un annuaire pour site web. On cherche un Nom de domaine (= Nom de famille) et on trouve l'adresse correspondante (= le numéro de téléphone). There DNS all over the world.
## ifconfig
Configure network interface
```bash
$ ifconfig -l
```
> -l : display only network interface names
```bash
$ ifconfig en0 | grep ether
```
> get 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU3NzEzMDE0NCwtMTYwNDgxMTY5LDE0Nj
AzNzUxMiwtNDU1NTI1MjY5LC02ODk2NjM3MjUsOTMzMzMxMDQz
XX0=
-->