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
### Identifying website technologies

### Burp Suite

### Google Fu

### Social Media

### OSINT Fundamentals

## Scanning & Enumeration
## Gaining Access
## Maintaining Access
## Covering Tracks

Read:
Darknet diaries
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTczMjIzMjMzLC0yMDgxNDYzMjE0LC0xMD
E4MzYyNjcsLTQ3NDk5MDk4OCwtMTQ3MzExNTM2LC0xMjQ0MTk3
Mjk4LDc2Mjc4MjE2MiwtMTgzMTMzOTg5LDQ2MjAyNjY3NSwtMT
E3Njk1NzY5MywtMTAwNzUxMjIwOCwtNTMzNzI2ODUxLDE0NDQx
NjY5MjUsMTI5MTc5MjY0NV19
-->