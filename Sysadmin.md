# Sysadmin
1. [ifconfig](#ifconfig)
2. [netstat](#netstat)
3. [nslookup](#nslookup)
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
## nslookup
Query internet name servers interactively
### Query DNS server to get IP address of a website
```bash
$ nslookup github.com
Server:		10.51.1.42
Address:	10.51.1.42#53

Non-authoritative answer:
Name:	github.com
Address: 140.82.118.4
Name:	github.com
Address: 140.82.118.3
```
> 10.51.1.42 is the default DNS server. 
> In OS X, the default DNS IP address can be found ( in /etc/resolv.conf
### Query an specific DSN server 
```bash
$ nslookup github.com 8.8.8.8
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
Name:	github.com
Address: 140.82.118.3
Name:	github.com
Address: 140.82.118.4
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

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3Njg3ODE3MTgsMTA1OTc5NDk1NywxMz
M2MzA4MTEwXX0=
-->