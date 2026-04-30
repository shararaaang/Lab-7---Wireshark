# Lab 7 - Wireshark

## TASK 7

ANSWER
Question 1: Analyse packet1.pcap and find the flag. 

<img width="605" height="279" alt="image" src="https://github.com/user-attachments/assets/b5a6f76c-7d78-4c57-83d3-1d0e200f7a6b" />

<img width="450" height="228" alt="image" src="https://github.com/user-attachments/assets/16e10f95-7124-4edf-abad-ebc39c0003d4" />



## Question 3: Interpret an Nmap Output
1.	What can an attacker do with each port?
2.	What vulnerabilities are likely present based on the version?
3.	Which one is the highest risk and why?
4.	What attack path can be built from this?
5.	What should be the remediation?

## 1. What attacker can do
- Port 21 (FTP)
Upload/download files
Anonymous login attack 
-	Port 22 (SSH)
Brute-force login
Remote access
-	Port 80 (HTTP)
Website attacks (SQLi, XSS) 
-	Port 139 & 445 (SMB)
File sharing access
Exploit Windows vulnerabilities

## 2. Vulnerabilities
-	vsftpd 2.3.4
Backdoor vulnerability (very famous) 
-	OpenSSH 5.3
Old version - possible brute-force & weak crypto 
-	Apache 2.2.8
Outdated - multiple CVEs (RCE, DoS) 
-	SMB (Windows 7 SP1)
Vulnerable to EternalBlue (MS17-010)

## 4. Highest Risk
Port 445 (SMB)
-	Remote code execution 
-	Wormable (spreads automatically) 
-	Used in ransomware (e.g. WannaCry)

## 5. Attack Path
Example attack chain:
1.	Scan target (Nmap) 
2.	Exploit SMB (EternalBlue) 
3.	Gain shell access 
4.	Move laterally 
5.	Access FTP / Web data

## 6. Remediation
-	Disable unused ports 
-	Update software 
-	Patch Windows (MS17-010) 
-	Use strong passwords 
-	Firewall rules
