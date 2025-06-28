# 🧭 NIST Cybersecurity Framework (CSF) Mapping

## 🎯 Purpose

This document maps your open-source SOC capabilities to the core functions and categories of the **NIST Cybersecurity Framework (CSF)** — helping startups build measurable, compliance-ready security practices without expensive tooling or MSSPs.

---

## 📚 Overview of the NIST CSF

The NIST CSF consists of **five core functions**:
1. **Identify** – Know your assets, risks, and people
2. **Protect** – Safeguard systems and limit impact
3. **Detect** – Spot malicious activity in real time
4. **Respond** – Contain and mitigate incidents
5. **Recover** – Restore operations and reduce future risk

---

## 📌 SOC Capability Mapping to NIST CSF

| Function | Category | Example Subcategory | Open-Source Tools / Assets |
|----------|----------|----------------------|-----------------------------|
| **Identify (ID)** | Asset Management (ID.AM) | Maintain inventory of assets | `asset-inventory.xlsx`, Wazuh |
|  | Risk Assessment (ID.RA) | Assess risk to operations | Manual RA doc, OpenRMF (optional) |
|  | Governance (ID.GV) | Define policies & roles | `acceptable-use.md`, `password-policy.md` |

| **Protect (PR)** | Access Control (PR.AC) | Enforce RBAC, MFA | IAM policies, Wazuh alerts |
|  | Awareness & Training (PR.AT) | Security awareness for users | `user_awareness_basics.md`, phishing simulations |
|  | Data Security (PR.DS) | Protect sensitive data at rest | Encrypted storage, `data-handling.md` |
|  | Maintenance (PR.MA) | Regular system updates | `patch_vuln_mgmt.md` |
|  | Protective Technology (PR.PT) | Harden systems and segment networks | Suricata, Firewalls, `system_hardening_guide.md` |

| **Detect (DE)** | Anomalies & Events (DE.AE) | Detect unusual behavior | Wazuh rules, Graylog alerts, Zeek |
|  | Continuous Monitoring (DE.CM) | Log collection and analysis | Wazuh, Graylog, Grafana dashboards |
|  | Detection Processes (DE.DP) | Maintain and tune detection rules | `alert_rules.md`, `siem_tuning_tips.md` |

| **Respond (RS)** | Response Planning (RS.RP) | IR plan exists and is tested | `incident_response_playbooks.md`, `incident_response_policy.md` |
|  | Communications (RS.CO) | Alert teams and external parties | TheHive, Email/Slack alerting |
|  | Analysis (RS.AN) | Investigate security events | TheHive, Cortex, OSQuery |
|  | Mitigation (RS.MI) | Contain incidents quickly | Custom playbooks, patching |
|  | Improvements (RS.IM) | Learn from incidents | `tabletop_exercise_guide.md`, post-mortems |

| **Recover (RC)** | Recovery Planning (RC.RP) | Recovery plans and roles | Business continuity (future) |
|  | Improvements (RC.IM) | Incorporate lessons learned | Jira/Notion post-incident reviews |
|  | Communications (RC.CO) | Restore trust and notify stakeholders | IR team templates, exec comms plan |

---

## 📊 Implementation Status Tracker (Example)

| CSF Category | Implementation Status | Notes |
|--------------|------------------------|-------|
| ID.AM | ✅ | Asset inventory in place |
| PR.AT | ✅ | Phishing simulation doc ready |
| DE.CM | ✅ | Wazuh + Zeek monitoring live |
| RS.RP | ⬜️ | IR tabletop scheduled next quarter |
| RC.IM | ⬜️ | Working on incident retrospective process |

---

## ✅ Summary

Even if you're not NIST-certified, aligning with NIST CSF gives your startup:

- A clear **roadmap for building trust** with customers and investors
- A framework to evaluate your **SOC maturity**
- A structure for choosing the **right controls and tools**

---

> 🧠 NIST CSF doesn’t prescribe specific tools — it asks “do you know your risks and can you respond?”  
> This MVS Kit + open-source SOC stack helps you say **yes** confidently.

---

> 🔄 _Last Updated: June 26, 2025_
