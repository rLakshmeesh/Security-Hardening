# Ubuntu System Hardening: Theory and Framework Mapping

This document explains the key steps in Ubuntu system hardening, their purposes, and how they map to **CIS Benchmarks** and **ISO 27001 controls**.  

---

## STEP 1 — System Update and Maintenance
**Purpose:**  
Keeping the system up-to-date ensures that all security patches and bug fixes are applied, reducing vulnerabilities that attackers could exploit.  

**CIS Mapping:**  
- CIS Ubuntu Benchmark: Ensure system is up-to-date, unnecessary packages removed  
- CIS Control v8: 7.1 – Continuous Vulnerability Management  

**ISO 27001 Mapping:**  
- Annex A.12.6 – Technical vulnerability management  
- Annex A.14.2 – Security in development and support processes  

---

## STEP 2 — User, Group, and Sudo Hardening
**Purpose:**  
Restricting user privileges and enforcing least privilege principles prevents unauthorized access and privilege escalation.  

**CIS Mapping:**  
- CIS Control 6.1 – Restrict administrative privileges  
- CIS Ubuntu Benchmark: Ensure users are assigned correct groups, sudo access limited  

**ISO 27001 Mapping:**  
- Annex A.9.2 – User access management  
- Annex A.9.4 – System and application access control  

---

## STEP 3 — SSH Hardening
**Purpose:**  
Securing SSH prevents unauthorized remote access. Measures include disabling root login, using key-based authentication, and restricting users.  

**CIS Mapping:**  
- CIS Control 16.9 – Secure configuration for network devices  
- CIS Ubuntu Benchmark: Disable root login, enforce SSH key authentication  

**ISO 27001 Mapping:**  
- Annex A.9.4 – Secure access to systems  
- Annex A.13.1 – Network security management  

---

## STEP 4 — Firewall Configuration (UFW)
**Purpose:**  
Configuring UFW (Uncomplicated Firewall) enforces network access policies and reduces the system’s attack surface.  

**CIS Mapping:**  
- CIS Control 13 – Network monitoring and defense  
- CIS Ubuntu Benchmark: Configure host-based firewall  

**ISO 27001 Mapping:**  
- Annex A.13.1 – Network security management  
- Annex A.12.4 – Logging and monitoring  

---

## STEP 5 — Intrusion Prevention (Fail2ban)
**Purpose:**  
Fail2ban monitors authentication logs and blocks IP addresses with repeated failed login attempts, protecting against brute-force attacks.  

**CIS Mapping:**  
- CIS Control 16 – Account monitoring and control  
- CIS Ubuntu Benchmark: Enable intrusion detection/prevention  

**ISO 27001 Mapping:**  
- Annex A.12.4 – Logging and monitoring  
- Annex A.13.1 – Network security management  

---

## STEP 6 — System Auditing (auditd)
**Purpose:**  
auditd tracks changes to critical files, user activity, and system events, supporting accountability and forensic investigation.  

**CIS Mapping:**  
- CIS Control 8 – Audit logs for accountability  
- CIS Ubuntu Benchmark: Configure audit rules for critical files  

**ISO 27001 Mapping:**  
- Annex A.12.4 – Logging and monitoring  
- Annex A.16.1 – Management of information security incidents  

---

## STEP 7 — Vulnerability and Integrity Scanning (Lynis)
**Purpose:**  
Lynis scans the system for vulnerabilities, misconfigurations, and compliance gaps, providing actionable recommendations.  

**CIS Mapping:**  
- CIS Control 7 – Continuous vulnerability management  
- CIS Ubuntu Benchmark: Perform periodic security scans  

**ISO 27001 Mapping:**  
- Annex A.12.6 – Technical vulnerability management  
- Annex A.18.2 – Compliance with security policies  

---

## STEP 8 — Malware and Rootkit Scanning
**Purpose:**  
Detecting and removing malware or rootkits ensures system integrity and prevents unauthorized backdoors.  

**CIS Mapping:**  
- CIS Control 8.8 – Malware defenses  
- CIS Ubuntu Benchmark: Install malware/anti-rootkit tools  

**ISO 27001 Mapping:**  
- Annex A.12.2 – Protection from malware  
- Annex A.12.4 – Logging and monitoring  
## Files and Configurations Altered

Below is a consolidated list of files, configurations, and commands modified or referenced during Ubuntu hardening:

### System Update and Maintenance
- `/etc/apt/sources.list` – repository configuration  
- `/etc/apt/apt.conf.d/50unattended-upgrades` – unattended upgrades config  
- Commands: `sudo apt update && sudo apt upgrade`  

### User, Group, and Sudo Hardening
- `/etc/passwd` – user accounts  
- `/etc/shadow` – user passwords  
- `/etc/group` – groups  
- `/etc/sudoers` and `/etc/sudoers.d/*` – sudo privileges  
- Commands: `usermod`, `groupmod`, `sudo`  

### SSH Hardening
- `/etc/ssh/sshd_config` – SSH configuration (root login, key-based authentication, allowed users)  
- Command: `systemctl restart ssh`  

### Firewall (UFW) Configuration
- `/etc/ufw/ufw.conf` – UFW main configuration  
- Commands: `sudo ufw enable`, `sudo ufw default deny incoming`, `sudo ufw allow <port>`  

### Intrusion Prevention (Fail2ban)
- `/etc/fail2ban/jail.conf` or `/etc/fail2ban/jail.d/*.conf` – Fail2ban configuration  
- `/var/log/auth.log` – authentication logs monitored by Fail2ban  
- Command: `systemctl restart fail2ban`  

### System Auditing (auditd)
- `/etc/audit/audit.rules` or `/etc/audit/rules.d/*.rules` – audit rules  
- `/etc/audit/auditd.conf` – audit daemon configuration  
- Commands: `auditctl -l`, `ausearch`, `aureport`  

### Vulnerability and Integrity Scanning (Lynis)
- Lynis installation and scan commands: `sudo lynis audit system`  

### Malware and Rootkit Scanning
- Tools and logs:  
  - `rkhunter` → `/var/log/rkhunter.log`  
  - `chkrootkit`  
  - `clamav` → `/var/log/clamav/`  

---

**Summary:**  
Following these steps strengthens Ubuntu systems against unauthorized access, reduces vulnerabilities, enforces auditability, and aligns system security with widely recognized frameworks like **CIS Benchmarks** and **ISO 27001**.  
