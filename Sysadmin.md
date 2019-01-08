# Sysadmin
## ifconfig
Configure network interface
### Display all network interfaces without info
```bash
$ ifconfig -l
```
### Get parameters of specific network interface
```bash
$ ifconfig en0 
```
```
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

## traceroute

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNjczMzAzMTddfQ==
-->