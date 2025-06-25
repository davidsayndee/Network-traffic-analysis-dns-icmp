# 🛡️ Network Traffic Analysis – DNS & ICMP Incident Response

## 📌 Project Overview
This project investigates a DNS-related network issue where users received a **“destination port unreachable”** error. As a cybersecurity analyst, I used tcpdump and ICMP packet analysis to identify that the DNS server was not responding to queries.

---

## 🧰 Tools Used
- tcpdump
- DNS / ICMP Protocol Analysis
- Linux Command Line
- Wireshark (planned)

---

## 📊 Summary of Findings
- DNS request to `www.yummyrecipesforme.com` failed on port 53
- ICMP returned: **udp port 53 unreachable**
- Likely causes:
  - DNS server is down or unreachable
  - Port 53 is blocked by a firewall
  - Potential DNS DoS or cache poisoning attack

---

## 🧠 Key Learnings
- Analyzing UDP/DNS failures
- Reading ICMP response packets
- Troubleshooting using packet analyzers

---

## 🖼️ Screenshots

### DNS Packet Capture

![DNS Error Screenshot](screenshots/screenshot.png)

---

## 📁 Files Included
- `incident_report.md` – Full incident write-up
- `README.md` – Summary and project breakdown
