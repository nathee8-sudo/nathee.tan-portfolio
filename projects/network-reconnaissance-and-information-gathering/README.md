# Network Reconnaissance & Information Gathering

## Overview
This project demonstrates reconnaissance techniques performed in my IoD cybersecurity labs.  
The goal was to identify active hosts, enumerate services, investigate DNS records, and gather information about a target system using open‑source tools.

---

## Objectives
- Identify active hosts on the network  
- Enumerate open ports and running services  
- Investigate DNS records  
- Perform WHOIS lookups  
- Fingerprint operating systems  
- Document findings and provide recommendations  

---

## Lab Environment

### Operating Systems
- Kali Linux  
- Metasploitable / DVWA target machines  

### Tools Used
- Nmap  
- WHOIS  
- dig  
- nslookup  

---

# Part 1 – Host Discovery

Host discovery was performed using Nmap’s default scanning behaviour, which identifies live hosts before performing deeper enumeration.

### Nmap Host Discovery
The lab used Nmap’s standard scan, which automatically performs host discovery:

```bash
nmap <target>
