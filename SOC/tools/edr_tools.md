# 🛡️ EDR Tools for Startup SOCs

> Endpoint Detection & Response (EDR) tools help detect, investigate, and respond to threats on workstations, servers, and laptops. This guide highlights lightweight, budget-conscious tools that can be integrated into a startup SOC.

---

## 🎯 What to Look for in an EDR

| Capability                     | Why It Matters                        |
|-------------------------------|----------------------------------------|
| Real-time monitoring          | Immediate detection of attacks         |
| Process & command tracking    | Visibility into suspicious behavior    |
| Log forwarding                | Integration with SIEM / Wazuh / TheHive |
| Alerting & correlation        | Actionable insights from endpoint data |
| Remote response capabilities  | Isolate or remediate compromised systems |

---

## 🛠️ Recommended EDR Tools

### 1. **Wazuh (with Agent)**
- ✅ Open-source and lightweight
- Monitors Windows, Linux, and macOS endpoints
- Detects anomalies, file changes, and policy violations
- Integrates well with Elastic Stack and TheHive

🔗 [https://wazuh.com](https://wazuh.com)

---

### 2. **Velociraptor**
- ✅ Open-source endpoint visibility and DFIR platform
- Advanced query capabilities via Velocidex Query Language (VQL)
- Supports live triage, memory collection, forensic acquisition

🔗 [https://www.velociraptor.app](https://www.velociraptor.app)

---

### 3. **OSQuery + FleetDM**
- Query endpoints like a database (SQL-like syntax)
- Great for live endpoint monitoring
- Combine with FleetDM for centralized management

🔗 [https://osquery.io](https://osquery.io)  
🔗 [https://fleetdm.com](https://fleetdm.com)

---

### 4. **Microsoft Defender for Endpoint (Free Tier)**
- Built-in on Windows 10/11 and Server
- Offers real-time scanning and basic EDR telemetry
- Integrates with Windows Event Logs and Sysmon

🔗 [https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint)

---

## 🧪 Optional Enhancements

| Tool              | Use Case                         |
|-------------------|----------------------------------|
| **Sysmon**        | Logs detailed system activity (Windows) |
| **Falco**         | Container-aware runtime security |
| **Auditd**        | Linux audit framework             |

---

## 🔗 SIEM Integration Tips

- Use Filebeat or Wazuh agents to forward logs from EDR to Graylog or Elasticsearch  
- Configure alerts in SIEM for:
  - Suspicious child processes (`cmd → powershell`)
  - Use of `netstat`, `certutil`, `whoami`, etc.
  - Persistence indicators (`run registry keys`, cronjobs)

---

## ⚠️ Startup Considerations

- 🧵 Keep noise low — start with detection-only mode  
- 🔄 Automate agent deployment via scripts or Ansible  
- 📉 Monitor performance impact on endpoints  
- 🚨 Avoid alert fatigue: group alerts by severity or asset class

---

## ✅ Summary

| Tool          | Best For                          |
|---------------|------------------------------------|
| **Wazuh**     | General-purpose open-source EDR    |
| **Velociraptor** | DFIR & threat hunting           |
| **OSQuery**   | Continuous posture visibility      |
| **Sysmon**    | Deep Windows telemetry             |
| **Defender (Free)** | Quick Windows deployments    |

---

> 💡 Pro Tip: Use Wazuh for baseline EDR coverage, then layer OSQuery or Velociraptor as your capabilities mature.

---

> 🔄 _Last Updated: June 28, 2025_
