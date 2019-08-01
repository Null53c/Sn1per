![alt tag](https://github.com/)

[![GitHub release](https://img.shields.io/github/release/1N3/Sn1per.svg)](https://github.com/1N3/Sn1per/releases) 
[![GitHub issues](https://img.shields.io/github/issues/1N3/Sn1per.svg)](https://github.com/1N3/Sn1per/issues) 
[![Github Stars](https://img.shields.io/github/stars/1N3/Sn1per.svg?style=social&label=Stars)](https://github.com/1N3/Sn1per/) 
[![GitHub Followers](https://img.shields.io/github/followers/1N3.svg?style=social&label=Follow)](https://github.com/1N3/Sn1per/)
[![Tweet](https://img.shields.io/twitter/url/http/xer0dayz.svg?style=social)](https://twitter.com/intent/tweet?original_referer=https%3A%2F%2Fdeveloper.twitter.com%2Fen%2Fdocs%2Ftwitter-for-websites%2Ftweet-button%2Foverview&ref_src=twsrc%5Etfw&text=Sn1per%20-%20Automated%20Pentest%20Recon%20Scanner&tw_p=tweetbutton&url=https%3A%2F%2Fgithub.com%2F1N3%2FSn1per)
[![Follow on Twitter](https://img.shields.io/twitter/follow/xer0dayz.svg?style=social&label=Follow)](https://twitter.com/intent/follow?screen_name=xer0dayz)

## ABOUT:
X is an automated scanner that can be used during a penetration test to enumerate and scan for vulnerabilities. for Professional Penetration Testers, Bug Bounty Researchers and Corporate Security teams to ..


## DEMO VIDEO:
[![Demo](https://www.google.com)

## SN1PER COMMUNITY FEATURES:
- [x] Automatically collects basic recon (ie. whois, ping, DNS, etc.)
- [x] Automatically launches Google hacking queries against a target domain
- [x] Automatically enumerates open ports via NMap port scanning
- [x] Automatically brute forces sub-domains, gathers DNS info and checks for zone transfers
- [x] Automatically checks for sub-domain hijacking
- [x] Automatically runs targeted NMap scripts against open ports
- [x] Automatically runs targeted Metasploit scan and exploit modules
- [x] Automatically scans all web applications for common vulnerabilities
- [x] Automatically brute forces ALL open services
- [x] Automatically test for anonymous FTP access
- [x] Automatically runs WPScan, Arachni and Nikto for all web services
- [x] Automatically enumerates NFS shares
- [x] Automatically test for anonymous LDAP access
- [x] Automatically enumerate SSL/TLS ciphers, protocols and vulnerabilities
- [x] Automatically enumerate SNMP community strings, services and users
- [x] Automatically list SMB users and shares, check for NULL sessions and exploit MS08-067
- [x] Automatically exploit vulnerable JBoss, Java RMI and Tomcat servers
- [x] Automatically tests for open X11 servers
- [x] Auto-pwn added for Metasploitable, ShellShock, MS08-067, Default Tomcat Creds
- [x] Performs high level enumeration of multiple hosts and subnets
- [x] Automatically integrates with Metasploit Pro, MSFConsole and Zenmap for reporting
- [x] Automatically gathers screenshots of all web sites
- [x] Create individual workspaces to store all scan output


## KALI LINUX INSTALL:
```
bash install.sh
```

## UBUNTU/DEBIAN/PARROT INSTALL:
```
bash install_debian_ubuntu.sh
```

## DOCKER INSTALL:
```
sudo docker build -t sn1per-docker . && docker run -it sn1per-docker /bin/bash
```

## USAGE:
```
[*] NORMAL MODE
sniper -t|--target <TARGET>

[*] NORMAL MODE + OSINT + RECON + FULL PORT SCAN + BRUTE FORCE
sniper -t|--target <TARGET> -o|--osint -re|--recon -fp|--fullportonly -b|--bruteforce

[*] STEALTH MODE + OSINT + RECON
sniper -t|--target <TARGET> -m|--mode stealth -o|--osint -re|--recon

[*] DISCOVER MODE
sniper -t|--target <CIDR> -m|--mode discover -w|--workspace <WORSPACE_ALIAS>

[*] FLYOVER MODE
sniper -t|--target <TARGET> -m|--mode flyover -w|--workspace <WORKSPACE_ALIAS>

[*] AIRSTRIKE MODE
sniper -f|--file /full/path/to/targets.txt -m|--mode airstrike

[*] NUKE MODE WITH TARGET LIST, BRUTEFORCE ENABLED, FULLPORTSCAN ENABLED, OSINT ENABLED, RECON ENABLED, WORKSPACE & LOOT ENABLED
sniper -f--file /full/path/to/targets.txt -m|--mode nuke -w|--workspace <WORKSPACE_ALIAS>

[*] SCAN ONLY SPECIFIC PORT
sniper -t|--target <TARGET> -m port -p|--port <portnum>

[*] FULLPORTONLY SCAN MODE
sniper -t|--target <TARGET> -fp|--fullportonly

[*] PORT SCAN MODE
sniper -t|--target <TARGET> -m|--mode port -p|--port <PORT_NUM>

[*] WEB MODE - PORT 80 + 443 ONLY!
sniper -t|--target <TARGET> -m|--mode web

[*] HTTP WEB PORT HTTP MODE
sniper -t|--target <TARGET> -m|--mode webporthttp -p|--port <port>

[*] HTTPS WEB PORT HTTPS MODE
sniper -t|--target <TARGET> -m|--mode webporthttps -p|--port <port>

[*] WEBSCAN MODE
sniper -t|--target <TARGET> -m|--mode webscan

[*] ENABLE BRUTEFORCE
sniper -t|--target <TARGET> -b|--bruteforce

[*] ENABLE LOOT IMPORTING INTO METASPLOIT
sniper -t|--target <TARGET>

[*] LOOT REIMPORT FUNCTION
sniper -w <WORKSPACE_ALIAS> --reimport

[*] LOOT REIMPORTALL FUNCTION
sniper -w <WORKSPACE_ALIAS> --reimportall

[*] DELETE WORKSPACE
sniper -w <WORKSPACE_ALIAS> -d

[*] DELETE HOST FROM WORKSPACE
sniper -w <WORKSPACE_ALIAS> -t <TARGET> -dh

[*] SCHEDULED SCANS'
sniper -w <WORKSPACE_ALIAS> -s daily|weekly|monthly'

[*] SCAN STATUS
sniper --status

[*] UPDATE SNIPER
sniper -u|--update
```
## DOCKER USAGE:
```
### After the Docker installation is successfull:

#### A) Run container and get a shell:
docker run -it sn1per-docker /bin/bash

#### B) Run a container, run sniper and get a shell (better integration):
docker run -it sn1per-docker sniper $@ -t <TARGET>

#### C) Even better you can create an alias:
alias sniper='docker run -it sn1per-docker sniper $@'
sniper -t <TARGET>
```

### MODES:
* **NORMAL:** Performs basic scan of targets and open ports using both active and passive checks for optimal performance.
* **STEALTH:** Quickly enumerate single targets using mostly non-intrusive scans to avoid WAF/IPS blocking.
* **FLYOVER:** Fast multi-threaded high level scans of multiple targets (useful for collecting high level data on many hosts quickly).
* **AIRSTRIKE:** Quickly enumerates open ports/services on multiple hosts and performs basic fingerprinting. To use, specify the full location of the file which contains all hosts, IPs that need to be scanned and run ./sn1per /full/path/to/targets.txt airstrike to begin scanning.
* **NUKE:** Launch full audit of multiple hosts specified in text file of choice. Usage example: ./sniper /pentest/loot/targets.txt nuke. 
* **DISCOVER:** Parses all hosts on a subnet/CIDR (ie. 192.168.0.0/16) and initiates a sniper scan against each host. Useful for internal network scans.
* **PORT:** Scans a specific port for vulnerabilities. Reporting is not currently available in this mode.
* **FULLPORTONLY:** Performs a full detailed port scan and saves results to XML.
* **WEB:** Adds full automatic web application scans to the results (port 80/tcp & 443/tcp only). Ideal for web applications but may increase scan time significantly.
* **WEBPORTHTTP:** Launches a full HTTP web application scan against a specific host and port.
* **WEBPORTHTTPS:** Launches a full HTTPS web application scan against a specific host and port.
* **WEBSCAN:** Launches a full HTTP & HTTPS web application scan against via Burpsuite and Arachni.

## LICENSE:
This software is free to distribute, modify and use with the condition that credit is provided to the creator (@xer0dayz @XeroSecurity) and is not for commercial use or resold and rebranded. Permission to distribute any part of the code for sale is strictly prohibited.

## LEGAL DISCLAIMER:
You may not rent or lease, distribute, modify, sell or transfer the software to a third party. Sn1per Community is free for distribution, and modification with the condition that credit is provided to the creator and not used for commercial use. You may not use software for illegal or nefarious purposes. No liability for consequential damages to the maximum extent permitted by all applicable laws. In no event shall XeroSecurity or any person be liable for any consequential, reliance, incidental, special, direct or indirect damages whatsoever (including without limitation, damages for loss of business profits, business interruption, loss of business information, personal injury, or any other loss) arising out of or in connection with the use or inability to use this product, even if XeroSecurity has been advised of the possibility of such damages. 

## COPYRIGHT:
The software code and logos are owned by XeroSecurity and protected by United States copyright and/or patent laws of international treaty provisions. All rights reserved.
