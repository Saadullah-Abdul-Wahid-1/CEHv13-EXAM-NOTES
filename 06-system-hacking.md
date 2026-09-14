# System Hacking

## 📌 Introduction
**System Hacking** is the process of exploiting vulnerabilities in an operating system to gain
unauthorized access, escalate privileges, steal information, or control system resources.
It is a critical phase in penetration testing and ethical hacking to assess the security posture of
target systems.

---

## 🎯 Objectives of System Hacking
- Gain access to the target system.
- Escalate privileges for full administrative control.
- Execute malicious or testing payloads.
- Steal sensitive information (passwords, tokens, documents).
- Create persistence for long-term access.
- Cover tracks to avoid detection.

---

## 🔑 Phases of System Hacking
1. **Gaining Access** – Exploiting system vulnerabilities, using stolen credentials or brute force
   attacks, exploiting misconfigured services.
2. **Privilege Escalation** – Elevating privileges from a low-level user to administrator/root,
   exploiting weak permissions or kernel vulnerabilities, using UAC bypass techniques (Windows).
3. **Executing Applications** – Running malicious scripts, malware, or keyloggers; leveraging
   remote command execution (RCE).
4. **Maintaining Access** – Creating backdoors, modifying registry entries for persistence, adding
   new hidden admin accounts.
5. **Covering Tracks** – Clearing logs and removing evidence, using anti-forensic techniques.

---

## 🧰 Tools for System Hacking
- **Metasploit Framework** – Exploitation and post-exploitation.
- **Mimikatz** – Credential dumping and privilege escalation.
- **CrackMapExec** – Remote code execution over SMB.
- **Netcat** – Backdoor and remote shell.
- **PowerShell Empire** – Post-exploitation framework.
- **Windows Credential Editor (WCE)** – Dump and replay passwords.
- **ProcDump** – Dumping process memory.
- **Keyloggers** – Logging keystrokes for password theft.

---

## 🧪 Practical Steps
### Step 1: Gaining Access
- Exploit vulnerabilities in SMB, RDP, or other services.
- Use phishing attacks to deliver payloads.
- Apply password guessing or brute force.

### Step 2: Privilege Escalation
```bash
whoami /priv                        # check current privileges (Windows)
getsystem                           # Meterpreter: escalate to SYSTEM
```
- Run Local Exploit Suggester in Metasploit.
- Manual UAC bypass techniques.

### Step 3: Executing Applications
- Deploy a keylogger (`keyscan_start` in Meterpreter).
- Execute remote commands with `shell` or `execute` in Meterpreter.
- Drop and execute files.

### Step 4: Maintaining Access
```bash
net user backdoor pass123 /add
net localgroup administrators backdoor /add
```
- Set reverse shell persistence in registry.

### Step 5: Clearing Tracks
```bash
wevtutil cl System
wevtutil cl Security
```
- Remove dropped payloads and scripts.

---

## ⚠️ Common Attack Vectors
- Exploiting unpatched vulnerabilities.
- Weak or reused passwords.
- Misconfigured file and folder permissions.
- Default admin accounts with unchanged credentials.
- Weak service configurations.

---

## 🛡️ Defensive Countermeasures
- Regular patching and updates.
- Enforce strong password policies.
- Disable unnecessary services and ports.
- Implement application whitelisting.
- Enable logging and continuous monitoring.
- Use endpoint detection and response (EDR) tools.
- Enable Credential Guard to hinder credential-dumping tools.

---

## 📄 Reporting & Documentation
When documenting a System Hacking assessment:
- Provide exploited vulnerabilities and methods used.
- List compromised accounts and privilege levels.
- Include screenshots of exploitation and post-exploitation activities.
- Recommend remediation steps.

---

## ⚠️ Disclaimer
This repository is for **educational and authorized penetration testing only**.
Performing these techniques without explicit permission is **illegal** and punishable by law.
Always use a controlled lab environment.
