# Intro to Network Traffic Analysis – Hack The Box

## 🔍 Project Overview
This hands-on lab focused on analyzing captured network traffic (PCAP files) to detect suspicious behavior using tools like **Wireshark** and **TCPdump**.

**Platform:** Hack The Box  
**Tools Used:** Wireshark, TCPdump  
**Skills Gained:** Packet analysis, protocol decoding, identifying malicious traffic, extracting IOCs (Indicators of Compromise)

---

## 📂 Project Objectives
- Understand the structure and flow of network packets.
- Identify suspicious activity (e.g., DNS tunneling, TCP/UDP anomalies).
- Extract meaningful data from raw traffic.

---

## 🛠 Steps Taken

1. **Loaded PCAP into Wireshark**
   - Applied filters to narrow down traffic (e.g., `http`, `dns`, `tcp.port == 443`)
   - Identified out-of-place DNS queries

2. **Analyzed Traffic Behavior**
   - Spotted unusual DNS tunneling behavior
   - Followed TCP streams to view suspicious payloads

3. **Extracted IOCs**
   - Captured IPs, domain names, file hashes
   - Logged timestamps of activity

4. **Used TCPdump for CLI-Based Capture**
   - Practiced filters: `tcpdump -r capture.pcap -nn`
   - Validated traffic volume and types

---

## 🧠 Key Learnings
- Gained hands-on skills in reading network logs.
- Improved understanding of TCP/IP, DNS tunneling, and packet structure.
- Learned to use CLI and GUI tools for packet inspection.

---

## 📸 Screenshots
_Include screenshots in a `screenshots/` folder and reference them here using Markdown._

![Packet Analysis](screenshots/wireshark-filter.png)

---

## ✅ Result
Successfully identified malicious behavior and extracted indicators for threat hunting.

---

## 📁 Files Included
- `notes.md`: Summary of commands and findings
- `ioc_list.txt`: List of extracted IOCs
- `screenshots/`: Folder with annotated images
# intro-to-network-traffic-analysis-htb
Hands-on lab from Hackthebox focusing on PCAP analysis using TCPDump and Wireshark
