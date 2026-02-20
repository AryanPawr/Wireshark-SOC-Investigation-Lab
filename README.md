# 🔍 Wireshark Network Traffic Investigation (SOC Simulation)

## 📌 Project Overview

In this project, I performed a simulated Security Operations Center (SOC) investigation using Wireshark. The objective was to capture and analyze network traffic in a controlled lab environment and identify any suspicious activity that could indicate phishing or data exfiltration.

This project helped me understand how real-world analysts monitor and investigate network communications at the packet level.

## 🎯 Objectives

- Capture and analyze live network traffic  
- Inspect DNS, TCP, and HTTP protocols  
- Reconstruct TCP sessions  
- Identify unusual outbound connections  
- Simulate a basic SOC investigation workflow  
- Document findings and recommended mitigations  

## 🖥️ Lab Environment

- Host OS: macOS / Windows  
- Virtualization: VirtualBox  
- Tool Used: Wireshark  
- Test Setup: Local VM-based lab (controlled environment)  
- Network Type: NAT / Host-Only  

## 🔎 Investigation Process

### 1️⃣ Packet Capture  
Captured live traffic from the active network interface while generating normal browsing activity.

### 2️⃣ Traffic Filtering  
Applied protocol-based filters including:

- dns
- tcp
- http
- http.request.method == "POST"
- tcp.flags.syn == 1

These filters helped isolate relevant traffic and reduce noise.

### 3️⃣ DNS Analysis  
Reviewed DNS queries and responses to understand domain resolution behavior. Checked for irregular or suspicious domain patterns.

### 4️⃣ TCP Session Analysis  
Observed TCP three-way handshakes (SYN → SYN-ACK → ACK) and used **Follow TCP Stream** to reconstruct full communication sessions between client and server.

### 5️⃣ HTTP Inspection  
Inspected HTTP headers and request methods (GET/POST). Noted that unencrypted HTTP traffic exposes data in plaintext, highlighting potential security risks.

---

## 🚨 Observations

- DNS queries are visible in plaintext  
- HTTP traffic can expose sensitive information if not encrypted  
- Outbound traffic patterns can be traced using IP-based filtering  
- Large outbound packets may indicate possible data transfer activity  


## 🛡️ Mitigation Recommendations

- Enforce HTTPS-only browsing policies  
- Implement DNS filtering and monitoring  
- Block suspicious IP addresses at firewall level  
- Deploy IDS/IPS solutions for anomaly detection  
- Conduct regular phishing awareness training  

## ⚠️ Challenges Faced

- Initially struggled to filter out background system noise in the packet capture  
- Required practice to properly interpret TCP flags and session flow  
- Understanding packet structure (Frame → Ethernet → IP → TCP → Application) took time  
- Differentiating between normal traffic and potentially suspicious behavior required careful review  

These challenges improved my ability to analyze traffic methodically rather than jumping to conclusions.


## 🔑 Skills Demonstrated

- Packet-level network traffic analysis  
- Practical use of Wireshark filters  
- DNS, TCP, and HTTP protocol inspection  
- Basic SOC-style investigation workflow  
- Identifying potential Indicators of Compromise (IOCs)  
- Technical documentation and reporting  


## 🇦🇺 Relevance to Australian SOC Roles

This project reflects core tasks performed by entry-level SOC Analysts in Australia, including:

- Monitoring network traffic  
- Investigating suspicious activity  
- Identifying Indicators of Compromise  
- Documenting findings for escalation  

The hands-on experience with packet inspection and structured investigation strengthens my foundation for Security Operations and Blue Team roles.


## 📌 Summary

This lab strengthened my understanding of how network communication works at a technical level and how security analysts detect and investigate suspicious behavior using tools like Wireshark.
