# 🧭 SOC Compliance Mapping for Startups

## 🎯 Purpose

This document helps map open-source SOC capabilities to major security and compliance frameworks. It's designed for startups who cannot yet afford a Managed Security Service Provider (MSSP), but want to grow **compliance-ready** by adopting the right tooling and controls from day one.

---

## 📊 Frameworks Mapped

| Acronym | Name |
|--------|------|
| ISO 27001 | Information Security Management System |
| SOC 2 | Service Organization Controls - Trust Principles |
| NIST CSF | Cybersecurity Framework (U.S. NIST) |
| PCI-DSS | Payment Card Industry Data Security Standard |

---

## 🛠️ Open-Source SOC Capability vs. Compliance Control

| SOC Capability | ISO 27001 | SOC 2 | NIST CSF | PCI-DSS | Example Tool |
|----------------|-----------|--------|-----------|----------|---------------|
| Log Collection | A.12.4.1 | CC7.2 | DE.CM-1 | Req 10.2 | Wazuh, FluentBit |
| Log Aggregation | A.12.4.3 | CC7.2 | DE.CM-7 | Req 10.5 | Graylog, OpenSearch |
| Correlation & Detection Rules | A.12.4.1 | CC7.1 | DE.DP-4 | Req 10.6 | Wazuh Rules, Sigma |
| Incident Response Workflow | A.16.1.5 | CC7.4 | RS.RP-1 | Req 12.10 | TheHive, Playbooks |
| Threat Intelligence | A.12.6.1 | CC7.3 | ID.RA-2 | N/A | MISP, ThreatFox |
| Vulnerability Detection | A.12.6.1 | CC7.3 | PR.IP-12 | Req 6.1, 11.2 | Wazuh, OpenVAS |
| Endpoint Monitoring | A.12.6.1 | CC7.3 | DE.CM-7 | Req 5.1.1 | CrowdStrike (paid) or Wazuh (open) |
| Alerting & Notification | A.16.1.1 | CC7.2 | DE.AE-2 | Req 10.6 | TheHive, Email/Slack |
| Dashboards & Reporting | A.12.7.1 | CC5.3 | DE.DP-5 | Req 10.6.1 | Grafana, Kibana |
| Asset Inventory & Classification | A.8.1.1 | CC1.1 | ID.AM-1 | Req 2.4 | asset-inventory.xlsx |
| Access Control Logging | A.9.4.5 | CC6.6 | PR.AC-7 | Req 10.2.5 | IAM logs, SIEM |
| Log Retention | A.12.4.2 | CC7.2 | DE.CM-7 | Req 10.7 | S3 Glacier, Elastic ILM |

---

## 🧪 Compliance Progress Tracker (Suggested)

| Area | In Place? | Notes |
|------|-----------|-------|
| Daily log review process | ✅ | See `log_review_checklist.md` |
| IR plan mapped to frameworks | ✅ | See `incident_response_playbooks.md` |
| Retention policies implemented | ⬜️ | In progress via S3 lifecycle |
| Access control logging | ✅ | Wazuh + IAM integration complete |
| Alert classification by severity | ✅ | See Wazuh + TheHive integration |
| Threat intel feeds integrated | ⬜️ | Pending setup of MISP |

---

## 📌 Compliance Mapping Strategy

- 🔍 Focus on **detectable and auditable controls** first
- 📁 Maintain evidence: alerts, playbooks, logs, reports
- 🧩 Choose tools that generate **structured data** (JSON, CSV, dashboards)
- 🧾 Keep mapping documents like this updated for audit readiness

---

## 🛡️ Final Note

> You don’t need to be fully certified to behave like a compliant company. Start by:
> - Mapping every tool to a control
> - Logging every alert and action
> - Writing minimal documentation that proves your intent and posture

---

> 🔄 _Last Updated: June 26, 2025_
