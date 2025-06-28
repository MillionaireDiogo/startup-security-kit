# 🛡️ System Hardening Guide

> A practical checklist for hardening operating systems (Linux & Windows) in a lean SOC environment. This helps reduce the attack surface, enforce baseline security, and support compliance efforts.

---

## 🎯 Purpose

To provide actionable system hardening steps that can be applied during provisioning or regular maintenance cycles — especially for internet-facing or critical infrastructure systems.

---

## 🧑‍💻 Applicable Systems

| OS / Platform   | Target Systems                   |
|-----------------|----------------------------------|
| Linux (Ubuntu, CentOS, RHEL) | Servers, containers, cloud VMs |
| Windows (10/11, Server) | Desktops, domain controllers, file servers |

---

## 🧱 Baseline Hardening Steps

### 🔒 User Accounts & Access

- [x] Disable or rename default accounts (e.g., `root`, `Administrator`)
- [x] Enforce strong password policies (see: `password_policy.md`)
- [x] Enable MFA for remote or privileged access
- [x] Use sudo/RunAs sparingly and log all escalations
- [x] Lock accounts after N failed attempts (fail2ban or GPO)

---

### 🔗 Network & Services

- [x] Close unused ports (use `nmap`, `netstat`, `ufw`, or `Windows Firewall`)
- [x] Disable unnecessary services (e.g., Telnet, FTP)
- [x] Use SSH keys, disable password-based SSH (Linux)
- [x] Enable Windows Firewall with appropriate rule sets
- [x] Enforce TLS 1.2+ for web servers and applications

---

### 🛠️ Logging & Monitoring

- [x] Enable system logging (journald, syslog, Event Viewer)
- [x] Forward logs to centralized SIEM (e.g., Wazuh, Graylog)
- [x] Monitor process creation, login/logout events
- [x] Use File Integrity Monitoring (FIM) for critical paths

---

### 🔄 Patch & Update Hygiene

- [x] Schedule automatic updates or patching windows
- [x] Subscribe to OS/vendor security bulletins
- [x] Validate kernel version and patch level regularly
- [x] Maintain change logs for any manual updates

---

### 🔐 Application & Software Control

- [x] Allow only signed applications (AppLocker / SELinux / AppArmor)
- [x] Disable autorun / autoplay on USBs
- [x] Whitelist browser extensions or plugins
- [x] Uninstall deprecated or unused software packages

---

### 🗃️ File System & Permissions

- [x] Set file and directory permissions using least privilege
- [x] Prevent execution in `/tmp` and user-writable directories (Linux)
- [x] Enable disk encryption for laptops and sensitive systems
- [x] Restrict access to config and secret files

---

## 📦 Hardening Automation Tools

| Tool | Platform | Use Case |
|------|----------|----------|
| **Lynis** | Linux | Hardening audit tool |
| **OpenSCAP** | Linux | CIS/NIST benchmark checks |
| **CIS-CAT Lite** | Cross-platform | CIS benchmark scans |
| **Ansible + Hardened Roles** | Linux | Repeatable hardening |
| **PowerShell DSC** | Windows | Enforce GPO-like configs |

---

## 📜 Documentation & Compliance Mapping

| Framework | Control Reference |
|-----------|-------------------|
| ISO 27001 | A.13.1.1, A.9.2.1 |
| NIST CSF  | PR.IP-1, PR.AC-1 |
| CIS v8    | Controls 4, 5, 7, 16 |
| SOC 2     | CC6.1, CC6.2, CC6.6 |

---

## 📎 Related Templates

- [`patch_vuln_mgmt.md`](../operations/patch_vuln_mgmt.md)
- [`asset_inventory.md`](../operations/asset_inventory.md)
- [`password_policy.md`](../../mvs-kit-fintech/password_policy.md)

---

> 📣 Security starts at the source. Harden once, monitor forever.

---

> 🔄 _Last Updated: June 27, 2025_
