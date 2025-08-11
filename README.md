# Wireshark Network Traffic Analysis

## 📜 Project Overview
This project captures and analyzes network traffic using **Wireshark**.  
The goal is to:
1. Capture live network packets.
2. Filter by relevant protocols.
3. Identify and analyze at least three different protocols.
4. Export the capture file (`.pcap`) and summarize findings.

---

## 🛠 Tools Used
- **Wireshark** (packet capture and analysis)
- **Npcap** (Windows packet capture library)


---

## 🚀 Steps Performed

### Step 1 – Install Wireshark
- Downloaded and installed Wireshark (with Npcap on Windows).
  
### Step 2 – Start Packet Capture
- Selected the active network interface (Wi-Fi/Ethernet) in Wireshark.
- Started capturing packets.

### Step 3 – Generate Traffic
- Visited multiple websites in browser.
- Used the `ping` command to generate ICMP traffic.

### Step 4 – Stop & Save Capture
- Stopped capture after ~1 minute.
- Saved the file as `network_capture.pcap`.

### Step 5 – Filter by Protocol
- Applied filters in Wireshark:
  - `dns`
  - `tcp`
  - `http` / `tls`
  - `icmpv6`

### Step 6 – Identify Protocols
Observed the following:
1. **DNS** – Domain name resolution.
2. **TCP** – Reliable transport for most web and application traffic.
3. **UDP** – Connectionless transport, often used for DNS.
4. **TLSv1.2** – Security layer for HTTPS.
5. **ICMPv6** – IPv6 neighbor discovery and diagnostics.

---

## 📊 Findings

| Protocol   | Purpose | Example in Capture |
|------------|---------|--------------------|
| **DNS**    | Resolves domain names to IPs | AAAA query for `www.googleapis.com` |
| **TCP**    | Reliable transport | Connection to web server, ACKs, retransmits |
| **UDP**    | Quick, connectionless transport | Short packets, DNS queries |
| **TLSv1.2**| Encryption for HTTPS | Secure handshake and application data |
| **ICMPv6** | IPv6 network management | Neighbor solicitation/advertisement |

---

## 🔍 Observations
- Network traffic used IPv6 extensively.
- Multiple DNS queries to resolve sites visited.
- TCP duplicate ACKs indicated possible packet retransmissions.
- TLSv1.2 indicated encrypted HTTPS browsing.
- `ping` generated ICMPv6 packets showing local network discovery.

---

## 📁 Files in Repository
- **`README.md`** – This documentation.
- **`network_capture.pcap`** – The saved packet capture file.
- **`analysis_summary.txt`** – Detailed packet breakdown (optional).

---

## ⚠️ Important
- Capturing live network data may expose sensitive information. Only capture on networks you own or have permission to monitor.

---

## 📚 References
- [Wireshark Display Filter Reference](https://www.wireshark.org/docs/dfref/)



