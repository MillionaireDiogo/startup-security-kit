# 🤝 Vendor Risk Management Policy – Fintech Startup

## 🎯 Purpose

This policy defines how we select, evaluate, onboard, and monitor third-party vendors and SaaS providers that have access to company infrastructure, systems, codebases, or customer data. It aims to reduce third-party risk and ensure compliance with data protection and cybersecurity regulations.

> 📚 Based on:  
> - ISO/IEC 27001:2013 – Annex A.15 (Supplier Relationships)  
> - SOC 2 Trust Services Criteria (Security, Confidentiality)  
> - GDPR / NDPR – Third-party processing requirements  

---

## 📌 Scope

This policy applies to **all vendors, contractors, service providers, and tools** that:

- Process or access customer or financial data
- Integrate into our production systems
- Store or manage source code, logs, or infrastructure
- Are involved in product delivery, data analytics, or operational functions

---

## 📦 Vendor Risk Classification

Vendors should be classified into risk tiers:

| Tier | Description | Examples |
|------|-------------|----------|
| 🔴 Critical | Vendors with access to PII, financial data, or production systems | Cloud providers, KYC providers, payment processors |
| 🟡 Moderate | Vendors with access to internal tools or non-sensitive data | Analytics platforms, CRM, HR tools |
| 🟢 Low | No system or data access | Printing vendors, office supply |

---

## ✅ Vendor Evaluation Criteria

Before onboarding, vendors must be evaluated for:

- 📜 **Security certifications** (e.g., ISO 27001, SOC 2)
- 🔐 **Data encryption** in transit and at rest
- 🧾 **Privacy policies and DPA** (Data Processing Agreements)
- 🚨 **Breach notification procedures**
- 🧪 **Penetration testing or security audits**
- 🧰 **Support for role-based access and audit logs**

> Vendors handling **payment data** must be **PCI-DSS compliant**.

---

## 📝 Due Diligence & Onboarding Checklist

| Task | Required |
|------|----------|
| Signed **DPA or MSA** with security clauses | ✅ |
| Documented **security assessment** | ✅ |
| Vendor contact for security incidents | ✅ |
| Confirmed **compliance certifications** (e.g., SOC 2 if available) | ✅ |
| NDA signed (if accessing confidential systems) | ✅ |

---

## 🔄 Ongoing Monitoring & Offboarding

| Activity | Frequency |
|----------|-----------|
| Access review & usage audit | Quarterly |
| Review of vendor security posture | Annually |
| Risk reassessment based on new services | As needed |
| Access termination upon contract end | Immediately |

---

## 🚨 Vendor Breach Protocol

If a vendor suffers a breach:

- They must notify uthe organization within **24–48 hours**
- The security team will evaluate the **blast radius**
- Affected customers will be notified per **GDPR/NDPR** timelines
- Vendor may be suspended or replaced depending on severity

---

## 🧾 Recordkeeping

Maintain a **Vendor Risk Register** documenting:

- Vendor name and purpose
- Risk tier
- DPA/MSA status
- Access level and data types handled
- Last risk review date

---

## 📋 Vendor Risk Checklist

| Task | Status |
|------|--------|
| Vendors classified by risk tier | ✅ |
| Security & compliance assessments completed | ✅ |
| DPAs signed with all critical vendors | ✅ |
| Access logs enabled for high-risk vendors | ✅ |
| Quarterly access reviews conducted | ✅ |
| Vendor risk register maintained | ✅ |

---

> 🔄 _Last Updated: June 27, 2025_
