# 📋 Log Review Checklist

## 🎯 Purpose

This checklist helps security teams at early-stage startups review logs effectively and consistently. It enables detection of anomalies, ensures compliance readiness (SOC 2, ISO 27001), and strengthens threat response via actionable insights from log sources.

---

## 🛠️ Tools You Should Be Using

- **Log Collectors:** Wazuh, Filebeat, FluentBit
- **SIEM/Log Viewer:** Graylog, Kibana (ELK), Wazuh Dashboard
- **Analysis/Alerting:** TheHive, Grafana dashboards, email/slack alerts
- **Threat Feeds (optional):** AbuseIPDB, MISP, ThreatFox

---

## 🧩 General Review Categories

| Category | What to Look For |
|----------|------------------|
| **Authentication Logs** | Failed logins, login outside business hours, geo anomalies |
| **Privilege Escalation** | `sudo`, `runas`, IAM role changes |
| **Network Logs** | Unusual outbound traffic, port scanning patterns |
| **Application Logs** | Repeated 500 errors, failed transactions |
| **Endpoint Activity** | Unexpected process launches (e.g. `powershell`, `bash`) |
| **Cloud Audit Logs** | Root account use, config changes, policy updates |
| **Container/K8s Logs** | Exec shells in pods, privileged pod creation |
| **File Integrity** | Modified config files, sensitive data movement |
| **System Errors** | Crashes, high resource usage, unscheduled reboots |

---

## 🔁 Daily Log Review Checklist

| ✅ | Task |
|----|------|
| [ ] Check for critical alerts in SIEM (Wazuh/Graylog) |
| [ ] Review authentication failures (esp. root/admin accounts) |
| [ ] Scan for new/unusual IP addresses |
| [ ] Look for application or API errors |
| [ ] Validate that logging agents are running on all endpoints |
| [ ] Cross-check today's incidents with logs |
| [ ] Review IDS/IPS alerts (e.g., Suricata, Zeek) |

---

## 📅 Weekly Log Review Checklist

| ✅ | Task |
|----|------|
| [ ] Review top source IPs and geo locations |
| [ ] Validate IAM or role-based permission changes |
| [ ] Check for disabled logging or agent failures |
| [ ] Analyze any repetitive alert patterns |
| [ ] Update SIEM filters to reduce noise |
| [ ] Audit log retention status and free disk space |
| [ ] Validate that critical systems (DNS, DB, Email) are being logged properly |

---

## 🧠 Review Strategy

- **Tag logs** with source system and priority (e.g., `prod-app`, `low`, `high`)
- **Aggregate alerts** into a weekly dashboard for trend spotting
- **Correlate logs** with threat intel feeds and IOC lists
- **Document findings** in TheHive, Notion, or internal wiki

---

## 🧾 Output Documentation Template

You can use the following fields in your internal documentation (or ticketing system):

```yaml
Date Reviewed: 2025-06-26
Analyst: Chidiogo A.
Reviewed Systems: WebApp, VPN, Auth Logs
Notable Findings:
  - Multiple failed logins from same IP (Germany)
  - Wazuh agent disconnected on dev-server-2
Actions Taken:
  - Alert triaged via TheHive, IP blocked
  - Agent restarted and status confirmed
```

🔄 Last Updated: June 27, 2025