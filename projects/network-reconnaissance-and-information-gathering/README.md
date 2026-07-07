# Network Reconnaissance & Information Gathering  
### Using Nmap, WHOIS, dig, DNS Enumeration & OS Detection  
### By Nathee Tan

---

## 📌 Overview

This project demonstrates practical reconnaissance techniques used to identify hosts, services, and potential security risks within a network.  
It is based on my IoD cybersecurity labs, specifically **Lab 5.1 – Reconnaissance & Information Gathering**.

The goal is to simulate the early stages of a security assessment by collecting information about a target system using open‑source tools.

---

## 🧪 Lab Environment

- Kali Linux (VM)
- Target machine (Metasploitable / DVWA / local VM)
- Tools used:
  - `nmap`
  - `whois`
  - `dig`
  - `nslookup`
  - Google Dorking techniques

---

## 🔍 1. Host Discovery

Identify active hosts on the network.

Commands used:

```bash
nmap -sn 192.168.1.0/24
