# 📘 SOC Daily Log Template

> Use this template to record daily SOC analyst activities, alerts reviewed, actions taken, and escalations. Helps maintain accountability, support shift handovers, and improve visibility in small teams.

---

## 🗓️ Date: [YYYY-MM-DD]  
## 👤 Analyst on Duty: [Full Name]  
## 🕒 Shift: [e.g., 08:00–16:00 / Night Shift / Weekend]

---

## 🧭 Summary of the Day

Provide a short narrative (~3–5 sentences):

- Overall activity level (e.g., quiet, moderate, high alert volume)
- Systems monitored
- Any escalations or handovers
- Tool/system issues (if any)

---

## 🛎️ Alerts Triaged

| Time (UTC) | Severity | Alert Type | Source | Action Taken | Escalated? |
|------------|----------|------------|--------|--------------|-------------|
| 09:12 | High | Brute force login | Wazuh | Account locked, IP blocked | Yes |
| 11:43 | Medium | Unusual DNS query | Zeek | Logged for review | No |
| ... | ... | ... | ... | ... | ... |

---

## 🛠️ System Health Check

| Tool/Service | Status | Notes |
|--------------|--------|-------|
| Wazuh | ✅ OK | Agent sync confirmed |
| Graylog | ⚠️ Slow queries | Restarted inputs |
| Cortex | ✅ OK | All responders operational |

---

## 🧠 Threat Intelligence Notables

- [ ] New IOC from MISP (Added to Wazuh ruleset)
- [ ] Updated AbuseIPDB feed integrated
- [ ] External advisory: New CVE-2025-XXXX — affects nginx <1.25.3

---

## 🚧 Incidents Opened / Investigated

| Incident ID | Title | Status | Owner |
|-------------|-------|--------|-------|
| INC-2025-021 | Possible RDP brute force | Investigating | Angela A. |
| INC-2025-022 | Suspicious script in container | Closed | Segun B. |

---

## 📦 Notes & Recommendations

- [ ] Alert rule for PowerShell encoding is noisy — consider tuning
- [ ] Missing logs from win-prod-02 — check Filebeat config
- [ ] Recommend adding dashboard panel for failed SSH attempts

---

## 🔁 Shift Handover Notes

- No major incidents ongoing  
- One alert awaiting review (11:00 AM) — passed to next shift  
- Ensure Zeek logs are parsing correctly — review pipeline

---

> 📅 Saved as: `soc-log-[YYYY-MM-DD].md`  
> 🔐 Access control: Read-only for non-SOC users

---

> 🔄 _Last Updated: June 27, 2025_
