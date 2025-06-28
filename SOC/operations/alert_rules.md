# 🚨 Alert Rules for Startup SOC

## 🎯 Purpose

This document provides a curated list of alert rules that early-stage startups can implement in their SIEM or detection system. It emphasizes high-value, low-noise detections tailored to open-source tools like Wazuh, Graylog, Zeek, Suricata, and custom log pipelines.

---

## 🛠️ Tools & Rule Formats

| Tool | Format | Rule Sources |
|------|--------|--------------|
| **Wazuh** | XML | Wazuh ruleset, Sigma (converted) |
| **Graylog** | Stream alerts, pipelines | Custom Grok + conditions |
| **ELK Stack** | Query-based | Kibana alerts, Sigma |
| **Falco** | YAML (K8s syscall) | Falco default rules |
| **Zeek/Suricata** | Custom scripts/signatures | EmergingThreats, SOC custom rules |

---

## 🔐 Identity & Access Alerts

| 🔍 Use Case | Suggested Rule |
|------------|----------------|
| **Multiple failed logins** | Alert after 5+ failed logins in 10 mins (per user/IP) |
| **Login from unusual geo** | Detect new country login for known user |
| **Root account login** | Alert on login using `root` or AWS root account |
| **MFA disabled or removed** | Alert if MFA status changes for user |
| **New IAM role creation** | Monitor AWS IAM/ Azure AD changes |

---

## 🖥️ Endpoint Behavior Alerts

| 🔍 Use Case | Suggested Rule |
|------------|----------------|
| **Execution of base64 or encoded commands** | `powershell.exe -enc ...` |
| **Unexpected child process** | MS Word spawning `cmd.exe` or `powershell.exe` |
| **Reverse shell attempt** | Bash connecting to external IP:port |
| **New binary in temp directory** | Unusual file write + execution |
| **Privilege escalation attempts** | Use of `sudo`, `runas`, `Set-UID` binaries |

---

## ☁️ Cloud Activity Alerts

| 🔍 Use Case | Suggested Rule |
|------------|----------------|
| **S3 bucket becomes public** | Monitor config change to public access |
| **IAM policy changes** | Detect user/role privilege modifications |
| **EC2 instance starts from unknown AMI** | Flag unknown image usage |
| **Unusual API calls** | Monitor unexpected use of APIs like `CreateUser`, `PutPolicy` |
| **Multiple failed logins to cloud console** | Similar to on-prem but via CloudTrail, Azure logs |

---

## 🌐 Network & Threat Intelligence Alerts

| 🔍 Use Case | Suggested Rule |
|------------|----------------|
| **Inbound traffic on restricted ports (e.g., 22/3389)** | Zeek or Suricata detection |
| **Outbound traffic to known malicious IPs** | Cross-reference threat feed (MISP, AbuseIPDB) |
| **DNS tunneling** | Excessive or long DNS queries (Zeek) |
| **Port scan detection** | Suricata/Zeek flag multi-port traffic from one IP |
| **Data exfiltration (unusual upload volume)** | Netflow/Zeek + anomaly detection |

---

## 🧪 Application-Specific Alerts

| 🔍 Use Case | Suggested Rule |
|------------|----------------|
| **API abuse detection** | 100+ failed API calls in 5 mins |
| **Sensitive endpoint access without auth** | `/admin`, `/api/key` without token |
| **5xx error spikes** | More than 10 server errors in 1 min |
| **Repeated login attempts from same IP (App logs)** | Correlate frontend logs and IPs |

---

## ✅ Prioritization Tags

You can tag alert rules based on **impact** and **confidence**:

| Tag | Meaning |
|-----|--------|
| `high-confidence` | Very low false positive rate |
| `high-impact` | Potentially severe incident |
| `investigate` | Context needed; not definitive |
| `informational` | Log enrichment or baseline pattern |

---

## 🧾 Example Wazuh Alert Rule (Encoded PowerShell)

```xml
<rule id="100100" level="10">
  <if_sid>18107</if_sid>
  <match>powershell.exe.*-enc</match>
  <description>Suspicious Encoded PowerShell Command</description>
  <group>windows,powershell,execution</group>
</rule>
```

## 📦 Alert Management Best Practices

- 🔄 **Review and tune alerts weekly**
- 🧵 **Correlate low-priority alerts** with others (e.g., login + file access)
- 🎯 **Suppress or auto-close known benign patterns**
- 💬 **Route alerts to appropriate channels:**
  - `high` → PagerDuty
  - `medium` → Slack/Email
  - `low` → Dashboard

---

## 🔄 Maintenance

- ✅ Maintain versioned alert rule files
- ✅ Periodically test alert generation with simulated data
- ✅ Review false positives and update rules monthly

---

> 🔄 _Last Updated: June 27, 2025_
