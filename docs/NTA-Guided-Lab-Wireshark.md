# Network Traffic Analysis- Guided Lab

## Project Overview

This lab simulates an internal incident response scenario where we analyzed suspicious traffic originating from a known internal host. Using a provided `.pcap` file and Wireshark, we investigated abnormal communication patterns, filtered unusual protocols, followed TCP streams, and uncovered malicious behavior such as account creation and lateral movement.

---

## Objectives
- Filter `.pcap` data to isolate suspicious host activity
- Use Wireshark plugins to analyze conversations and protocols
- Identify patterns indicating exploitation and privilege escalation
- Follow TCP streams and uncover plain-text commands
- Recommend proper incident response (IR) procedures

---

## Tools & Dataset
- **Tool:** Wireshark
- **Capture File:** `NTA-guided.pcap`
- **Target Host:** `10.129.43.4`
- **Secondary Host:** `10.129.43.29`
- **Suspected Port:** `4444` (unknown protocol)

---

## Define Scope and Identify Traffic
- Focused on traffic **from 10.129.43.4** over the last **48 hours**
- Used `Conversations` and `Protocol Hierarchy` tools to narrow down key traffic

<details>
  <summary>Conversations & Protocol Overview</summary>

![Conversations Tab](/screenshots/wireshark-conversation-tool.png)

![Protocol Hierarchy](/screenshots/wireshark-hierarchy-tool.png)

</details>

---

## Filter UDP and TCP Traffic

### Step 1: Filter UDP
Filtered only `udp` packets:

`!tcp`

Result: Normal traffic (ARP, NAT, SSDP)

<details>
  <summary>UDP Filtering</summary>

![UDP Traffic](/screenshots/wireshark-udp-traffic.png)

</details>

### Step 2: Filter TCP
Filtered only `tcp` by removing `udp` and `arp`:

`!udp && !arp`
Result: Single persistent TCP connection between `10.129.43.4` and `10.129.43.29`

<details>
  <summary>TCP Traffic</summary>

![TCP Filtered](/screenshots/tcp-traffic-results.png)

</details>

---

## Session Analysis – Suspicious TCP Activity
### Three-Way Handshake Verified
Observed a full TCP session established, but no teardown:

<details>
  <summary>TCP Handshake</summary>

![TCP Handshake](/screenshots/odd-tcp-traffic.png)

</details>

### Follow TCP Stream
Followed TCP stream from packet 3 — session still open.

<details>
<summary>Followed Stream</summary>
<br>

![TCP Stream Output](/screenshots/compromised-tcp-stream.png)
![TCP Stream Output](/screenshots/compromised-tcp-stream1.png)

</details>

- Commands executed:
  - `whoami`, `ipconfig`, `dir`
  - Created user: `hacker`
  - Added to group: `administrators`

---

## Findings & IR Recommendation
### Findings:
- Reconnaissance and privilege escalation from host `10.129.43.4`
- Account `hacker` created on host `10.129.43.29`
- Used unmonitored TCP session (likely backdoor via port 4444)
- RDP later used from Bob’s host to pivot further

### Recommendations:
- Quarantine affected host (Bob’s machine)
- Launch full Incident Response plan
- Audit other internal endpoints for persistence and lateral movement

---

## Summary
This lab provided practical experience in:
- Real-world network forensic investigation
- Using Wireshark’s built-in tools (filters, stream following, protocol views)
- Identifying exploitation via command-and-control traffic
- Practicing structured analysis and reporting to IR teams

---

## Let’s Connect
I'm seeking entry-level roles in **Cybersecurity**, **SOC Analysis**, or **Incident Response** where I can use my growing traffic analysis and IR skills.

**Email**: jovaan.jwhitton@gmail.com  
**LinkedIn**: [linkedin.com/in/jovaan-whitton-profile](https://linkedin.com/in/jovaan-whitton-profile)
