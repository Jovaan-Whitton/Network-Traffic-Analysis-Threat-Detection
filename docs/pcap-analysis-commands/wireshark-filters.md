# Wireshark Display Filters & Explanations

This document includes Wireshark display filters I applied during the network traffic analysis lab.

Wireshark was essential for:
- Inspecting `.pcap` files in a graphical interface
- Filtering large datasets to reveal suspicious behavior (e.g., DNS tunneling, RDP usage)
- Analyzing application-layer protocols and payloads
- Identifying specific content like images or HTTP sessions

Its intuitive interface and powerful filtering language helped validate patterns I observed with `tcpdump` and provided deep insights into the captured traffic.

---

### Filter:
`host 8.8.8.8`  
**Explanation:**  
Displays all traffic to or from the IP address `8.8.8.8` (Google DNS).  
Useful for isolating DNS requests or checking outbound connections to a known host.

---

### Filter:
`http && image-jfif`  
**Explanation:**  
Filters for HTTP packets that include JPEG image transfers (JFIF format).  
Helps identify if image-based content is being transferred, which may be used for steganography or data exfiltration.

![JFIF HTTP filter](/screenshots/wireshark-http-image-jfif.png)

---

### Filter:
`!tcp`  
**Explanation:**  
Excludes all TCP traffic from the view.  
Useful when focusing on UDP, ICMP, or other non-TCP protocols.

![No TCP filter](/screenshots/wireshark-not-tcp.png)

---

### Filter:
`!udp && !arp`  
**Explanation:**  
Excludes both UDP and ARP traffic.  
This helps isolate other traffic types such as ICMP or obscure protocols that may indicate malicious activity.

![No UDP or ARP](/screenshots/wireshark-not-udp-arp.png)

---

### Filter:
`rdp`  
**Explanation:**  
Displays all packets related to **Remote Desktop Protocol (RDP)**.  
Useful for identifying remote desktop sessions or detecting unauthorized remote access attempts.

![RDP traffic filter](/screenshots/wireshark-rdp-traffic.png)

---

**Tip:** These filters help narrow down large packet captures and are critical for quickly identifying signs of malicious behavior, unauthorized access, or unusual network activity.
