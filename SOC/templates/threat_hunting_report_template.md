# 🕵️ Threat Hunting Report Template

> Use this template to document structured threat hunting exercises. It supports both proactive hunting missions and follow-up investigations from weak signals. Helps improve detection rules, visibility gaps, and team learning.

---

## 🗓️ Date: [YYYY-MM-DD]  
## 🧑‍💻 Analyst(s): [Name(s)]  
## 🔍 Hunt ID: [e.g., TH-2025-001]

---

## 🎯 Hunt Objective

Briefly describe the hypothesis or trigger for the hunt.

_Examples:_
- Investigate signs of credential dumping activity using `procdump.exe`
- Detect unauthorized data transfers to cloud storage services
- Validate potential C2 beaconing over non-standard ports

---

## 🧱 Environment Scope

| Environment | Included? | Notes |
|-------------|-----------|-------|
| Production Servers | ✅ Yes | All Linux and Windows hosts |
| Endpoints | ✅ Yes | Staff laptops and desktops |
| Cloud | ⚠️ Partial | AWS EC2 and S3 buckets only |
| Containers / Dev | ❌ No | Not included this cycle |

---

## 🛠️ Data Sources Used

- [x] Wazuh (host-based alerts)
- [x] Zeek (network metadata)
- [x] Graylog / ElasticSearch (log review)
- [x] Filebeat / Winlogbeat (event logs)
- [ ] DNS Logs
- [ ] Proxy or Web Gateway logs
- [ ] EDR (e.g., Osquery, Velociraptor)

---

## 🧪 Hunting Methodology

Describe your process step by step. Include queries, scripts, or tools used.

```sql
Wazuh Rule Query: data.win.system.eventID: 4688 AND commandLine: "*procdump*"
Graylog Query: source:"10.10.1.*" AND message:"curl" AND NOT destination:"trusted-domain.com"
Zeek Intel Match: service == "http" AND uri contains ".php"

### 🔄 Pivoting & Enrichment Techniques Used

- Used **AbuseIPDB** to check outbound IP reputation  
- Correlated **MISP indicators** with DNS query logs  

## 🚩 Key Findings

Summarize the most relevant results:

| Indicator              | Type     | Description                                       | Action         |
|------------------------|----------|---------------------------------------------------|----------------|
| 185.220.101.45         | IP       | Tor exit node connection seen from dev endpoint   | Blocked        |
| user.exe               | Process  | Unsigned binary executed with `--silent` flag     | Escalated      |
| s3.amazonaws.com/upload| Domain   | Unusual data size uploaded                        | Under review   |

---

## 📊 Summary

- ✅ **Systems Reviewed:** 142  
- 🧠 **Hypothesis Validated:** Partial  
- ⚠️ **Anomalies Detected:** 3  
- 📂 **IOC Artifacts Collected:** 5  
- 🔧 **Detection Rules Updated:** 2  

---

## 🛡️ Recommendations

- Enable logging for USB usage on all endpoints  
- Add Zeek signature for base64-encoded PowerShell payloads  
- Tune Wazuh rule for Event ID 4624 (noise from service accounts)  

---

## 📚 Attachments

- [ ] PCAP samples (in secure repo)  
- [ ] IOC CSV list  
- [ ] Screenshots of dashboard spikes  
- [ ] Sigma rule draft: `proc_creation_silent_exe.yml`  

> 🔄 _Last Updated: June 27, 2025_