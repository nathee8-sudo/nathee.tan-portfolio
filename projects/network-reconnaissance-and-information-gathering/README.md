<h1>Network Reconnaissance & Information Gathering</h1>

<h2>Overview</h2>
<p>
This project demonstrates the use of reconnaissance techniques to identify active hosts, enumerate services, investigate DNS records, and fingerprint operating systems within a target network. 
The work is based on IoD Labs 5.1, 5.2, and 5.3, and showcases practical skills used in cybersecurity and IT support roles.
</p>

<hr>

<h2>Objectives</h2>
<ul>
  <li>Discover active hosts on a network.</li>
  <li>Enumerate open ports and running services.</li>
  <li>Identify DNS records using dig and nslookup.</li>
  <li>Perform WHOIS lookups.</li>
  <li>Detect operating systems using Nmap fingerprinting.</li>
  <li>Document findings and provide security recommendations.</li>
</ul>

<hr>

<h2>Lab Environment</h2>

<h3>Operating Systems</h3>
<ul>
  <li>Kali Linux</li>
  <li>Metasploitable / DVWA target machines</li>
</ul>

<h3>Tools Used</h3>
<ul>
  <li>Nmap</li>
  <li>WHOIS</li>
  <li>dig</li>
  <li>nslookup</li>
</ul>

<hr>

<h2>Part 1 – Host Discovery</h2>
<p>
Host discovery was performed using Nmap ping sweeps and ARP scans to identify active machines on the network.
</p>

<h3>Nmap Ping Sweep</h3>
<pre><code>nmap -sn 192.168.56.0/24</code></pre>

<img src="host-discovery.jpg" alt="Host Discovery">

<hr>

<h2>Part 2 – DNS Enumeration</h2>
<p>
DNS records were enumerated using dig and nslookup to identify domain information such as A, MX, NS, and TXT records.
</p>

<h3>dig ANY</h3>
<pre><code>dig ANY example.com</code></pre>
<img src="dns-any.jpg" alt="DNS ANY Lookup">

<h3>dig NS</h3>
<pre><code>dig NS example.com</code></pre>
<img src="dns-ns.jpg" alt="DNS NS Lookup">

<h3>nslookup</h3>
<pre><code>nslookup example.com</code></pre>
<img src="nslookup.jpg" alt="nslookup Output">

<hr>

<h2>Part 3 – WHOIS Lookup</h2>
<p>
WHOIS was used to gather domain registration details, including registrar, contact information, and DNS servers.
</p>

<pre><code>whois example.com</code></pre>
<img src="whois.jpg" alt="WHOIS Output">

<hr>

<h2>Part 4 – Port Scanning & Service Enumeration</h2>
<p>
Nmap was used to enumerate open ports and identify running services on the target machine.
</p>

<h3>Version Detection</h3>
<pre><code>nmap -sV 192.168.56.101</code></pre>
<img src="service-enumeration.jpg" alt="Service Enumeration">

<h3>Full Port Scan</h3>
<pre><code>nmap -p- 192.168.56.101</code></pre>
<img src="full-port-scan.jpg" alt="Full Port Scan">

<hr>

<h2>Part 5 – Operating System Detection</h2>
<p>
Nmap OS fingerprinting was used to identify the operating system based on TCP/IP characteristics.
</p>

<pre><code>nmap -O 192.168.56.101</code></pre>
<img src="os-detection.jpg" alt="OS Detection">

<hr>

<h2>Skills Demonstrated</h2>
<ul>
  <li>Network scanning</li>
  <li>Host discovery</li>
  <li>DNS enumeration</li>
  <li>WHOIS analysis</li>
  <li>Service identification</li>
  <li>OS fingerprinting</li>
  <li>Security interpretation</li>
  <li>Documentation and reporting</li>
</ul>

<hr>

<h2>Key Takeaways</h2>
<p>
This project provided hands-on experience performing reconnaissance and analysing network exposure. 
Understanding how attackers gather information helps strengthen defensive strategies and improve network security posture.
</p>
