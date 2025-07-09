
# 📡 Network Traffic Analysis Lab (Wireshark)

## Project Overview
This two-part lab introduces the foundational skills required to analyze network traffic using Wireshark. In Part 1, I examined pre-captured HTTP traffic to extract embedded files. In Part 2, I conducted a live capture from a suspicious host and analyzed both HTTP and FTP communications to uncover potential exfiltration and malicious behavior.

---

## Objectives
- Use display filters to isolate relevant protocols (HTTP, FTP)
- Extract transferred image files from pcap files
- Follow TCP streams and identify file content
- Perform live packet capture and analyze real-time activity

---

## Tools & Technologies
- **Tool**: Wireshark
- **Protocols Analyzed**: HTTP, FTP
- **Capture Files**: `Wireshark-lab-2.pcap`, live capture

---

## Part 1: HTTP Image Extraction (Pre-Captured File)

### 1. Load the PCAP File
Opened `Wireshark-lab-2.pcap` via:
```
File → Open → Wireshark-lab-2.pcap
```

<details>
<summary>📎 Opened PCAP in Wireshark</summary>
<img src="screenshots/pcap-opened.png" alt="Opened PCAP File">
</details>

---

### 2. Filter for HTTP Traffic
Filtered for HTTP packets to reduce noise:
```
http
```

<details>
<summary>🔍 Filtered HTTP traffic</summary>
<img src="screenshots/http-filter.png" alt="HTTP Filter Applied">
</details>

---

### 3. Follow HTTP Stream & Identify JFIF
Selected a `200 OK` response and followed the TCP stream. Searched for image identifiers such as `JFIF` (JPEG File Interchange Format).

<details>
<summary>🧠 JFIF image located</summary>
<img src="screenshots/jfif-found.png" alt="JFIF Packet Identified">
</details>

---

### 4. Export Embedded Images
Exported image files using:
```
File → Export Objects → HTTP
```

<details>
<summary>📂 Exported image objects</summary>
<img src="screenshots/export-http-objects.png" alt="Export HTTP Objects">
</details>

---

## Part 2: Live Capture and FTP/HTTP Analysis

### 1. Start Live Capture
Captured live traffic on interface `ens224` for a few minutes.

<details>
<summary>🔴 Live capture started</summary>
<img src="screenshots/live-capture.png" alt="Live Capture Started">
</details>

---

### 2. Analyze FTP Traffic
Filtered for FTP:
```
ftp
```
Identified server at `172.16.10.20` and verified login (authenticated or anonymous).

<details>
<summary>📦 FTP communication</summary>
<img src="screenshots/ftp-traffic.png" alt="FTP Traffic Found">
</details>

---

### 3. Extract FTP Files
Filtered `ftp-data` and reassembled payloads to extract transferred files.

<details>
<summary>🧩 FTP data reassembled</summary>
<img src="screenshots/ftp-reassembled.png" alt="FTP Reassembled Data">
</details>

---

### 4. Analyze HTTP Traffic
Filtered HTTP again:
```
http
```
Identified the web server and extracted files by following the HTTP stream.

<details>
<summary>🌐 HTTP file extraction</summary>
<img src="screenshots/http-stream.png" alt="HTTP Stream Followed">
</details>

---

## 🧠 Key Skills & Learnings
- Applied packet-level analysis to uncover suspicious file transfers
- Used filters to reduce noise and zero in on relevant protocols
- Exported images and documents for digital forensics review
- Conducted live capture and applied structured methodology to analyze activity

---

## 📬 Let’s Connect
I'm seeking entry-level roles in **Cybersecurity**, **SOC Analysis**, or **IT Support** where I can continue developing my packet analysis and security operations skills.

**Email**: jovaan.jwhitton@gmail.com  
**LinkedIn**: [linkedin.com/in/jovaan-whitton-profile](https://linkedin.com/in/jovaan-whitton-profile)
