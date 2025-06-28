# 📘 ISO/IEC 27001 Basics for Startups

## 🎯 Purpose

This guide explains ISO/IEC 27001 in the context of building a startup Security Operations Center (SOC) using mostly open-source tools. It helps security-conscious fintechs and growing tech startups align early with the **controls and principles of ISO 27001** — even before formal certification.

---

## 🧠 What is ISO/IEC 27001?

ISO/IEC 27001 is an international standard for establishing, implementing, maintaining, and continuously improving an **Information Security Management System (ISMS)**.

For startups, it means:
- Identifying and securing sensitive information
- Implementing policies and procedures for risk management
- Proving those controls are working consistently

---

## 🧩 Key Components Mapped to a Startup SOC

| ISO Control Area | What It Means | Example (Startup Context) |
|------------------|----------------|-----------------------------|
| A.5 – InfoSec Policies | Define security goals and rules | Acceptable Use, IR Policy |
| A.6 – Organization of InfoSec | Assign roles and responsibilities | IR Team Roles, Alert Handling |
| A.8 – Asset Management | Know what assets you own and protect | asset-inventory.xlsx |
| A.9 – Access Control | Restrict data access to authorized users | MFA, RBAC, IAM logs |
| A.10 – Cryptography | Use encryption at rest and in transit | S3/Azure Blob encryption, HTTPS |
| A.12 – Operations Security | Secure day-to-day IT ops | Wazuh, Graylog, Patch Mgmt |
| A.13 – Communications Security | Secure data in networks and apps | TLS, VPN, Firewall rules |
| A.16 – Incident Management | Be prepared to detect & respond to breaches | TheHive, playbooks, IR drills |
| A.18 – Compliance | Align with legal/regulatory needs | GDPR, NDPR, PCI-DSS mappings |

---

## ⚙️ Implementing ISO 27001 with Open-Source Tools

| Requirement | Tool/Practice |
|-------------|---------------|
| Log monitoring | Wazuh, Graylog |
| Access tracking | IAM logs, auditd |
| Risk assessment | Manual spreadsheet or OpenRMF |
| IR documentation | `incident_response_playbooks.md` |
| Asset inventory | `asset-inventory.xlsx` |
| Controls mapping | `compliance_mapping.md` |
| Dashboards | Grafana, Kibana |
| Security policies | Markdown files in GitHub repo |

---

## 🚀 ISO Readiness Milestones for Startups

| Milestone | Description |
|-----------|-------------|
| 🔹 Policy Adoption | Acceptable Use, Password, Vendor, IR |
| 🔹 Asset Classification | Document what data and systems you protect |
| 🔹 Logging & Monitoring | Log and alert on critical activity |
| 🔹 Response Capability | Know how to handle incidents |
| 🔹 Evidence Generation | Maintain logs, reports, playbooks |

---

## 🧾 Documentation Required

- ✅ Security Policies (`*.md`)
- ✅ Risk Register (spreadsheet or Notion doc)
- ✅ Incident Logs
- ✅ User Access Reviews
- ✅ Vendor Risk Assessments

---

## 🛡️ Tips for Pre-Certification Teams

- Track your work in version control (GitHub or GitLab)
- Centralize your logs and alerts early
- Build a habit of documentation (automate where possible)
- Maintain a minimal but functional ISMS folder/repo

---

> 📌 You don’t need a badge to align with ISO 27001.  
> You need **evidence, consistency, and intent**.  

---

> 🔄 _Last Updated: June 27, 2025_
