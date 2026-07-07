Network Reconnaissance & Information Gathering
A practical demonstration of host discovery, DNS enumeration, service identification, and OS fingerprinting using industry‑standard tools.

📌 Overview
This project showcases my ability to perform network reconnaissance using open‑source tools such as Nmap, WHOIS, dig, and DNS enumeration techniques.
It is based directly on my IoD labs and demonstrates real‑world skills used in cybersecurity, IT support, and system administration.

The goal is to simulate a small network assessment and identify active hosts, exposed services, and potential risks — similar to what a junior analyst or technician would perform during troubleshooting or security review.

🎯 Objectives
Discover active hosts on a network

Enumerate open ports and running services

Identify DNS records

Perform WHOIS lookups

Detect operating systems

Interpret results and provide security recommendations

🧪 Lab Environment
Kali Linux

Nmap

dig

WHOIS

Local virtual network

Screenshots taken directly from IoD labs (3.1, 5.1, 5.2, 5.3)

🔍 Reconnaissance Steps
1. Host Discovery
Techniques demonstrated:

nmap -sn

ARP ping scans

ICMP echo scans

📸 Screenshot to include:  
Your Nmap host discovery output from Lab 5.1.

2. Port Scanning
Techniques demonstrated:

SYN scan

Version detection

Service enumeration

Commands used:

Code
nmap -sS -sV <target>
📸 Screenshot to include:  
Your Nmap port scan results showing open ports (Lab 5.2 / 5.3).

3. Service Enumeration
Identifying:

HTTP

SSH

FTP

MySQL

Apache

Other services discovered during scans

📸 Screenshot to include:  
Service version detection output.

4. DNS Investigation
Using:

Code
dig A <domain>
dig MX <domain>
dig NS <domain>
📸 Screenshot to include:  
Your DNS record lookup from Lab 5.1.

5. WHOIS Analysis
Using:

Code
whois <domain>
📸 Screenshot to include:  
WHOIS output showing registrar + contact info.

6. OS Fingerprinting
Using:

Code
nmap -O <target>
📸 Screenshot to include:  
Your OS detection results.

⚠️ Security Findings
Examples (replace with your actual results):

Unnecessary open ports

Services running outdated versions

Missing firewall rules

Publicly exposed DNS records

Weak server fingerprinting protections

🛡️ Recommendations
Close unused ports

Restrict SSH access

Update vulnerable services

Implement firewall rules

Hide unnecessary DNS records

Enforce network segmentation

📚 Skills Demonstrated
Network scanning

Host discovery

DNS enumeration

WHOIS analysis

OS fingerprinting

Service identification

Security interpretation

Documentation & reporting

📝 Lessons Learned
Reconnaissance reveals more than people expect

DNS records often leak sensitive information

Even small networks expose multiple attack surfaces

Proper documentation is essential for real‑world security work

✔️ Project Status
Completed using IoD Labs:

Lab 3.1 – Capturing Traffic

Lab 5.1 – Reconnaissance & Information Gathering

Lab 5.2 – Gaining Access

Lab 5.3 – DVWA & Pen Testing
