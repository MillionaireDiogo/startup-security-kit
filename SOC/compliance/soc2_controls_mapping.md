# 🛡️ SOC 2 Controls Mapping for Startup SOC

## 🎯 Purpose

This document maps key SOC 2 Trust Services Criteria (TSC) to controls that can be implemented using open-source SOC tools. It's designed to help lean startups demonstrate security, availability, and confidentiality practices **without an MSSP or enterprise tooling**.

---

## 📚 What is SOC 2?

SOC 2 is a security framework developed by the AICPA that evaluates an organization’s systems based on five Trust Service Criteria (TSC):

1. **Security** (required)
2. **Availability**
3. **Confidentiality**
4. **Processing Integrity**
5. **Privacy** (optional)

> Most startups focus on **Security**, **Availability**, and **Confidentiality** for early-stage audits.

---

## ✅ Mapping Open-Source SOC Capabilities to SOC 2 Criteria

| SOC 2 Criteria | Common Control | MVS/SOC Artifact or Tool |
|----------------|----------------|---------------------------|
| **CC1.2** – Board oversight | Define roles and accountability | Acceptable Use, IR Policy |
| **CC1.4** – Risk assessment | Periodic risk analysis | Risk Register (manual or template) |
| **CC5.2** – User access provisioning | RBAC, IAM, least privilege | IAM config + Wazuh monitoring |
| **CC6.1** – Logical access controls | MFA, password policies | `password-policy.md`, MFA logs |
| **CC6.2** – Auth mechanisms | Auth logs + monitoring | Wazuh, auditd, cloud IAM logs |
| **CC6.3** – Role-based access | Permissions tied to job roles | IAM policies, SSO rules |
| **CC6.6** – Change management | Track infra/app changes | Git, audit logs, `patch_vuln_mgmt.md` |
| **CC6.7** – Security alerts | Alerting system with severity | Wazuh + TheHive + email/Slack |
| **CC6.8** – Vulnerability detection | Vulnerability scans | Wazuh, OpenVAS, patch reports |
| **CC7.1** – Threat detection | SIEM rules and threat feeds | Sigma rules, Wazuh, MISP |
| **CC7.2** – Log review | Centralized logging + review checklist | Graylog/Wazuh, `log_review_checklist.md` |
| **CC7.3** – Incident response | Formal IR plan and playbooks | `incident_response_playbooks.md`, TheHive |
| **CC7.4** – Post-incident analysis
