# ☁️ Cloud Security Checks for Startup SOC

## 🎯 Purpose

This document outlines essential cloud security checks that startups can implement within their SOC using open-source tools and manual processes. It focuses on balancing security, compliance, and cost-efficiency in cloud environments like AWS, Azure, and GCP.

---

## 🔐 Key Cloud Security Checks

### 1. **Identity and Access Management (IAM) Reviews**

- Audit IAM users, roles, and policies regularly  
- Remove or disable inactive accounts  
- Enforce least privilege principle  
- Enable MFA for all privileged accounts  
- Monitor and alert on unusual login patterns

**Tools:** AWS IAM Access Analyzer, Azure AD reports, Open Source: Prowler, ScoutSuite

---

### 2. **Cloud Resource Inventory and Tagging**

- Maintain an up-to-date inventory of cloud resources  
- Use tagging for ownership, environment (dev/prod), and sensitivity  
- Detect and remove unused or orphaned resources

**Tools:** AWS Config, Azure Resource Graph, GCP Asset Inventory

---

### 3. **Network Security**

- Review security groups and firewall rules to prevent overly permissive access (e.g., wide-open ports)  
- Use Network Access Control Lists (NACLs) effectively  
- Enforce encrypted communications (TLS) between services  
- Segment networks using VPCs, subnets, and private endpoints

**Tools:** AWS Security Hub, Azure Security Center, Open Source: CloudMapper, Steampipe

---

### 4. **Logging and Monitoring**

- Enable CloudTrail (AWS), Azure Monitor, or GCP Audit Logs for all accounts  
- Aggregate logs into centralized SIEM or log management system (Graylog, Wazuh)  
- Set alerts on critical events like privilege escalation, root account use, or IAM policy changes

---

### 5. **Data Protection**

- Encrypt data at rest using cloud provider native encryption or customer-managed keys (CMKs)  
- Enforce encryption in transit (TLS/SSL)  
- Regularly audit S3 bucket or blob storage permissions to avoid public exposure  
- Backup critical data and verify recovery procedures

---

### 6. **Vulnerability and Patch Management**

- Scan cloud workloads and container images regularly for vulnerabilities  
- Apply OS and application patches promptly  
- Use Infrastructure as Code (IaC) scanning tools to catch misconfigurations before deployment

**Tools:** OpenVAS, Trivy, TerraScan, Checkov

---

### 7. **Compliance and Governance**

- Map cloud resource configurations to compliance frameworks (e.g., CIS Benchmarks, PCI DSS)  
- Use automated compliance checks where possible  
- Document findings and remediation actions

---

## 🚀 Practical Tips for Startups

- Automate checks with scheduled scans and IaC validation pipelines  
- Integrate cloud security findings with SOC alerting (TheHive, Graylog)  
- Prioritize fixes based on business impact and risk level  
- Use free or low-cost community tools before considering paid solutions

---

## 📚 Useful Resources

- [AWS Security Hub](https://aws.amazon.com/security-hub/)  
- [Azure Security Center](https://azure.microsoft.com/en-us/services/security-center/)  
- [Google Cloud Security Command Center](https://cloud.google.com/security-command-center)  
- [Prowler - AWS Security Tool](https://github.com/toniblyx/prowler)  
- [ScoutSuite](https://github.com/nccgroup/ScoutSuite)  
- [CloudMapper](https://github.com/duo-labs/cloudmapper)

---

> 🔄 _Last Updated: June 27, 2025_
