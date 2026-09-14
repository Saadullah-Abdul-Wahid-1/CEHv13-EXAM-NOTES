# Scanning Networks

## 📌 Introduction
**Scanning** is the active phase of penetration testing where testers interact with target systems
to identify live hosts, open ports, running services, service versions, and operating systems.
It acts as the bridge between reconnaissance and exploitation, helping uncover attack surfaces.

---

## 🎯 Objectives of Scanning
- Discover active hosts on the target network.
- Identify open ports and services.
- Determine service versions for vulnerability mapping.
- Detect the operating system running on a target.
- Gather data for further exploitation.

---

## 🛠️ Types of Scanning
1. **Port Scanning** – Detects open, closed, or filtered ports.
2. **Service Scanning** – Identifies services running on open ports.
3. **Version Detection** – Determines application/service versions.
4. **OS Fingerprinting** – Detects the target operating system.
5. **Vulnerability Scanning** – Matches detected services to known vulnerabilities.

---

## 📂 Methodology
1. **Identify Live Hosts** – Perform a ping sweep to find responsive systems.
2. **Port Scanning** – Scan for open ports and available services.
3. **Service Version Detection** – Identify the exact software version.
4. **OS Detection** – Determine the target OS for exploit matching.
5. **Vulnerability Mapping** – Link discovered services to CVEs or known flaws.

---

## 🧰 Common Tools for Scanning
- **Nmap** – Advanced port scanning, OS detection, scripting.
- **Masscan** – High-speed port scanning.
- **Netcat (nc)** – Port scanning and banner grabbing.
- **Zenmap** – GUI version of Nmap.
- **Unicornscan** – Asynchronous scanning.
- **Nessus / OpenVAS** – Vulnerability scanning with service mapping.

---

## 📜 Useful Commands & Examples
```bash
# Discover live hosts
nmap -sn 192.168.1.0/24

# Scan a specific host
nmap 192.168.1.10

# Scan multiple hosts
nmap 192.168.1.10 192.168.1.11

# Full port scan
nmap -p 1-65535 192.168.1.10

# OS detection
nmap -O 192.168.1.10

# Vulnerability scanning via NSE
nmap --script vuln 192.168.1.10

# Fast scan with Masscan
masscan -p1-65535 192.168.1.0/24 --rate=1000

# Banner grabbing with Netcat
nc 192.168.1.10 80
```

---

## 📊 Interpreting Scan Results
- **Open Ports** → Potential entry points.
- **Service Versions** → Can be cross-checked with CVE databases.
- **OS Information** → Guides exploit selection.
- **Closed/Filtered Ports** → Indicate firewall filtering or blocked services.

---

## 🛡️ Defensive Countermeasures
- Configure firewalls to block unused ports.
- Disable unnecessary services.
- Use IDS/IPS to detect and block scanning.
- Limit ICMP responses to prevent ping sweeps.
- Apply network segmentation.

---

## 📄 Reporting & Documentation
When documenting scanning results:
- Date/time of scan.
- Tools used and command syntax.
- Detected hosts and IP addresses.
- List of open ports and services.
- Service versions and OS details.
- Screenshots or saved logs.
- Potential vulnerabilities linked to findings.

---

## ⚠️ Disclaimer
This repository is for educational and authorized penetration testing only.
