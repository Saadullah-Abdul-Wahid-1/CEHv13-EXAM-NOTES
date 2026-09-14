# Hacking Mobile Platforms

## 📌 Introduction
Mobile devices (Android/iOS) carry sensitive personal and corporate data, and are targeted through
malicious apps, weak app-level security, and social engineering (e.g., malicious QR codes).

---

## 🎯 Objectives
- Understand mobile OS security models (sandboxing, permissions).
- Understand the risks of rooting/jailbreaking.
- Learn the OWASP Mobile Top 10 risk categories.
- Apply mobile-specific testing and defensive practices.

---

## 🔐 Core Mobile Security Concepts
- **Application Sandboxing** – isolates each app's data/process from others by default.
- **Runtime Permissions** – dangerous permissions requested at runtime (Android 6.0+), not just
  install time.
- **Rooting / Jailbreaking** – removes OS-imposed restrictions; weakens the sandbox and verified
  boot protections even though it grants more user control.
- **Verified/Secure Boot** – cryptographically checks the boot chain for tampering.
- **Mobile Device Management (MDM)** – centrally enforces policy, remote wipe, and app control
  across an organization's device fleet.

---

## 🔍 OWASP Mobile Top 10 Themes (selected)
- **Insecure Data Storage** – sensitive data stored unencrypted in local files/shared prefs/logs.
- **Insecure Communication** – missing TLS or certificate validation.
- **Insufficient Cryptography** – weak or improperly implemented crypto.
- **Reverse Engineering Risk** – decompiled APKs exposing hardcoded secrets/business logic.
- **Insecure Authentication/Authorization** – weak session or token handling on mobile clients.

---

## 🧰 Tools
- **Burp Suite (as MITM proxy)** – intercept mobile app network traffic.
- **JADX / apktool** – decompile Android APKs for static review.
- **MobSF (Mobile Security Framework)** – automated static/dynamic mobile app analysis.

---

## 🧪 Hands-on Labs
- **Lab 1: Traffic Interception** – configure a test device to route through Burp Suite; inspect
  API calls for missing TLS/cert pinning.
- **Lab 2: APK Static Review** – decompile a sample APK and search for hardcoded API
  keys/credentials.
- **Lab 3: Permission Review** – audit an app's requested permissions against its actual
  functionality.
- **Lab 4: Insecure Storage Check** – inspect an app's local storage/shared preferences for
  plaintext sensitive data.

---

## 🛡️ Defensive Countermeasures
- Enforce **certificate/SSL pinning** to resist MITM even with a rogue trusted CA cert.
- Encrypt sensitive local storage; avoid storing secrets in plaintext.
- Request only the permissions the app's functionality genuinely needs (least privilege).
- Use **full-device encryption** and enforce screen-lock policies via MDM.
- Distribute apps only via official, vetted app stores.

---

## 📄 Reporting
- App/platform tested, OWASP Mobile Top 10 category per finding.
- Evidence (intercepted traffic, decompiled strings, storage dumps).
- Remediation guidance (pinning, encryption, permission tightening).

---

## ⚠️ Disclaimer
This content is for **educational and authorized security testing only**, performed on devices/apps
you own or have explicit permission to test.
