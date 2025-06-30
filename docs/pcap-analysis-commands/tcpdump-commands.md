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

---

### Command:
`tcpdump -D`  
**Explanation:**  
Lists all available network interfaces (e.g., `eth0`, `wlan0`) you can use for packet capture.

---

### Command:
`tcpdump -i eth0 -vX`  
**Explanation:**  
Captures live traffic on the `eth0` interface with detailed output.

- `-i eth0`: Interface to listen on  
- `-v`: Verbose output (more header info)  
- `-X`: Shows packet contents in both hex and ASCII

---

### Command:
`tcpdump -i eth0 -nvw ~/sample.pcap`  
**Explanation:**  
Captures live traffic and saves it to a `.pcap` file for later analysis.

- `-n`: Don’t resolve hostnames  
- `-v`: Verbose mode  
- `-w ~/sample.pcap`: Write packet data to `sample.pcap` in the home directory

---

### Command:
`tcpdump -nnSXr sample.pcap`  
**Explanation:**  
Reads packets from a saved `.pcap` file and shows deep packet information.

- `-r`: Read from file  
- `-nn`: Don’t resolve IPs or ports  
- `-S`: Show absolute TCP sequence numbers  
- `-X`: Show full packet content in hex and ASCII

---

### Command:
`tcpdump -r file.pcap`  
**Explanation:**  
Reads all packets from a saved `.pcap` file without applying any filters.

---

### Command:
`tcpdump -r file.pcap udp and port 53`  
**Explanation:**  
Filters for DNS traffic in the `.pcap` file.

- `udp`: Protocol used by DNS  
- `port 53`: Standard DNS port

---

### Command:
`tcpdump -r file.pcap '(port 80 or port 443)'`  
**Explanation:**  
Filters for HTTP and HTTPS traffic from the capture file.

- `port 80`: HTTP  
- `port 443`: HTTPS  
- Parentheses are needed to group filters correctly in `tcpdump`
