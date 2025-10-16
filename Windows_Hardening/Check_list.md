# Windows System Hardening Checklist

## 1. System Update and Patch Management
| Step | Description | Status |
|------|-------------|--------|
| Enable automatic updates | Keep Windows updated with latest security patches | ⬜ |
| Remove unnecessary software | Uninstall unused applications to reduce attack surface | ⬜ |
| Verify update history | Ensure critical security patches are applied | ⬜ |

## 2. User, Group, and Privilege Management
| Step | Description | Status |
|------|-------------|--------|
| Enforce least privilege | Grant users only necessary permissions | ⬜ |
| Remove/disable default or unused accounts | Disable Guest, default Admin accounts if not needed | ⬜ |
| Configure UAC (User Account Control) | Ensure prompts for administrative actions | ⬜ |
| Review group memberships | Ensure users belong only to required groups | ⬜ |

## 3. Account and Password Policies
| Step | Description | Status |
|------|-------------|--------|
| Enforce password complexity | Minimum length, uppercase, lowercase, numbers, symbols | ⬜ |
| Set account lockout policy | Lock accounts after multiple failed login attempts | ⬜ |
| Enforce password expiration | Require regular password changes | ⬜ |
| Disable storing passwords | Prevent credentials caching where possible | ⬜ |

## 4. Remote Access and RDP Hardening
| Step | Description | Status |
|------|-------------|--------|
| Disable RDP if not needed | Turn off Remote Desktop service | ⬜ |
| Restrict RDP access | Allow only specific IPs or VPN | ⬜ |
| Enable Network Level Authentication (NLA) | Requires authentication before RDP session starts | ⬜ |
| Configure firewall rules for RDP | Allow only trusted connections | ⬜ |

## 5. Windows Firewall and Network Security
| Step | Description | Status |
|------|-------------|--------|
| Enable Windows Defender Firewall | Protect against unauthorized inbound/outbound traffic | ⬜ |
| Configure inbound and outbound rules | Allow only required ports and applications | ⬜ |
| Disable unused network protocols | Turn off SMBv1, Telnet, etc. if not needed | ⬜ |
| Enable logging for firewall events | Monitor blocked connections | ⬜ |

## 6. Auditing and Logging
| Step | Description | Status |
|------|-------------|--------|
| Enable auditing via Group Policy | Track login, file access, privilege changes | ⬜ |
| Configure Event Log retention | Ensure logs are stored long enough for forensic analysis | ⬜ |
| Centralize logs if possible | Use SIEM or central logging server | ⬜ |

## 7. Malware Protection
| Step | Description | Status |
|------|-------------|--------|
| Enable Windows Defender or equivalent | Real-time malware scanning | ⬜ |
| Schedule regular scans | Full system scans periodically | ⬜ |
| Enable automatic definition updates | Keep antivirus signatures up-to-date | ⬜ |
| Enable Controlled Folder Access | Protect critical directories from ransomware | ⬜ |

## 8. System Integrity and Security Tools
| Step | Description | Status |
|------|-------------|--------|
| Enable BitLocker | Encrypt system and data drives | ⬜ |
| Enable Secure Boot | Prevent boot-level malware | ⬜ |
| Disable unnecessary services | Minimize attack surface (print spooler, SMBv1, etc.) | ⬜ |
| Implement AppLocker or Software Restriction Policies | Control executable usage | ⬜ |

