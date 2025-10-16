# Ubuntu Hardening Checklist

## 1. User, Group, and Sudo Hardening
| Step | Description | Status |
|------|-------------|--------|
| Remove/disable unnecessary users | Delete or lock unused accounts | ⬜ |
| Enforce strong passwords | Configure `/etc/login.defs` and `libpam-pwquality` | ⬜ |
| Limit sudo privileges | Restrict `/etc/sudoers` to necessary users | ⬜ |
| Use groups for access control | Assign users to proper groups only | ⬜ |
| Audit user/group changes | Monitor `/etc/passwd`, `/etc/group`, `/etc/shadow` | ⬜ |

## 2. SSH & Service Restrictions
| Step | Description | Status |
|------|-------------|--------|
| Disable root login | Set `PermitRootLogin no` in `/etc/ssh/sshd_config` | ⬜ |
| Disable password authentication | Use key-based authentication only | ⬜ |
| Restrict allowed users | Use `AllowUsers` or `AllowGroups` | ⬜ |
| Change default SSH port | Optional, for reducing automated attacks | ⬜ |
| Disable unused services | Use `systemctl` to stop and disable unnecessary services | ⬜ |

## 3. Firewall (UFW) Setup
| Step | Description | Status |
|------|-------------|--------|
| Enable UFW | `sudo ufw enable` | ⬜ |
| Set default deny policy | `sudo ufw default deny incoming` and `allow outgoing` | ⬜ |
| Allow required ports | e.g., `sudo ufw allow 22/tcp` for SSH | ⬜ |
| Enable logging | `sudo ufw logging on` | ⬜ |
| Review rules regularly | `sudo ufw status verbose` | ⬜ |

## 4. File Permissions and auditd Rules
| Step | Description | Status |
|------|-------------|--------|
| Secure important files | Set strict permissions on `/etc/passwd`, `/etc/shadow`, `/etc/sudoers` | ⬜ |
| Audit critical files | Configure `auditd` rules for `/etc/passwd`, `/etc/shadow`, `/etc/sudoers` | ⬜ |
| Monitor world-writable files | Use `find / -type f -perm -002` to locate and fix | ⬜ |
| Set sticky bit on /tmp | `chmod +t /tmp` | ⬜ |

## 5. System Updates and Unattended Upgrades
| Step | Description | Status |
|------|-------------|--------|
| Enable automatic security updates | Configure `/etc/apt/apt.conf.d/50unattended-upgrades` | ⬜ |
| Regularly check for updates | `sudo apt update && sudo apt upgrade` | ⬜ |
| Remove unnecessary packages | `sudo apt autoremove` | ⬜ |

## 6. Log Monitoring
| Step | Description | Status |
|------|-------------|--------|
| Install and configure rsyslog | Ensure system logs are collected centrally | ⬜ |
| Monitor authentication logs | `/var/log/auth.log` for failed login attempts | ⬜ |
| Configure log rotation | Ensure logs do not grow indefinitely | ⬜ |
| Setup alerts | Use `logwatch` or similar tools for daily summaries | ⬜ |
