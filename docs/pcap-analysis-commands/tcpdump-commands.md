## TCPDump Commands and Explanations

This document outlines the `tcpdump` commands I used to capture and analyze network traffic during the Intro to Network Traffic Analysis lab.	

I chose `tcpdump` for its lightweight, command-line capabilities, which allowed me to:
- Capture live traffic from specific interfaces
- Filter by port, protocol, and host during capture or offline analysis
- Save traffic into `.pcap` files for deeper inspection
- Examine packet contents quickly using hex and ASCII output

These commands supported real-time visibility and efficient CLI-based threat hunting during the lab.

### Command:
`which tcpdump`  
**Explanation:**  
Returns the full path of the `tcpdump` binary on your system, confirming it is installed and accessible.

![tcpdump -D](/screenshots/tcpdump-which-D-interface.png)

---

### Command:
`tcpdump -D`  
**Explanation:**  
Lists all available network interfaces (e.g., `eth0`, `wlan0`) you can use for packet capture.

(See above shared screenshot: `tcpdump-which-D-interface.png`)


---

### Command:
`tcpdump -i ens3 -vX`  
**Explanation:**  
Captures live traffic on the `ens3` interface.

(See above shared screenshot: `tcpdump-which-D-interface.png`)

---

### Command:
`sudo tcpdump -i ens3 -vX`
**Explanation:**
Captures live traffic on the `ens3` interface with detailed output.

- `-i ens3`: Interface to listen on  
- `-v`: Verbose output (more header info)  
- `-X`: Shows packet contents in both hex and ASCII
  
![tcpdump -D](/screenshots/tcpdump-ens3-vX.png)

---

### Command:
`tcpdump -i ens3 -nvw ~/Desktop/Test.pcap`  
**Explanation:**  
Captures live traffic and saves it to a `.pcap` file for later analysis.

- `-n`: Don’t resolve hostnames  
- `-v`: Verbose mode  
- `-w ~/sample.pcap`: Write packet data to `sample.pcap` in the home directory
  
![tcpdump -nvw](/screenshots/tcpdump-capture-save.png)

---

### Command:
`tcpdump -nnSXr ~Desktop/Test.pcap`  
**Explanation:**  
Reads packets from a saved `.pcap` file and shows deep packet information.

- `-r`: Read from file  
- `-nn`: Don’t resolve IPs or ports  
- `-S`: Show absolute TCP sequence numbers  
- `-X`: Show full packet content in hex and ASCII
  
(See above shared screenshot: `tcpdump-capture-save.png`)

---

### Command:
`tcpdump -r file.pcap`  
**Explanation:**  
Reads all packets from a saved `.pcap` file without applying any filters.

![tcpdump -r](/screenshots/tcpdump-read-all.png)

---

### Command:
`tcpdump -nnSr ~/Desktop/Test.pcap port 53`  
**Explanation:**  
Reads a .pcap file and filters for DNS traffic (UDP over port 53).

- nn: Don’t resolve hostnames or ports
- S: Show absolute TCP sequence numbers
- r: Read from file
- `port 53`: Standard DNS port
  
![tcpdump DNS filter](/screenshots/tcpdump-read-pcap-port-filter.png)

---

### Command:
`tcpdump -nnSr ~/Desktop/Test.pcap port 80`  
**Explanation:**  
Filters for HTTP and HTTPS traffic from the capture file.

- Reads a .pcap file and filters for HTTP traffic (port 80).
- `port 80`: Standard HTTP port
- Alternatively `port 443` coudlve been used, which is the standard port for HTTPS traffic.
- Syntax and flags match the previous command.
  
*Same screenshot shown above, reused for HTTP traffic example.*

(See above shared screenshot: `tcpdump-read-pcap-port-filter.png`)

---

**Tip:** These commands are essential for inspecting PCAP files in real-time or offline, helping detect DNS queries, HTTP sessions, and potentially malicious network activity.
"""
