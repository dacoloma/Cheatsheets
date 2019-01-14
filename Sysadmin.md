# Sysadmin (OSX, Debian)
https://www.vagrantup.com/docs/vagrantfile/
https://misc.flogisoft.com/bash/tip_colors_and_formatting
1. [ifconfig](#ifconfig)
2. [netstat](#netstat)
3. [dig / host](#dig-/-host)
4. [whois](#whois)
5. [ping](#ping)
6. [traceroute](#traceroute)
## ifconfig
Configure network interface
### Display all network interfaces without info
```bash
$ ifconfig -l
```
> -l : display only network interface names
### Get parameters of specific network interface
```bash
$ ifconfig en0 | grep ether
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
options=10b<RXCSUM,TXCSUM,VLAN_HWTAGGING,AV>
ether XX:XX:XX:XX:XX:XX
inet6 XXXX::XXXX:XXXX:XXXX:XXXX%en0 prefixlen 64 secured scopeid 0x4
inet 10.11.8.1 netmask 0xffff0000 broadcast 10.11.255.255
nd6 options=201<PERFORMNUD,DAD>
media: autoselect (1000baseT <full-duplex>)
status: active
```
> ether : MAC address
> inet : IPv4 address | netmask | broadcast address
> inet6 : IPv6 address
## netstat
Show network status
### Routing table
```bash
$ netstat -nr
```
## dig / host
Query DNS[^1]  interactively. nslookup is deprecated.

### Query DNS server to get IP address of a website
```bash
$ dig github.com
; <<>> DiG 9.8.3-P1 <<>> github.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 38576
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 8, ADDITIONAL: 8

;; QUESTION SECTION:
;github.com.			IN	A

;; ANSWER SECTION:
github.com.		56	IN	A	140.82.118.4
github.com.		56	IN	A	140.82.118.3

;; AUTHORITY SECTION:
github.com.		100095	IN	NS	ns-1707.awsdns-21.co.uk.
github.com.		100095	IN	NS	ns-520.awsdns-01.net.
github.com.		100095	IN	NS	ns4.p16.dynect.net.
github.com.		100095	IN	NS	ns1.p16.dynect.net.
github.com.		100095	IN	NS	ns3.p16.dynect.net.
github.com.		100095	IN	NS	ns-1283.awsdns-32.org.
github.com.		100095	IN	NS	ns2.p16.dynect.net.
github.com.		100095	IN	NS	ns-421.awsdns-52.com.

;; ADDITIONAL SECTION:
ns1.p16.dynect.net.	7603	IN	A	208.78.70.16
ns2.p16.dynect.net.	7603	IN	A	204.13.250.16
ns3.p16.dynect.net.	7603	IN	A	208.78.71.16
ns4.p16.dynect.net.	7603	IN	A	204.13.251.16
ns-421.awsdns-52.com.	2992	IN	A	205.251.193.165
ns-520.awsdns-01.net.	4519	IN	A	205.251.194.8
ns-1283.awsdns-32.org.	4519	IN	A	205.251.197.3
ns-1707.awsdns-21.co.uk. 4519	IN	A	205.251.198.171

;; Query time: 2 msec
;; SERVER: 10.51.1.42#53(10.51.1.42)
;; WHEN: Wed Jan  9 11:17:29 2019
;; MSG SIZE  rcvd: 408
```
> 10.51.1.42 is the default DNS server.
> In OS X, the default DNS IP address can be found (and configured) in /etc/resolv.conf
### Query an specific DNS server
```bash
$ dig 8.8.8.8 github.com
; <<>> DiG 9.8.3-P1 <<>> @8.8.8.8 slash16.org
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 25406
;; flags: qr rd ra; QUERY: 1, ANSWER: 4, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;slash16.org.			IN	A

;; ANSWER SECTION:
slash16.org.		7	IN	A	143.204.194.143
slash16.org.		7	IN	A	143.204.194.182
slash16.org.		7	IN	A	143.204.194.136
slash16.org.		7	IN	A	143.204.194.122

;; Query time: 6 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Wed Jan  9 11:18:19 2019
;; MSG SIZE  rcvd: 93

```
> 8.8.8.8 : Google public DNS address


## whois
Internet domain name and network number directory service
```bash
$ whois google.com
Domain Name: GOOGLE.COM
Registry Domain ID: 2138514_DOMAIN_COM-VRSN
Registrar WHOIS Server: whois.markmonitor.com
Registrar URL: http://www.markmonitor.com
Updated Date: 2018-02-21T18:36:40Z
Creation Date: 1997-09-15T04:00:00Z
Registry Expiry Date: 2020-09-14T04:00:00Z
Registrar: MarkMonitor Inc.
Registrar IANA ID: 292
Registrar Abuse Contact Email: abusecomplaints@markmonitor.com
Registrar Abuse Contact Phone: +1.2083895740
Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
Domain Status: serverDeleteProhibited https://icann.org/epp#serverDeleteProhibited
Domain Status: serverTransferProhibited https://icann.org/epp#serverTransferProhibited
Domain Status: serverUpdateProhibited https://icann.org/epp#serverUpdateProhibited
Name Server: NS1.GOOGLE.COM
Name Server: NS2.GOOGLE.COM
Name Server: NS3.GOOGLE.COM
Name Server: NS4.GOOGLE.COM
DNSSEC: unsigned
URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of whois database: 2019-01-08T13:08:27Z <<<
[...]
```
## ping
Send ICMP ECHO_REQUEST packets to network hosts
```bash
$ ping -c 2 github.com
PING github.com (140.82.118.4): 56 data bytes
64 bytes from 140.82.118.4: icmp_seq=0 ttl=56 time=12.215 ms
64 bytes from 140.82.118.4: icmp_seq=1 ttl=56 time=12.184 ms
--- github.com ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 12.184/12.200/12.215/0.015 ms
```
> -c _count_ : stop after sending and receiving _count_ packets (In the example, after 2 packets)
## traceroute
Print the route packets take to network host
```bash
$ traceroute google.fr
$ traceroute to google.fr (216.58.198.195), 64 hops max, 52 byte packets
1  10.11.254.254 (10.11.254.254)  3.023 ms  1.296 ms  0.853 ms
2  nat-1 (10.60.1.11)  0.211 ms  0.174 ms  0.233 ms
3  dc3 (62.210.35.1)  1.938 ms  1.838 ms  1.799 ms
4  195.154.1.174 (195.154.1.174)  1.097 ms  1.063 ms  1.901 ms
5  a9k2-45x-s44-2.dc3.poneytelecom.eu (195.154.1.106)  1.230 ms  1.085 ms  1.066 ms
6  209.85.149.12 (209.85.149.12)  1.434 ms  1.369 ms  1.297 ms
7  108.170.244.161 (108.170.244.161)  1.309 ms	
   108.170.244.225 (108.170.244.225)  2.470 ms
   108.170.244.161 (108.170.244.161)  1.301 ms
8  108.170.232.125 (108.170.232.125)  1.368 ms  1.394 ms  1.359 ms
9  par10s27-in-f195.1e100.net (216.58.198.195)  1.417 ms  1.241 ms  1.428 ms
```
## hostnamectl
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
#### Error after reinstalling openssh-server
```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
[...]
Please contact your system administrator.
```
After reinstalling ssh server, a new connection has been established. That means new ssh key as well. You need to regenerate them :
```bash
$ ssh-keygen -R 10.11.200.163
# Host 10.11.200.163 found: line 7
/Users/user/.ssh/known_hosts updated.
Original contents retained as /Users/user/.ssh/known_hosts.old
```
#### File transfer
```bash
$ scp user@file_to_transfer:/path/to/file /path/to/copy_file
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




## User & Group
https://doc.ubuntu-fr.org/tutoriel/gestion_utilisateurs_et_groupes_en_ligne_de_commande
### List of all users
```bash
# Debian command
$ getent passwd
# Or
$ cat /etc/passwd | cut -d: -f 1
```
> To understand /etc/passwd file : https://www.cyberciti.biz/faq/understanding-etcpasswd-file-format/
### List of all groups
```bash
# Debian command
$ getent passwd
# Or
$ cat /etc/group | cut -d: -f 1
```
### Add user
```bash
$ adduser new_user 
```
### Delete a user
```bash
$ deluser user 
```
If the user is logged in, execute the following command then delete the user :
```bash
$ killall -u user
```
### Add a group
```bash
$ addgroup group_name
```
### Add user to a group
User must be created first
```bash
$ adduser user group_name
```
### Delete a group
```bash
$ delgroup nom_groupe
```
*[DNS]: Domain Name Server
*[SSH]: Secure Shell
[^1]: The Domain Name Server. Comme un annuaire pour site web. On cherche un Nom de domaine (= Nom de famille) et on trouve l'adresse correspondante (= le numéro de téléphone). There DNS all over the world.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA2MjcxMjY5MiwxNTc2NDg4MDkzLDE2NT
MxMTk3MjcsNjc3NjU3MjEyLDEyMjY3NzE5NDcsMTE5NTE0NjUz
NCwtMTQ3NTU3MjM5MiwtMTEyMTMyNzk1Miw4MTM1NjI3MDFdfQ
==
-->