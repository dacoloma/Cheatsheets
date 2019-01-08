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
	ether 10:dd:b1:b9:2c:de
	inet6 fe80::c09:d075:22a2:aff0%en0 prefixlen 64 secured scopeid 0x4
	inet 10.11.8.1 netmask 0xffff0000 broadcast 10.11.255.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect (1000baseT <full-duplex>)
	status: active
```
###
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NjA0Nzg5ODNdfQ==
-->