# Lab 7 - Wireshark

## TASK 7

ANSWER
## Question 1: Analyse packet1.pcap and find the flag. 

<img width="605" height="279" alt="image" src="https://github.com/user-attachments/assets/b5a6f76c-7d78-4c57-83d3-1d0e200f7a6b" />

<img width="450" height="228" alt="image" src="https://github.com/user-attachments/assets/16e10f95-7124-4edf-abad-ebc39c0003d4" />

## Question 2: Analyse packet2.pcap and find the flag. 


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

## 3. Highest Risk
Port 445 (SMB)
-	Remote code execution 
-	Wormable (spreads automatically) 
-	Used in ransomware (e.g. WannaCry)

## 4. Attack Path
Example attack chain:
1.	Scan target (Nmap) 
2.	Exploit SMB (EternalBlue) 
3.	Gain shell access 
4.	Move laterally 
5.	Access FTP / Web data

## 5. Remediation
-	Disable unused ports 
-	Update software 
-	Patch Windows (MS17-010) 
-	Use strong passwords 
-	Firewall rules

## Question 4: Identify the OS (OS Fingerprinting) - TTL
The TTL value observed is 128, which indicates the system is likely running Windows OS.
Image 1 : TTL 64 = Linux.  

Image 2 : TTL 128 = Windows.  

Image 3 : TTL 255 = Network Device.

## Question 5: Analyse the Nessus file
Nessus Scanning result.

<img width="1919" height="890" alt="Screenshot 2026-05-01 015208" src="https://github.com/user-attachments/assets/6395a366-0a26-4310-845b-7f5f69ac3a19" />

<img width="1916" height="884" alt="Screenshot 2026-05-01 015304" src="https://github.com/user-attachments/assets/4d6eb03a-6f51-4837-8028-f80b00a0f012" />

<img width="1919" height="886" alt="Screenshot 2026-05-01 015355" src="https://github.com/user-attachments/assets/7aa7ef2f-aecc-4450-86f0-50eb1cc25d8a" />

<img width="1919" height="844" alt="Screenshot 2026-05-01 015952" src="https://github.com/user-attachments/assets/0881c893-b030-461b-b640-4b12d46c53af" />


1.	What is the affected Port number
Answer: 8009

2.	What is the Affected protocol
Answer: 
