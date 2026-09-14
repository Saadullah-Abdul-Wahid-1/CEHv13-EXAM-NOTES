# 🕵️‍♂️ Footprinting – Complete Guide

## 📌 Introduction
**Footprinting** is the first phase of ethical hacking and penetration testing.
It involves gathering information about the target system, organization, or network to identify
potential attack vectors. Footprinting helps attackers (and security professionals) understand the
digital footprint of their target.

---

## 🎯 Objectives of Footprinting
- Collect publicly available information about the target.
- Map the target's digital presence (domains, subdomains, IP ranges).
- Identify technologies used by the target (servers, frameworks, apps).
- Gather employee or organizational details for social engineering.
- Prepare for further penetration testing phases.

---

## 📂 Types of Footprinting
1. **Passive Footprinting**
   - Information gathering without direct interaction.
   - Example: WHOIS, DNS records, social media, job postings.
2. **Active Footprinting**
   - Direct interaction with the target system/network.
   - Example: Nmap scans, traceroute, ping sweeps.

---

## 🛠️ Techniques of Footprinting
- **Search Engines** – Google Dorks, Bing, Shodan, Censys.
- **WHOIS Lookup** – Domain registration details.
- **DNS Enumeration** – NSLookup, dig, dnsenum, Fierce.
- **Social Media Profiling** – LinkedIn, Twitter, Facebook intelligence.
- **Email Harvesting** – theHarvester, Hunter.io.
- **Website Footprinting** – Wappalyzer, WhatWeb, BuiltWith.
- **Network Recon** – Traceroute, Ping, Nmap.
- **Metadata Extraction** – ExifTool, FOCA.
- **Public Data Sources** – Job postings, press releases, Google Alerts.

---

## 🧰 Common Tools
- **theHarvester** – Email and domain information gathering.
- **Maltego** – Relationship mapping and intelligence.
- **Recon-ng** – Web-based reconnaissance framework.
- **Shodan** – Search engine for IoT and connected devices.
- **Censys** – Internet-wide scanning engine.
- **FOCA** – Metadata analysis tool.
- **OSINT Framework** – Collection of OSINT resources.

---

## 🧪 Hands-on Labs
- **Lab 1: WHOIS Lookup** – Perform WHOIS lookup on a target domain.
- **Lab 2: DNS Enumeration** – Use `nslookup` or `dig` to extract DNS records.
- **Lab 3: Email Harvesting** – Collect emails using **theHarvester**.
- **Lab 4: Search Engine Footprinting** – Use **Google Dorks** to find sensitive files or exposed
  directories.
- **Lab 5: Metadata Extraction** – Extract document metadata with **ExifTool** or **FOCA**.
- **Lab 6: Subdomain Discovery** – Identify subdomains using tools like **Sublist3r** or **Amass**.

---

## 🛡️ Defensive Countermeasures
- Limit public exposure of sensitive data.
- Use privacy protection for WHOIS records.
- Disable directory listing on web servers.
- Train employees against oversharing on social media.
- Monitor OSINT sources for data leaks.
- Regularly audit digital footprint of the organization.

---

## 📄 Reporting
A proper **Footprinting Report** should include:
- Target information summary.
- List of discovered domains, subdomains, IPs.
- Employee or email addresses (if any).
- Tools and methods used.
- Risk analysis of exposed information.
- Defensive recommendations.

---

## ⚠️ Disclaimer
This content is for **educational and authorized penetration testing only**.
Unauthorized reconnaissance and footprinting of systems without permission is **illegal**.
