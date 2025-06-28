# 🩹 Patch & Vulnerability Management

## 🎯 Purpose

This document outlines a structured but lightweight vulnerability and patch management approach for startups. It’s built to support open-source tools and limited staff while maintaining visibility, compliance (e.g., ISO 27001, SOC 2), and real-world security readiness.

---

## 🧱 Core Principles

- 🔍 **Visibility First:** Know what assets and software you’re running.
- 🗓️ **Patch Regularly:** Apply updates on a scheduled basis (monthly/quarterly).
- 🛑 **Prioritize Risk:** Focus on CVEs with known exploits or affecting critical systems.
- ⚙️ **Automate Where Possible:** Use simple scripts, tools, or cloud-native patching.

---

## 📦 What to Patch

| Asset Type | Examples |
|------------|----------|
| **OS & Kernel** | Ubuntu, Windows, CentOS, macOS |
| **Browsers** | Chrome, Firefox, Edge |
| **Productivity Tools** | Office, PDF readers |
| **Cloud Hosts** | EC2, Azure VMs, Kubernetes nodes |
| **Containers** | Base images, libraries, runtimes |
| **Applications** | Web servers, database servers |
| **Firmware** | Routers, firewalls, IoT devices |

---

## 🛠️ Open-Source Tools

| Tool | Function |
|------|----------|
| **OpenVAS** | Network and host vulnerability scanning |
| **Trivy** | Container and image scanning |
| **Wazuh** | Vulnerability detection + alerting |
| **Lynis** | Linux system auditing and hardening |
| **Debsecan** / **yum updateinfo** | CVE detection in Linux distros |
| **Patch My PC (Free)** | Windows app patching |

---

## 🚦 Patch Management Workflow

```text
Asset Inventory → Vulnerability Scan → Prioritize → Patch → Verify → Document

## 📁 Sample Documentation Format

```yaml
Patch Window: 2025-06-25

Systems Patched:
  - ubuntu-web-01: nginx 1.18 → 1.25
  - win-app-03: Microsoft Edge auto-updated
  - aws-node-04: applied kernel patch

Pending:
  - db-prod-02 (restart scheduled)

Verified By: Chidiogo A.

## 🔐 Patch SLA Recommendation

| Risk Level | SLA          |
|------------|--------------|
| Critical   | 72 hours     |
| High       | 7 days       |
| Medium     | 14–30 days   |
| Low        | 60+ days     |

---

## 📝 Compliance Mappings

| Control Set        | Relevant Requirement                          |
|--------------------|-----------------------------------------------|
| ISO 27001 A.12.6.1 | Management of technical vulnerabilities       |
| SOC 2 CC5.2        | Remediation of vulnerabilities                |
| NIST CSF PR.IP-12  | Vulnerabilities are identified and remediated |


🔄 Last Updated: June 27, 2025