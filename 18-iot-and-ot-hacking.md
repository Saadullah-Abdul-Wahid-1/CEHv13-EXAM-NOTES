# IoT and OT Hacking

## 📌 Introduction
Internet of Things (IoT) devices and Operational Technology (OT/ICS/SCADA) systems increasingly
connect physical-world processes to networks, often with weaker security controls than
traditional IT — making them high-value, frequently under-protected targets.

---

## 🎯 Objectives
- Understand why IoT devices are commonly vulnerable.
- Understand OT/ICS-specific constraints (uptime, patch difficulty, legacy protocols).
- Learn IoT-focused reconnaissance and firmware analysis techniques.
- Apply segmentation and hardening best practices.

---

## 🔍 Why IoT/OT Is High-Risk
- Default/hardcoded credentials frequently left unchanged.
- Limited compute resources for robust on-device security controls.
- Infrequent or unsupported firmware updates.
- OT/ICS systems often require continuous uptime, making patching operationally difficult.
- Legacy ICS protocols (e.g., **Modbus**) historically lack authentication/encryption.

---

## 🧰 Tools & Techniques
- **Shodan / Censys** – discover internet-exposed IoT/ICS devices and default services.
- **Binwalk** – extract and analyze firmware images for hardcoded secrets or vulnerabilities.
- **Hardware interfaces (UART/JTAG/SPI)** – physical debug ports that may expose direct access.

---

## 🧪 Hands-on Labs
- **Lab 1: Shodan Reconnaissance** – search for exposed IoT device banners and identify default
  service exposure (lab/authorized scope only).
- **Lab 2: Firmware Extraction** – run binwalk against a sample firmware image and extract its
  filesystem.
- **Lab 3: Default Credential Check** – attempt documented default credentials against a lab IoT
  device to confirm the risk.
- **Lab 4: Network Segmentation Review** – verify IoT devices sit on an isolated VLAN separate from
  critical systems.

---

## ⚠️ Notable Risk Patterns
- **Mirai-style botnets** – scan the internet and brute-force well-known default IoT credentials
  to build large botnets.
- **Insecure firmware update mechanisms** – unsigned/unverified updates allow malicious firmware
  to be pushed to a device.
- **OT safety considerations** – testing live ICS/OT environments can cause real-world physical
  safety incidents; prefer non-production replicas where possible.

---

## 🛡️ Defensive Countermeasures
- Change all default credentials at setup; enforce strong, unique passwords.
- Segment IoT/OT devices onto isolated VLANs, separate from critical infrastructure.
- Verify firmware update signing/integrity before deployment.
- Reference **NIST SP 800-82** for ICS-specific security guidance.
- Apply rigorous change control and testing before patching OT systems.

---

## 📄 Reporting
- Devices/protocols assessed and exposure found (e.g., Shodan-indexed services).
- Firmware analysis findings (hardcoded secrets, vulnerable components).
- Segmentation gaps and default-credential findings.
- Remediation: credential rotation, segmentation, firmware integrity checks.

---

## ⚠️ Disclaimer
This content is for **educational and authorized security testing only**. OT/ICS testing carries
real-world physical safety risk and must be scoped and authorized with extreme care.
