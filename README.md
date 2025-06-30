# Intro to Network Traffic Analysis – Hack The Box

## Project Overview
This hands-on lab from Hack The Box focused on analyzing captured network traffic using **Wireshark** and **tcpdump**. The goal was to detect suspicious behavior, extract indicators of compromise (IOCs), and understand traffic anomalies that could indicate cyberattacks.

---

## Objectives
- Load and filter PCAP files using Wireshark and tcpdump
- Identify DNS tunneling and suspicious TCP sessions
- Extract meaningful metadata and IOCs
- Reconstruct attacker behavior from traffic logs

---

## Tools & Technologies
- Platform: Hack The Box Academy
- Tools: Wireshark, tcpdump
- Environment: Simulated PCAP Analysis Lab
- File Types: `.pcap`, `.txt`, `.png`

---

## Steps Taken

1. **Opened PCAP in Wireshark**
   - Applied filters: `tcp`, `rdp`, `!udp && !arp`
   - Observed DNS tunneling signatures

2. **Used tcpdump for CLI Analysis**
   - Filtered packet streams to isolate anomalies
   - Verified findings from Wireshark in raw format

3. **Extracted Indicators of Compromise**
   - Noted suspicious domains, IPs, and file hashes
   - Created IOC list for reporting

4. **Documented Findings**
   - Summarized behavior patterns and matched them to C2 communication tactics

---

## Key Skills & Learnings
- Improved ability to interpret raw packet data
- Practiced filtering and isolating relevant traffic
- Identified early-stage attack behavior
- Strengthened IOC extraction and documentation workflow

---

## Screenshots
### DNS Tunneling Detection
![DNS Tunneling Detected](screenshots/dns-tunnel-detected.png)
### Wireshark HTTP Filter Results
![Wireshark HTTP Filter](screenshots/wireshark-http-filter.png)
### TCPdump Output Highlighting Suspicious Traffic
![TCPdump Output](screenshots/tcpdump-suspicious.png)

---

## Documentation
- [PCAP Analysis Commands](docs/pcap-analysis-commands)
- [Network Findings](network-findings.md)
- [Visual walkthrough of key steps](screenshots/)

---

## ✅ Result
Completed the lab with successful identification of malicious behavior within PCAP files. Demonstrated the ability to extract, document, and analyze IOCs—skills critical for SOC and incident response roles.

---

## Let’s Connect
I’m actively seeking IT Support or SOC Analyst roles in New York City or remote/hybrid environments. Let’s connect!

**Email**: jovaan.jwhitton@gmail.com  
**LinkedIn**: [linkedin.com/in/jovaan-whitton-profile](https://linkedin.com/in/jovaan-whitton-profile)

