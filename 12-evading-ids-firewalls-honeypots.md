# 🔥 Evading IDS, Firewalls, and Honeypots

## 📌 Introduction
Firewalls, Intrusion Detection Systems (IDS), and Intrusion Prevention Systems (IPS) are essential
components in network security.
- **Firewall**: Controls incoming and outgoing network traffic based on predetermined rules.
- **IDS**: Monitors network/system activities for malicious actions and policy violations.
- **IPS**: Detects and actively prevents identified threats in real-time.

---

## 🎯 Objectives
- Understand the role of firewalls, IDS, and IPS in cybersecurity.
- Learn the differences between IDS and IPS.
- Explore firewall types, architectures, and deployment methods.
- Perform practical exercises to analyze, detect, and prevent attacks.

---

## 🛡️ Firewall

### Types of Firewalls
1. **Packet-Filtering Firewall** – rules based on IP/port/protocol, no connection state awareness.
2. **Stateful Inspection Firewall** – tracks the state of active connections.
3. **Proxy Firewall** – intermediates connections at the application layer.
4. **Next-Generation Firewall (NGFW)** – deep packet inspection, app-awareness, integrated IPS.

### Firewall Architectures
- Bastion Host
- Screened Subnet (DMZ)
- Dual-Homed Host

### Example Commands
```bash
# View firewall rules (Linux - iptables)
sudo iptables -L

# View firewall rules (Windows)
netsh advfirewall firewall show rule name=all
```

---

## 👁️ IDS (Intrusion Detection System)

### Types of IDS
- **NIDS** – Network-based IDS
- **HIDS** – Host-based IDS

### Detection Methods
- Signature-Based Detection – matches known attack patterns; blind to zero-days.
- Anomaly-Based Detection – flags deviations from a "normal" baseline.
- Hybrid Detection – combines both approaches.

### Example Tool – Snort
```bash
# Run Snort in packet capture mode
snort -i eth0 -A console
```

---

## 🛑 IPS (Intrusion Prevention System)

### Functions
- Detect and block malicious traffic.
- Automatically update rule sets.
- Prevent known attack signatures.

### Example Tool – Suricata
```bash
# Run Suricata in IPS mode
suricata -c /etc/suricata/suricata.yaml -i eth0
```

---

## 🕳️ Honeypots & Honeynets
- **Honeypot** – a decoy system designed to attract, detect, and study attacker behavior in an
  isolated environment.
- **Honeynet** – a full network of honeypots simulating a realistic production environment for
  richer threat intelligence.

---

## 🥷 Evasion Techniques (for awareness/detection purposes)
- **Fragmentation** – splitting payloads across multiple packets to dodge signature matching.
- **Obfuscation/Encoding** – URL/Unicode encoding to disguise malicious payloads.
- **Timing manipulation** – slowing an attack to stay under rate-based detection thresholds.

---

## 🧪 Hands-On Labs
### Lab 1 – Configure Linux Firewall (iptables)
```bash
# Block incoming traffic from an IP
sudo iptables -A INPUT -s 192.168.1.100 -j DROP
```

### Lab 2 – Detect Suspicious Traffic with Snort
```bash
snort -i eth0 -A console -c /etc/snort/snort.conf
```

### Lab 3 – Prevent Attack with Suricata
```bash
suricata -c /etc/suricata/suricata.yaml -q 0 -i eth0
```

---

## 🛡️ Defensive Best Practices
- Layer firewalls, IDS/IPS, and honeypots as part of defense in depth.
- Keep signature databases current; supplement with anomaly-based detection for zero-days.
- Regularly tune detection thresholds to reduce false positives/negatives.

---

## ⚠️ Disclaimer
This content is for **educational and authorized penetration testing/defensive research only**.
