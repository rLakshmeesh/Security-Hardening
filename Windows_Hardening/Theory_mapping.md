# Windows System Hardening: Theory and Framework Mapping

This document explains the key steps in Windows system hardening, their purposes, and how they map to **CIS Benchmarks** and **ISO 27001 controls**.  

---

## STEP 1 — System Update and Patch Management
**Purpose:**  
Keeping the system updated ensures vulnerabilities are patched and reduces exposure to exploits.  

**CIS Mapping:**  
- CIS Control 7 – Continuous Vulnerability Management  
- CIS Windows Benchmark: Ensure automatic updates enabled  

**ISO 27001 Mapping:**  
- Annex A.12.6 – Technical vulnerability management  

---

## STEP 2 — User, Group, and Privilege Management
**Purpose:**  
Enforcing least privilege and managing accounts reduces the risk of unauthorized access and privilege escalation.  

**CIS Mapping:**  
- CIS Control 6 – Account Management  
- CIS Windows Benchmark: Remove/disable default accounts, configure UAC  

**ISO 27001 Mapping:**  
- Annex A.9.2 – User access management  
- Annex A.9.4 – System and application access control  

---

## STEP 3 — Account and Password Policies
**Purpose:**  
Strong password policies and account lockout prevent brute-force attacks and unauthorized logins.  

**CIS Mapping:**  
- CIS Control 16 – Account monitoring and control  
- CIS Windows Benchmark: Enforce password complexity, lockout, expiration  

**ISO 27001 Mapping:**  
- Annex A.9.2 – User authentication management  

---

## STEP 4 — Remote Access and RDP Hardening
**Purpose:**  
Securing remote access prevents attackers from exploiting exposed services like RDP.  

**CIS Mapping:**  
- CIS Control 14 – Controlled use of administrative privileges  
- CIS Windows Benchmark: Restrict RDP, enable NLA  

**ISO 27001 Mapping:**  
- Annex A.13.1 – Network security management  

---

## STEP 5 — Windows Firewall and Network Security
**Purpose:**  
Configuring Windows Firewall and disabling unused protocols reduces the network attack surface.  

**CIS Mapping:**  
- CIS Control 13 – Network monitoring and defense  
- CIS Windows Benchmark: Enable firewall, configure rules  

**ISO 27001 Mapping:**  
- Annex A.13.1 – Network security management  
- Annex A.12.4 – Logging and monitoring  

---

## STEP 6 — Auditing and Logging
**Purpose:**  
Tracking system events, login attempts, and changes helps in accountability and forensic investigation.  

**CIS Mapping:**  
- CIS Control 8 – Audit logs for accountability  
- CIS Windows Benchmark: Enable event logging, configure retention  

**ISO 27001 Mapping:**  
- Annex A.12.4 – Logging and monitoring  
- Annex A.16.1 – Management of information security incidents  

---

## STEP 7 — Malware Protection
**Purpose:**  
Protects the system against malware, ransomware, and other malicious software.  

**CIS Mapping:**  
- CIS Control 8.8 – Malware defenses  
- CIS Windows Benchmark: Enable antivirus, schedule scans, auto-update signatures  

**ISO 27001 Mapping:**  
- Annex A.12.2 – Protection from malware  

---

## STEP 8 — System Integrity and Security Tools
**Purpose:**  
Implementing encryption, Secure Boot, and application control enhances system integrity and prevents unauthorized software execution.  

**CIS Mapping:**  
- CIS Control 3 – Data Protection  
- CIS Control 17 – Implement application control  
- CIS Windows Benchmark: Enable BitLocker, Secure Boot, AppLocker  

**ISO 27001 Mapping:**  
- Annex A.10.1 – Cryptographic controls  
- Annex A.12.2 – Malware protection  
- Annex A.12.5 – Security in development and support  

---

## Files, Services, and Configurations Altered

### System Updates and Patching
- Windows Update Settings via `Settings > Update & Security`  
- Command: `sconfig` or PowerShell `Get-WindowsUpdate`  

### User, Group, and Privilege Management
- `Local Users and Groups` (lusrmgr.msc)  
- UAC settings via `Control Panel > User Accounts > Change User Account Control`  

### Account and Password Policies
- Local Security Policy (`secpol.msc`)  
- Group Policy for password settings (`gpedit.msc`)  

### Remote Access / RDP
- `System Properties > Remote` – enable/disable Remote Desktop  
- RDP settings in `gpedit.msc`  
- Firewall rules for RDP via `Windows Defender Firewall`  

### Firewall and Network
- Windows Defender Firewall configuration (`wf.msc`)  
- Disable SMBv1 (`Windows Features > Turn Windows features on or off`)  

### Auditing and Logging
- Event Viewer (`eventvwr.msc`)  
- Security Audit Policies in `Local Security Policy`  

### Malware Protection
- Windows Defender or third-party AV  
- Controlled Folder Access via `Windows Security > Virus & threat protection`  

### System Integrity and Security Tools
- BitLocker via `Control Panel > BitLocker Drive Encryption`  
- Secure Boot via BIOS/UEFI  
- AppLocker / Software Restriction Policies via `gpedit.msc`  

---

**Summary:**  
These steps ensure Windows systems are hardened against unauthorized access, vulnerabilities, and malware, while maintaining compliance with **CIS Benchmarks** and **ISO 27001 standards**. Users can study the altered files, services, and configurations for hands-on learning.
