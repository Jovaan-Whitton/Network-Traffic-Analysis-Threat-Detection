# RDP Traffic Decryption – Wireshark Lab

## Project Overview

This guided analysis lab focuses on decrypting and analyzing **RDP (Remote Desktop Protocol)** traffic using Wireshark. Leveraging a captured `.pcapng` file and a recovered **RSA private key**, I decrypted encrypted RDP sessions to view session details in cleartext. This simulates a real-world forensic scenario where encrypted traffic must be inspected during an investigation.

---

## Objectives

- Identify and verify encrypted RDP traffic
- Import a recovered RSA private key to decrypt traffic in Wireshark
- Analyze decrypted traffic to extract session information
- Demonstrate post-decryption forensics (TCP stream following, object extraction, session metadata)

---

## Tools & Environment

- **Wireshark**: Traffic analysis and TLS decryption
- **RSA Private Key**: Used to decrypt TLS session
- **PCAP File**: `rdp.pcapng`
- **Environment**: Simulated incident response scenario (HTB Academy)

---

## Key Steps

### 1. Load the PCAP

- Open `rdp.pcapng` in Wireshark.

### 2. Filter for RDP traffic

```wireshark
rdp 
- No readable results appeared because RDP traffic is encrypted by default
- Verified TCP sessions activity using: `tcp.port == 3389`

### 3. Configure Wireshark to Use RSA Key
Navigated to:

- Edit → Preferences → Protocols → TLS
- Edited RSA Keys list with:

-IP Address: 10.129.43.29
-Port: 3389
-Protocol: tpkt
-Key File: server.key
-Refreshed PCAP file to reprocess traffic with new decryption settings.

### 4. Analyze Decrypted RDP Traffic
Applied:

- rdp
- Decrypted packets now visible:
- rdp.slow.path.pduType
- Session keystrokes and metadata

- Used Follow TCP Stream to analyze the full conversation between client and server.

Findings
Initiating Host: 10.129.43.27

Target RDP Server: 10.129.43.29

User Account Used: bob.infra

Key Takeaways
Wireshark can decrypt TLS traffic with the appropriate private key

This allows full visibility into user actions and session behavior

Demonstrates the importance of proper key management in enterprise environments

Let’s Connect
I'm actively seeking IT Support, SOC Analyst, or Security Operations roles where I can apply practical cybersecurity skills such as traffic analysis and decryption.

Email: jovaan.jwhitton@gmail.com
LinkedIn: linkedin.com/in/jovaan-whitton-profile

