# Secure Apache Web Server Deployment (HTTPS + SSL + Firewall + Hardening)

## Overview

This project documents the deployment and hardening of an Apache web server with HTTPS using SSL/TLS, firewall configuration, and common system hardening steps. The lab demonstrates installing and configuring Apache, obtaining and configuring TLS certificates (Let's Encrypt / certbot), tuning SSL parameters for security, configuring a host-based firewall, and implementing basic server hardening.

---

## Objectives

The objectives of this project are to:

- Install and configure Apache HTTP Server.
- Enable HTTPS using trusted SSL/TLS certificates.
- Configure strong TLS settings and disable weak ciphers and protocols.
- Configure a host firewall to limit incoming services (e.g., UFW/iptables).
- Apply basic system and Apache hardening (file permissions, modules, headers, logging).
- Test and verify the server is secure and reachable over HTTPS.

---

## Lab Environment

### Hypervisor / Platform

- VirtualBox, VMware, or cloud instance (AWS/GCP/Azure)

### Operating System

- Ubuntu Server (20.04 / 22.04) or Debian

### Tools Used

- Apache HTTP Server (httpd / apache2)
- certbot (Let's Encrypt)
- OpenSSL
- UFW (Uncomplicated Firewall) or iptables/nftables
- curl, openssl s_client
- browser for manual verification

---

## Part 1 — Apache Installation and Basic Configuration

1. Update package index and install Apache:

```bash
sudo apt update
sudo apt install -y apache2
```

2. Verify Apache is running and enable at boot:

```bash
sudo systemctl status apache2
sudo systemctl enable --now apache2
```

3. Create a site virtual host file for your domain (example: /etc/apache2/sites-available/example.com.conf) and set DocumentRoot, ServerName, and logging.

4. Enable the site and reload Apache:

```bash
sudo a2ensite example.com.conf
sudo systemctl reload apache2
```

---

## Part 2 — Enabling HTTPS with Let's Encrypt (certbot)

1. Install certbot and the Apache plugin:

```bash
sudo apt install -y certbot python3-certbot-apache
```

2. Request and install certificate for your domain (ensure DNS A record points to the server):

```bash
sudo certbot --apache -d example.com -d www.example.com
```

3. Verify certificate renewal is configured (cron/systemd timer). Test with:

```bash
sudo certbot renew --dry-run
```

---

## Part 3 — SSL/TLS Hardening

1. Configure strong TLS in Apache config (ssl.conf or site config). Recommended settings include:

- Disable TLS 1.0 and 1.1; enable TLS 1.2 and 1.3 only.
- Use a modern cipher suite (prioritize AEAD ciphers like ECDHE_AESGCM, CHACHA20_POLY1305).
- Enable HSTS (with care) and forward secrecy.

Example snippet:

```apache
SSLProtocol -all +TLSv1.2 +TLSv1.3
SSLCipherSuite HIGH:!aNULL:!MD5:!3DES
SSLHonorCipherOrder On
Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains"
```

2. Test the server with external scanners (Mozilla SSL Configuration Generator as reference) and tools like sslscan or Qualys SSL Labs.

```bash
openssl s_client -connect example.com:443 -servername example.com
```

---

## Part 4 — Firewall Configuration

1. Using UFW (example):

```bash
sudo apt install ufw
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp   # SSH (restrict by IP if possible)
sudo ufw allow 80/tcp   # HTTP (for ACME challenges if needed)
sudo ufw allow 443/tcp  # HTTPS
sudo ufw enable
sudo ufw status verbose
```

2. If using cloud provider security groups, ensure equivalent rules exist at the network level.

---

## Part 5 — Apache and System Hardening

Key hardening steps applied:

- Disable unnecessary Apache modules (e.g., autoindex if not used):

```bash
sudo a2dismod status autoindex
sudo systemctl reload apache2
```

- Restrict directory permissions for DocumentRoot and configuration files.
- Run Apache as a dedicated non-root user (default behaviour) and verify file ownership.
- Limit information exposure by disabling server tokens and signatures in Apache:

```apache
ServerSignature Off
ServerTokens Prod
```

- Implement security headers (Content-Security-Policy, X-Content-Type-Options, X-Frame-Options) where appropriate.
- Keep system and packages up to date and review logs regularly (/var/log/apache2/).

---

## Part 6 — Testing and Verification

- Verify HTTP redirects to HTTPS and certificate details are correct in browser.
- Use curl and openssl to inspect TLS handshake and certificate chain.
- Run security scanners like open-source sslscan or sslyze and review results.
- Confirm firewall rules are active and only required ports are open.

Example test:

```bash
curl -I https://example.com
openssl s_client -connect example.com:443 -servername example.com
```

---

## Skills Demonstrated

- Apache installation and Virtual Host configuration
- TLS/SSL setup using Let's Encrypt (certbot)
- TLS/SSL hardening and cipher configuration
- Host-based firewall setup and rule management
- Apache and system hardening best practices
- Server testing and verification techniques

---

## Key Takeaways

Deploying a secure Apache web server involves multiple layers: correctly installing and configuring Apache, obtaining and maintaining valid TLS certificates, hardening TLS parameters, restricting network exposure with a firewall, and applying system-level hardening. Regular testing and timely updates are essential to maintain security.


![Apache Hardening Example](1.jpg)
