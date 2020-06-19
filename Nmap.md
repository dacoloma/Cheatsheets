

# Nmap
{{TOC}}
## Port Specification
Scan | Examples
------ | --------
Port scan all ports | `nmap 192.168.1.1 -p-`
Port scan from service name | `nmap 192.168.1.1 -p http,https`

## Scan technique
Scan | Examples
------ | --------
TCP SYN port scan (Default) |`nmap 192.168.1.1 -sS`
  TCP connect port scan (Default without root privilege) | `nmap 192.168.1.1 -sT`
UDP port scan | `nmap 192.168.1.1 -sU`
TCP ACK port scan | `nmap 192.168.1.1 -sA`
TCP Window port scan | `nmap 192.168.1.1 -sW`
TCP Maimon port scan | `nmap 192.168.1.1 -sM`

## Service and version detection
Scan | Examples
------ | --------
Attempts to determine the version of the service running on port | `nmap 192.168.1.1 -sV`
Enables OS detection, version detection, script scanning, and traceroute | `nmap 192.168.1.1 -A`


## NSE Script
Scan | Examples
------ | --------
Scan with default NSE scripts. Considered useful for discovery and safe | `nmap 192.168.1.1 -sC`



[https://resources.infosecinstitute.com/nmap/](https://resources.infosecinstitute.com/nmap/)

[https://www.frameip.com/scanner-port-tcp-udp/#72-8211nmap](https://www.frameip.com/scanner-port-tcp-udp/#72-8211nmap)


[https://nmap.org/](https://nmap.org/)



[https://www.softwaretestinghelp.com/ddos-attack-tools/](https://www.softwaretestinghelp.com/ddos-attack-tools/)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzU3Mjg4MTgsLTE2MDM0MDY0ODZdfQ
==
-->