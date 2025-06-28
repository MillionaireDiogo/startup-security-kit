# 🚨 Incident Response Playbooks

## 🎯 Purpose

This document provides ready-to-use incident response (IR) playbooks for common security incidents. These are tailored for startups using open-source tools and are aligned with lean SOC operations and fast containment, even without a dedicated security team.

---

## 📁 Format

Each playbook contains:

- **Trigger:** What activates the playbook
- **Objective:** What to achieve
- **Actions:** Steps to take
- **Tools Involved:** Open-source or native tools
- **Escalation:** When and how to escalate
- **Post-Incident:** Lessons learned and cleanup

---

## 🖥️ 1. Suspicious Login Attempt (Brute Force / Geo-Anomaly)

- **Trigger:** 5+ failed logins or login from unusual geo
- **Objective:** Validate, contain, and prevent account compromise
- **Actions:**
  1. Review logs (SIEM, Wazuh, Graylog)
  2. Correlate IP with threat intel (e.g., AbuseIPDB, MISP)
  3. Temporarily lock the account if needed
  4. Reset password and enforce MFA
- **Tools:** Wazuh, Graylog, TheHive, AbuseIPDB
- **Escalation:** If account is privileged or if lateral movement is detected
- **Post-Incident:** Document in TheHive or ticketing system; brief users

---

## 💾 2. Ransomware or Unusual File Encryption

- **Trigger:** High CPU usage + unusual file extensions or encryption tools
- **Objective:** Stop spread, isolate affected systems, and recover data
- **Actions:**
  1. Isolate infected endpoint (disable NIC or use EDR)
  2. Identify encryption process via logs or Wazuh
  3. Retrieve backup (if available)
  4. Run malware scan + snapshot disk for forensics
- **Tools:** Wazuh, EDR (like Velociraptor or Osquery), backups
- **Escalation:** If multiple systems are affected or data loss occurred
- **Post-Incident:** IR report, root cause analysis, user awareness training

---

## 🌐 3. Cloud IAM Misconfiguration or Policy Abuse

- **Trigger:** Sudden privilege escalation or permission change via CloudTrail/Azure logs
- **Objective:** Limit exposure and revert malicious change
- **Actions:**
  1. Review logs to confirm the event
  2. Revoke suspicious tokens/roles
  3. Validate current IAM policies
  4. Enable CloudTrail/Defender alerts for future events
- **Tools:** AWS CloudTrail, Azure Monitor, Wazuh, TheHive
- **Escalation:** If attacker used elevated roles or created persistence
- **Post-Incident:** IAM review, detection rule update, alert tuning

---

## 🧪 4. Malware Detection on Endpoint

- **Trigger:** Malware signature match from AV/EDR or Wazuh
- **Objective:** Contain the threat and prevent reinfection
- **Actions:**
  1. Isolate endpoint
  2. Identify and terminate malicious process
  3. Remove malware and scan all drives
  4. Investigate lateral movement or persistence
- **Tools:** Wazuh, ClamAV, Osquery, Velociraptor
- **Escalation:** If malware has exfiltration or beaconing behavior
- **Post-Incident:** Signature updates, educate user, create detection use case

---

## 📡 5. Data Exfiltration Alert

- **Trigger:** Sudden upload spike, DLP alert, large transfers to unknown IPs
- **Objective:** Confirm exfiltration, isolate flow, and investigate
- **Actions:**
  1. Check logs for destination IP, file size/type
  2. Verify user and process context
  3. Block outgoing connection
  4. Snapshot affected endpoint and alert management
- **Tools:** Suricata/Zeek, Wazuh, Graylog, SOAR, TheHive
- **Escalation:** If sensitive or regulated data (PII, IP) involved
- **Post-Incident:** Update firewall rules, notify stakeholders, compliance check

---

## 🔄 General IR Best Practices

- 🧠 Use TheHive to track all incident timelines and evidence
- 💬 Communicate incidents via secure internal channels (e.g., Signal, Mattermost)
- 🧾 Retain logs and alerts for post-incident reviews
- 📦 Practice tabletop exercises quarterly (see: `tabletop_exercise_guide.md`)
- 🛠️ Update detection rules and lessons learned after every incident

---

> 📣 A playbook you don’t practice is just a PDF. Run drills. Iterate fast.

---

> 🔄 _Last Updated: June 27, 2025_
