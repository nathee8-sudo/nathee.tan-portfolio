# ASD Essential 8 Security Controls – Implementation Project

## 1. Overview

The **ASD Essential 8** is a cybersecurity baseline developed by the **Australian Cyber Security Centre (ACSC)** to help organisations reduce cyber risk and uplift their security posture.

This project demonstrates the implementation of all eight controls across a mixed Windows and Linux environment, including:

- Windows 10/11
- Ubuntu 22.04
- Kali Linux
- Google Chrome
- Microsoft Edge

The goal of this project is to showcase practical system hardening, patching, access control, MFA, and backup strategies aligned with Australian government standards.

---

## 2. Environment

- Windows 10/11 Pro
- Ubuntu 22.04 LTS
- Kali Linux
- Google Chrome
- Microsoft Edge

---

## 3. Essential 8 Implementation

### 🛡️ 1. Application Whitelisting (Windows)

#### Concept
Application whitelisting ensures only approved applications can run, reducing malware execution risk.

#### Implementation
- Opened **Local Security Policy** (`secpol.msc`)
- Configured **Software Restriction Policies**
- Set default security level to **Disallowed**
- Applied policies to **All users except local administrators**
- Restricted **Trusted Publishers** management to admins
- Enabled **AppLocker** rule enforcement
- Created **Default Rules**
- Automatically generated executable rules for **Program Files**

#### Screenshots

##### Local Security Policy
![Local Security Policy](./Picture1.png)

##### Security Levels (Disallowed)
![Security Levels (Disallowed)](./Picture2.png)

##### Warning prompt
![Warning prompt](./Picture3.png)

##### Enforcement Properties
![Enforcement Properties](./Picture4.png)

##### Trusted Publishers
![Trusted Publishers](./Picture5.png)

##### AppLocker rule enforcement
![AppLocker rule enforcement](./Picture6.png)

#### Software Restriction Policies
![Software Restriction Policies](./picture12.png)

#### Default Rules creation
![Default Rules creation](./picture7.png)
![Default Rules creation](./picture10.png)

#### Automatically Generated Rules
![Automatically Generated Rules](./Picture8.png).
![Automatically Generated Rules](./Picture11.png).

#### Outcome
Only authorised applications can run, significantly reducing the attack surface.

---

### 🛠️ 2. Patch Applications (Linux)

#### Concept
Keeping applications patched prevents exploitation of known vulnerabilities.

#### Implementation
- Compared file versions using `diff`
- Used `patch` to apply changes
- Created patch files using unified diff format
- Demonstrated patching workflow using text files

#### Screenshots
- `file1.txt`
- `file2.txt`
- `man diff`
- `diff -y` output
- `diff -c` output
- `man patch`
- Creating patch file
- Running patch
- Patched file result

#### Outcome
Understanding of patching workflows and version control using Linux tools.

---

### 📄 3. Configure Microsoft Office Macro Settings

#### Concept
Macros can contain malicious code. Disabling them prevents malware execution.

#### Implementation
- Accessed **Trust Center**
- Disabled all macros
- Allowed only digitally signed macros
- Reviewed trusted locations

#### Screenshots
- Options → Trust Center
- Trust Center Settings
- Macro Settings
- Trusted Locations

#### Outcome
Reduced risk of macro-based malware.

---

### 🌐 4. User Application Hardening (Chrome & Edge)

#### Concept
Browser hardening prevents malicious scripts, ads, and insecure connections.

#### Chrome Hardening
- Enabled **Enhanced Protection**
- Forced **HTTPS-only mode**
- Blocked third-party cookies
- Reviewed permissions (location, camera, mic)

#### Edge Hardening
- Set **Tracking Prevention** to Strict
- Enabled **Potentially Unwanted App Blocking**
- Enabled **Enhanced Security Mode**

#### Screenshots
**Chrome**
- Privacy & Security
- Enhanced Protection
- Secure Connections
- Third-party cookies
- Permissions

**Edge**
- Privacy, Search & Services
- Tracking Prevention
- Exceptions
- PUA blocking
- Enhanced Security Mode

#### Outcome
Browsers hardened against common web-based threats.

---

### 🔐 5. Restrict Administrative Privileges (Linux)

#### Concept
Least privilege reduces the impact of compromised accounts.

#### Implementation
- Created group `my_group`
- Added multiple users
- Created sensitive directory and file
- Changed group ownership
- Configured directory and file permissions

#### Screenshots
- `addgroup`
- `adduser`
- group membership
- directory creation
- `chgrp`
- directory permissions
- file permissions

#### Outcome
Proper separation of privileges and secure access control.

---

### 💻 6. Patch Operating Systems

#### Windows
- Used **Windows Update**
- Checked for updates under **Update & Security**

#### Linux
Ran:

```bash
sudo apt-get update
sudo apt-get upgrade
