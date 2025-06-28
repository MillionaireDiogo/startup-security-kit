# 🔐 Password Policy – Fintech Startup

## 🎯 Purpose

This policy sets the standards for creating, managing, and securing passwords used across company systems, tools, and infrastructure. The goal is to protect accounts and systems from unauthorized access while following best practices from leading standards.

> 📚 Based on:  
> - NIST SP 800-63B: Digital Identity Guidelines  
> - ISO/IEC 27001:2013  
> - OWASP Authentication Cheat Sheet  

---

## 🔑 Scope

This policy applies to all employees, contractors, vendors, and partners who access:

- Internal systems (e.g., dashboards, CI/CD, DevOps tools)
- External services (e.g., cloud platforms, email, SaaS tools)
- Customer or payment-related systems

---

## 🧠 Password Requirements

| Category | Rule |
|----------|------|
| 🔤 Length | Minimum **12 characters** |
| 🧩 Complexity | Must include **3 of 4**: upper-case, lower-case, number, symbol |
| 🔁 Expiry | Passwords do **not expire** unless there’s suspicion of compromise |
| ❗ Reuse | Passwords must not be reused across systems |
| 📵 Prohibited | No use of dictionary words, names, dates, or reused corporate credentials |
| 🛠️ Generator | Encourage use of password managers to generate and store passwords |

---

## 🛡️ Authentication Controls

| Control | Description |
|---------|-------------|
| ✅ MFA Required | All critical accounts must have **multi-factor authentication** |
| 🔐 Password Managers | Use of secure password managers (e.g., Bitwarden, 1Password) is **strongly recommended** |
| 🚫 No Hardcoded Secrets | Passwords must never be stored in code or config files |
| 🧾 Hashing | Passwords must be hashed using **bcrypt, Argon2**, or similar algorithms |
| 🕵️ Monitoring | Monitor for credential stuffing and brute-force attempts via SIEM or alerting tools |

---

## 🧼 Password Hygiene Guidelines

Employees must:

- Never share passwords, even with coworkers or IT support
- Avoid writing down passwords physically or storing in plaintext
- Change passwords **immediately** if there’s any suspicion of compromise
- Use **different passwords** for work and personal accounts

---

## 📝 Enforcement

Non-compliance with this policy may result in:

- Revoked access to sensitive systems
- Internal disciplinary action
- Investigation by the security team

---

## 📋 Password Policy Checklist

| Task | Status |
|------|--------|
| All passwords meet minimum length & complexity | ✅ |
| MFA is enabled for admin and cloud accounts | ✅ |
| Password manager policy implemented | ✅ |
| Developers are prohibited from hardcoding secrets | ✅ |
| Breach monitoring is in place | ✅ |
| Password storage uses strong hashing | ✅ |

---

> 🔄 _Last Updated: June 27, 2025_
