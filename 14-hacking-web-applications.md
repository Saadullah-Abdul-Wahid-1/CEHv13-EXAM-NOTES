# Hacking Web Applications

## 📌 Introduction
Web application hacking targets flaws in the application logic and code itself, rather than the
underlying server or OS. Most real-world breaches trace back to application-layer vulnerabilities
catalogued by the **OWASP Top 10**.

---

## 🎯 Objectives
- Understand the OWASP Top 10 categories of web application risk.
- Learn how XSS, CSRF, IDOR, and injection-adjacent flaws are exploited.
- Explore session management and access control testing.
- Apply secure coding and defense-in-depth countermeasures.

---

## 🔍 Core Vulnerability Classes
1. **Cross-Site Scripting (XSS)** – injecting client-side scripts that execute in victims' browsers.
   - **Reflected XSS** – payload echoed immediately from a crafted request, not stored.
   - **Stored (Persistent) XSS** – payload is saved server-side and served to many users.
   - **DOM-based XSS** – vulnerability lives entirely in client-side JavaScript.
2. **Cross-Site Request Forgery (CSRF)** – tricks an authenticated victim's browser into submitting
   unwanted requests to a trusted site.
3. **Broken Access Control / IDOR** – users access resources beyond their permissions, often via
   manipulating an ID/reference parameter.
4. **Security Misconfiguration** – default credentials, verbose errors, unnecessary features left
   enabled.
5. **Insecure Deserialization** – untrusted serialized objects trigger code execution or logic
   tampering when deserialized.
6. **Command Injection** – unsanitized input passed to a system shell/command.

---

## 🛠️ Methodology
1. **Map the application** – spider/crawl pages, forms, and parameters.
2. **Identify entry points** – every input: forms, headers, cookies, URL parameters, file uploads.
3. **Test each OWASP Top 10 category** systematically.
4. **Validate and chain findings** where possible (e.g., XSS -> session theft -> account takeover).
5. **Report** with reproduction steps and remediation guidance.

---

## 🧰 Tools
- **Burp Suite / OWASP ZAP** – intercepting proxy for manual and automated testing.
- **Browser DevTools** – inspect cookies, local storage, and network requests.
- **OWASP Top 10 checklist** – structured coverage reference.

---

## 🧪 Hands-on Labs
- **Lab 1: Reflected XSS** – craft a URL parameter payload and confirm script execution.
- **Lab 2: Stored XSS** – submit a payload via a comment/profile field and confirm it fires for
  other viewers.
- **Lab 3: CSRF Proof-of-Concept** – build an auto-submitting HTML form targeting a state-changing
  endpoint while authenticated.
- **Lab 4: IDOR** – increment/change an object ID in a request and confirm unauthorized access.
- **Lab 5: File Upload Testing** – attempt to upload a disguised executable and check for execution.

---

## 🛡️ Defensive Countermeasures
- Content-Security-Policy (CSP) header to restrict script sources.
- Anti-CSRF tokens validated server-side on every state-changing request.
- Enforce authorization checks on every object access (not just authentication).
- Validate file uploads by content/type, store outside the web root, disable execution.
- Secure, HttpOnly cookies; short session lifetimes.
- WAF as a complementary (not sole) layer of defense.

---

## 📄 Reporting
- Vulnerability class (OWASP category), proof-of-concept request/response.
- Impact assessment (what an attacker could achieve).
- CVSS-style severity and clear remediation guidance.

---

## ⚠️ Disclaimer
This content is for **educational and authorized penetration testing only**.
