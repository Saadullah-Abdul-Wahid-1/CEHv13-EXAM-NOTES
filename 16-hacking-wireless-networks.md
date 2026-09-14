# Hacking Wireless Networks

## 📌 Introduction
Wireless (Wi-Fi) networks broadcast over open air, making them inherently exposed to
eavesdropping, unauthorized access, and denial-of-service attacks if not properly secured.

---

## 🎯 Objectives
- Understand the evolution and weaknesses of wireless encryption standards.
- Learn common wireless attack techniques.
- Understand enterprise vs personal Wi-Fi authentication models.
- Apply wireless-specific defensive controls.

---

## 🔐 Encryption Standard Evolution
- **WEP** – uses flawed RC4 with weak IV handling; crackable within minutes. Avoid entirely.
- **WPA** – interim improvement over WEP (TKIP), still has weaknesses.
- **WPA2** – AES-CCMP based, current baseline; PSK mode vulnerable to offline dictionary attacks if
  handshake is captured.
- **WPA3** – introduces SAE (Simultaneous Authentication of Equals), resistant to offline
  dictionary attacks even if traffic is captured.

---

## ⚙️ Common Wireless Attacks
- **Handshake capture + offline cracking** – capture the WPA/WPA2 4-way handshake, crack offline.
- **Deauthentication attack** – forcibly disconnects a client to force a re-handshake for capture.
- **Evil Twin** – rogue AP mimics a legitimate SSID to intercept victim traffic.
- **WPS PIN brute-force** – exploits weak WPS PIN implementations (e.g., via Reaver).
- **Wardriving** – scanning/mapping accessible wireless networks while mobile.
- **RF jamming** – wireless denial-of-service via radio interference.
- **MAC spoofing** – bypasses MAC filtering since addresses are sent in cleartext.

---

## 🧰 Tools
- **Aircrack-ng suite** – capture (airodump-ng), deauth (aireplay-ng), cracking (aircrack-ng).
- **Reaver** – WPS PIN brute-forcing.
- **Wireshark** – 802.11 frame analysis.

---

## 🧪 Hands-on Labs
- **Lab 1: Handshake Capture** – use airodump-ng to capture a WPA2 4-way handshake.
- **Lab 2: Deauthentication** – use aireplay-ng to force a client reconnect.
- **Lab 3: Offline Dictionary Attack** – run aircrack-ng against the captured handshake with a
  wordlist.
- **Lab 4: Evil Twin Setup (lab-only)** – stand up a rogue AP mimicking a target SSID in an
  isolated test environment.

---

## 🛡️ Defensive Countermeasures
- Use **WPA3** or, at minimum, WPA2-AES with a strong, unique passphrase.
- Use **WPA2/WPA3-Enterprise (802.1X/RADIUS)** for per-user authentication in enterprise settings.
- Disable WPS or use a version resistant to PIN brute-forcing.
- Deploy a **Wireless IDS (WIDS)** to detect rogue APs and deauth floods.
- Treat SSID hiding and MAC filtering as obscurity, not real security controls.

---

## 📄 Reporting
- Encryption standard in use and any weaknesses identified.
- Captured evidence (handshake, cracked passphrase if authorized).
- Rogue AP / WIDS coverage gaps.
- Remediation: upgrade encryption, enterprise auth, WIDS deployment.

---

## ⚠️ Disclaimer
This content is for **educational and authorized penetration testing only**. Attacking wireless
networks without explicit permission is illegal in most jurisdictions.
