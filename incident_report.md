# 🛡️ Cybersecurity Incident Report

## 📌 Project: Network Traffic Analysis – DNS & ICMP Issue

**Date of Incident:**  
June 25, 2025 – 1:24 PM

**Analyst:**  
David Sayndee

---

## 🧠 Incident Summary

Several users reported that they were unable to access the client website:  
**`www.yummyrecipesforme.com`**  
They encountered the error:  
> **"Destination port unreachable"**

Initial checks confirmed that even manual attempts to access the site resulted in the same error.

---

## 🔍 Technical Investigation

### Tools Used:
- `tcpdump` (network analyzer)
- DNS & ICMP protocol review

### Process:
1. A DNS query was sent using the UDP protocol to resolve the domain name.
2. `tcpdump` showed that the UDP packets to port 53 received ICMP responses:
   > **"udp port 53 unreachable"**
3. This confirmed that DNS resolution was failing — no service was listening on port 53.

---

## 🔐 Protocols Involved:
- **DNS** (UDP/Port 53) – used to resolve domain names
- **ICMP** – used to return error messages indicating unreachable destinations

### Key Flag:
- `A?` DNS query flag shown in logs confirms a name lookup was attempted.

---

## 🚨 Root Cause Analysis

The analysis indicates that:
- DNS traffic was **not reaching** the intended server on port 53
- ICMP packets reported this as unreachable

### Possible Causes:
- DNS server is offline
- Firewall blocking UDP traffic to port 53
- DDoS or DNS cache poisoning attack targeting the server

---

## ✅ Recommended Next Steps

- Verify DNS server availability and logs
- Check firewall rules for inbound/outbound traffic to port 53
- Run vulnerability and performance scans on DNS infrastructure
- Monitor for unusual traffic patterns or attacks

---

## 💡 Lessons Learned

- Importance of DNS protocol and port mapping in web access
- ICMP can be a powerful diagnostic tool in traffic analysis
- Incident response depends heavily on fast packet capture and interpretation

---

*Prepared by:*  
**David Sayndee**  
Cybersecurity Analyst
