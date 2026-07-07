<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Network Reconnaissance & Information Gathering</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 40px; line-height: 1.6; }
    h1, h2, h3 { color: #2c3e50; }
    hr { margin: 24px 0; }
    code { background: #f4f4f4; padding: 2px 4px; border-radius: 3px; }
    pre { background: #f4f4f4; padding: 10px; border-radius: 4px; overflow-x: auto; }
    ul { margin-left: 20px; }
  </style>
</head>
<body>

  <h1>Network Reconnaissance &amp; Information Gathering</h1>
  <p><em>A practical demonstration of host discovery, DNS enumeration, service identification, and OS fingerprinting using industry‑standard tools.</em></p>

  <hr>

  <h2>Overview</h2>
  <p>
    This project demonstrates my ability to perform <strong>network reconnaissance</strong> using open‑source tools such as
    <strong>Nmap</strong>, <strong>WHOIS</strong>, <strong>dig</strong>, and DNS enumeration techniques. It is based directly on my IoD
    cybersecurity labs and showcases real‑world skills used in IT support, cybersecurity, and system administration.
  </p>
  <p>
    The goal is to simulate a small network assessment and identify active hosts, exposed services, and potential risks — similar to what a
    junior analyst or technician would perform during troubleshooting or security review.
  </p>

  <hr>

  <h2>Objectives</h2>
  <ul>
    <li>Discover active hosts on a network</li>
    <li>Enumerate open ports and running services</li>
    <li>Identify DNS records</li>
    <li>Perform WHOIS lookups</li>
    <li>Detect operating systems</li>
    <li>Interpret results and provide security recommendations</li>
  </ul>

  <hr>

  <h2>Lab Environment</h2>
  <ul>
    <li><strong>Kali Linux</strong></li>
    <li><strong>Nmap</strong></li>
    <li><strong>dig</strong></li>
    <li><strong>WHOIS</strong></li>
    <li><strong>Local VirtualBox network</strong></li>
    <li>Screenshots taken from:
      <ul>
        <li>Lab 5.1 – Reconnaissance &amp; Information Gathering</li>
        <li>Lab 5.2 – Gaining Access (Recon only)</li>
        <li>Lab 5.3 – DVWA &amp; Pen Testing (Recon only)</li>
      </ul>
    </li>
  </ul>

  <hr>

  <h2>1. Host Discovery</h2>
  <p>Commands used:</p>
  <pre><code>nmap -sn &lt;target-range&gt;</code></pre>
  <p><strong>Screenshots to include:</strong></p>
  <ul>
    <li>Nmap ping sweep</li>
    <li>ARP discovery (if performed)</li>
    <li>List of active hosts</li>
  </ul>

  <hr>

  <h2>2. DNS Enumeration</h2>
  <p>Commands used:</p>
  <pre><code>dig ANY &lt;domain&gt;
dig NS &lt;domain&gt;
dig MX &lt;domain&gt;
nslookup &lt;domain&gt;</code></pre>
  <p><strong>Screenshots to include:</strong></p>
  <ul>
    <li>dig ANY output</li>
    <li>NS/MX records</li>
    <li>nslookup results</li>
  </ul>

  <hr>

  <h2>3. WHOIS Lookup</h2>
  <p>Command used:</p>
  <pre><code>whois &lt;domain&gt;</code></pre>
  <p><strong>Screenshots to include:</strong></p>
  <ul>
    <li>WHOIS output showing registrar, DNS servers, contact info</li>
  </ul>

  <hr>

  <h2>4. Port Scanning &amp; Service Enumeration</h2>
  <p>Commands used:</p>
  <pre><code>nmap -sS &lt;target&gt;
nmap -sV &lt;target&gt;
nmap -p- &lt;target&gt;</code></pre>
  <p><strong>Screenshots to include:</strong></p>
  <ul>
    <li>Open ports</li>
    <li>Service versions</li>
    <li>Apache/SSH/FTP/MySQL banners</li>
  </ul>

  <hr>

  <h2>5. Operating System Detection</h2>
  <p>Command used:</p>
  <pre><code>nmap -O &lt;target&gt;</code></pre>
  <p><strong>Screenshots to include:</strong></p>
  <ul>
    <li>OS fingerprinting results</li>
    <li>TCP/IP signature guess</li>
  </ul>

  <hr>

  <h2>Security Findings</h2>
  <p>Examples (replace with your actual results):</p>
  <ul>
    <li>Unnecessary open ports</li>
    <li>Outdated services</li>
    <li>Exposed DNS records</li>
    <li>Weak SSH configuration</li>
    <li>Information leakage through WHOIS</li>
  </ul>

  <hr>

  <h2>Recommendations</h2>
  <ul>
    <li>Close unused ports</li>
    <li>Restrict SSH access</li>
    <li>Patch outdated services</li>
    <li>Implement firewall rules</li>
    <li>Disable DNS zone transfers</li>
    <li>Enforce network segmentation</li>
  </ul>

  <hr>

  <h2>Skills Demonstrated</h2>
  <ul>
    <li>Network scanning</li>
    <li>Host discovery</li>
    <li>DNS enumeration</li>
    <li>WHOIS analysis</li>
    <li>OS fingerprinting</li>
    <li>Service identification</li>
    <li>Security interpretation</li>
    <li>Documentation &amp; reporting</li>
  </ul>

  <hr>

  <h2>Lessons Learned</h2>
  <ul>
    <li>Reconnaissance is the foundation of both offensive and defensive security</li>
    <li>DNS and WHOIS often reveal more than expected</li>
    <li>Small misconfigurations can expose critical information</li>
    <li>Proper documentation is essential for real‑world security work</li>
  </ul>

  <hr>

  <h2>Repository Structure</h2>
  <pre><code>network-reconnaissance-and-information-gathering/
│
├── README.md
└── screenshots/
    ├── host-discovery.png
    ├── dns-enumeration.png
    ├── whois.png
    ├── port-scan.png
    ├── os-detection.png</code></pre>

  <hr>

  <h2>Project Status</h2>
  <p>Completed using IoD Labs:</p>
  <ul>
    <li>Lab 5.1 – Reconnaissance &amp; Information Gathering</li>
    <li>Lab 5.2 – Gaining Access (Recon only)</li>
    <li>Lab 5.3 – DVWA &amp; Pen Testing (Recon only)</li>
  </ul>

</body>
</html>

Lab 5.2 – Gaining Access

Lab 5.3 – DVWA & Pen Testing
