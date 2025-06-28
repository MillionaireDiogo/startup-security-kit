# 🧱 SOC Architecture Overview

## 🎯 Purpose

This document provides a high-level overview of how to architect a lightweight, cost-effective Security Operations Center (SOC) that fits the needs of fintech startups. The goal is to prioritize visibility, detection, and response — using open-source or low-cost tools — while staying compliant-ready.

---

## ⚙️ SOC Objectives for Startups

- 📈 Achieve **continuous monitoring** of assets and identities
- 🔍 Enable **real-time detection and alerting** of security incidents
- 🛡️ Support **incident response** and evidence collection
- 🧾 Provide **audit logs** for compliance (SOC 2, ISO 27001, PCI-DSS)
- 💡 Maintain **scalability** for future MSSP integration

---

## 🧬 Core Components

| Layer | Function | Tools (Suggested) |
|-------|----------|--------------------|
| **Data Collection** | Log collection from systems, endpoints, cloud | Wazuh, Beats/FluentBit, Syslog, AuditD |
| **Log Aggregation** | Central storage and normalization of logs | Graylog, Elasticsearch, OpenSearch |
| **Detection & Correlation** | Identify suspicious behavior and match rules | Sigma rules, Wazuh rules, Zeek, Suricata |
| **Alerting** | Trigger alerts for investigation | TheHive + Cortex, Email, Slack, SIEM-native |
| **Dashboarding** | Visualization of threats, metrics | Grafana, Kibana, Graylog UI |
| **Response & Ticketing** | IR workflow, case management | TheHive, Jira, Notion, Google Sheets (starter) |
| **Threat Intelligence** | External context for IOCs | MISP, OpenCTI, ThreatFox, AbuseIPDB |

---

## 🔄 Event Flow Architecture

```text
Endpoints / Servers / Cloud
            ↓
   Syslog / FluentBit / Beats
            ↓
 Log Aggregator (Graylog / Wazuh)
            ↓
    SIEM & Detection Rules
            ↓
   Alert → TheHive → IR Team Notification
```


---

## 🧠 Deployment Tips

- **Start small.** Use hosted versions or containers to bootstrap the SOC stack (e.g., Wazuh in Docker).
- **Automate ingestion.** Use agent-based log collection (Wazuh agent, OSQuery, Filebeat).
- **Tag and normalize.** Apply naming conventions for log sources and severity tagging.
- **Use dashboards.** Focus on visibility first — Grafana + simple dashboards help teams stay proactive.
- **Centralize assets.** Integrate your asset inventory (from your MVS Kit) with log sources and monitoring.

---

## 🚧 Growth Roadmap

| Phase | Milestone |
|-------|-----------|
| Phase 1 | Local SIEM + Wazuh + manual alerting |
| Phase 2 | Add Zeek/Suricata for network monitoring |
| Phase 3 | Integrate TheHive for IR case management |
| Phase 4 | Automate threat intel lookups (e.g., AbuseIPDB) |
| Phase 5 | Review compliance controls (log retention, access control) |
| Phase 6 | Consider MSSP integration or managed SIEM (as funding grows) |

---

## 📚 References

- [NIST SP 800-61r2 – Incident Handling Guide](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)
- [Sigma Rules Project](https://github.com/SigmaHQ/sigma)
- [Wazuh Docs](https://documentation.wazuh.com/)
- [TheHive Project](https://thehive-project.org/)
- [Graylog](https://www.graylog.org/)

---

> 🏁 Build lean. Monitor smart. Scale secure.

> 🔄 _Last Updated: June 27, 2025_
