#  Network Traffic Analysis Lab (Wireshark)

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

`File → Open → Wireshark-lab-2.pcap`

---

### 2. Filter for HTTP Traffic
Filtered for HTTP packets to reduce noise:

Filter: `http`

<details>
  <summary> Filtered HTTP traffic</summary>
  
![Filtered HTTP Traffic](/screenshots/http-filter.png)

</details>

---

### 3. Follow HTTP Stream & Identify JFIF
Selected a `200 OK` response and followed the TCP stream. Searched for image identifiers such as `JFIF` (JPEG File Interchange Format).

<details>
  <summary> JFIF image located</summary> 

![Follow TCP Stream](/screenshots/follow-tcp-stream.png)
![TCP Stream Results](/screenshots/tcp-stream-results.png)
![HTTP and Image-JFIF Filter](/screenshots/http-and-image-filter.png)

</details>

---

### 4. Export Embedded Images
Exported image files using:

`File → Export Objects → HTTP`

<details>
  <summary>Exported image objects</summary>
  
![Objects to Export](/screenshots/objects-to-export.png)
![Exported Objects](/screenshots/-exported-objects.png)

</details>

---

## Part 2: Live Capture and FTP/HTTP Analysis

### 1. Start Live Capture
Captured live traffic on interface `ens224` for a few minutes.

---

### 2. Analyze FTP Traffic
Filtered for FTP:

`Filter: ftp`

Identified server at `172.16.10.20` and verified anonymous login.

<details>
  <summary> FTP communication</summary>
  
![FTP Traffic Filter](/screenshots/ftp-filter.png)
![FTP Request Command](/screenshots/ftp-req-command-filter.png)

</details>

---

### 3. Extract FTP Files
Filtered `ftp-data` and reassembled payloads to extract transferred files.

<details>
  <summary>FTP data reassembled</summary>
  
![FTP Data](/screenshots/ftp-data-filter.png)
![FTP-Data-Stream](/screenshots/follow-ftp-data-stream.png)
![FTP Data Stream Results](/screenshots/ftp-data-stream-results.png)
![Confirmed Data Transfer](/screenshots/data-transfer-captured.png)

</details>

---

## Key Skills & Learnings
- Applied packet-level analysis to uncover suspicious file transfers
- Used filters to reduce noise and zero in on relevant protocols
- Exported images and documents for digital forensics review
- Conducted live capture and applied structured methodology to analyze activity

---

## Let’s Connect
I'm seeking entry-level roles in **Cybersecurity**, **SOC Analysis**, or **IT Support** where I can continue developing my packet analysis and security operations skills.

**Email**: jovaan.jwhitton@gmail.com  
**LinkedIn**: [linkedin.com/in/jovaan-whitton-profile](https://linkedin.com/in/jovaan-whitton-profile)
