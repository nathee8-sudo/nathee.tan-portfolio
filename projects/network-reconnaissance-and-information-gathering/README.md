# Network Reconnaissance & Information Gathering

## Overview

This project demonstrates reconnaissance techniques performed in my IoD cybersecurity labs.  
The goal was to identify active hosts, enumerate services, investigate DNS records, and gather information about a target system using open-source tools.

All screenshots and outputs in this project come directly from:

- Lab 5.1 – Reconnaissance & Information Gathering
- Lab 5.2 – Gaining Access (Recon only)
- Lab 5.3 – DVWA & Pen Testing (Recon only)

These labs form the foundation of the reconnaissance workflow.

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

## Part 1 – Host Discovery

Host discovery was performed using Nmap’s default scanning behavior, which identifies live hosts before deeper enumeration.

### Nmap Host Discovery

```bash
nmap <target>
```

#### Screenshots

- Nmap output showing “Host is up”
- List of discovered hosts
- MAC address and vendor information

---

## Part 2 – DNS Enumeration

DNS investigation was performed using `dig` and `nslookup`.

### dig ANY

```bash
dig ANY <domain>
```

### dig MX

```bash
dig MX <domain>
```

### nslookup

```bash
nslookup <domain>
```

#### Screenshots

- `dig ANY` output
- MX records
- `nslookup` results

---

## Part 3 – WHOIS Lookup

WHOIS was used to gather domain registration details.

### WHOIS Command

```bash
whois <domain>
```

#### Screenshots

- WHOIS output showing registrar
- DNS servers
- Contact information

---

## Part 4 – Port Scanning & Service Enumeration

Service enumeration was performed using Nmap version detection and full port scans.

### Version Detection

```bash
nmap -sV <target>
```

### Full Port Scan

```bash
nmap -p- <target>
```

#### Screenshots

- Open ports
- Service versions (Apache, SSH, FTP, MySQL, etc.)
- Version banners

---

## Part 5 – Operating System Detection

OS fingerprinting was performed using Nmap’s OS detection capabilities.

### OS Detection

```bash
nmap -O <target>
```

#### Screenshots

- OS guess
- TCP/IP fingerprinting results

---

## Security Findings

Examples based on lab results:

- Multiple open ports exposed
- Outdated service versions
- Web server information leakage
- DNS records revealing internal details
- WHOIS data exposing administrative contacts

---

## Recommendations

- Close unused ports
- Restrict SSH access
- Update outdated services
- Implement firewall rules
- Limit DNS exposure
- Enforce network segmentation

---

## Skills Demonstrated

- Network scanning
- Host discovery
- DNS enumeration
- WHOIS investigation
- Service identification
- OS fingerprinting
- Security analysis
- Documentation and reporting

---

## Key Takeaways

This project provided hands-on experience performing reconnaissance and analyzing network exposure.  
Understanding how attackers gather information helps strengthen defensive strategies and improve network security posture.
