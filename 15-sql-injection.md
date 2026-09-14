# SQL Injection

## 📌 Introduction
**SQL Injection (SQLi)** occurs when untrusted user input is concatenated directly into a SQL
query without proper sanitization or parameterization, letting an attacker alter the query's
logic — historically one of the most damaging web vulnerability classes.

---

## 🎯 Objectives
- Understand the root cause of SQL injection.
- Learn the major injection techniques and how to detect them.
- Practice safe exploitation with automated and manual tools.
- Apply structural (not just cosmetic) defenses.

---

## 🔍 Types of SQL Injection
1. **Classic / Auth-bypass** – e.g., `' OR '1'='1` to always satisfy a WHERE clause.
2. **UNION-based** – appends a `UNION SELECT` to combine attacker data with legitimate output.
3. **Error-based** – relies on verbose DB error messages leaking query structure.
4. **Blind SQLi** –
   - **Boolean-based** – infers data from true/false page behavior differences.
   - **Time-based** – uses functions like `SLEEP()` and measures response delay.
5. **Second-order SQLi** – malicious input is stored safely first, then used unsafely later.

---

## 🛠️ Methodology
1. Identify input points (forms, URL parameters, headers, cookies).
2. Test for injection with simple probes (`'`, `"`, `--`, `OR 1=1`).
3. Determine the injection type (error-based, blind, UNION-based).
4. Extract database metadata (tables, columns) and then data.
5. Assess impact (read/write/delete, OS command execution via extended procedures).

---

## 🧰 Tools
- **sqlmap** – automated detection and exploitation of SQL injection.
- **Burp Suite** – manual request manipulation and Intruder-based fuzzing.

---

## 🧪 Hands-on Labs
- **Lab 1: Authentication Bypass** – test a login form with classic OR-based payloads.
- **Lab 2: UNION-based Extraction** – determine column count, then extract table data via UNION
  SELECT.
- **Lab 3: Blind Boolean-based** – infer data one character at a time from true/false responses.
- **Lab 4: Time-based Blind** – use SLEEP()-based payloads to confirm and extract data via response
  timing.
- **Lab 5: sqlmap automation** – point sqlmap at a vulnerable parameter and enumerate databases.

---

## 🛡️ Defensive Countermeasures
- **Parameterized queries / prepared statements** — the primary, structural fix.
- Least-privilege database accounts for web applications (no DBA rights).
- Input validation/whitelisting as a secondary layer, not a replacement.
- Disable dangerous extended stored procedures (e.g., `xp_cmdshell`) unless required.
- WAF with SQLi signature/anomaly detection as defense-in-depth.

---

## 📄 Reporting
- Vulnerable parameter/endpoint and injection type.
- Proof-of-concept payload and extracted evidence (redacted where sensitive).
- Business impact (data exposure, integrity, potential OS-level compromise).
- Remediation: parameterized queries + least privilege + WAF.

---

## ⚠️ Disclaimer
This content is for **educational and authorized penetration testing only**. Never run SQL
injection payloads against systems you do not own or have explicit written authorization to test.
