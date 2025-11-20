🛰️ Network Traffic Capture & Analysis Using Wireshark 

---

## 🌐 **Overview**

This task demonstrates **real-world network forensic skills**, using Wireshark to capture live packets, analyze communication protocols, identify anomalies, and export traffic logs.

---

## 🎯 **Objective**

- Capture live network packets using Wireshark
- Analyze TCP, UDP, DNS, HTTP(S), ICMP, ARP, and other protocols
- Understand packet structures, handshake flows, DNS resolution, and encrypted traffic behavior
- Export traffic as a `.pcap` file and produce a forensic-grade analysis

---

## 🎨 **Why This Task Matters (Attractive Insight)**

✔ Builds **SOC Analyst** and **Network Forensics** skills  
✔ Helps understand **attack patterns**, reconnaissance, DNS abuse, and anomalies  
✔ Trains you to read **raw network behavior**, the foundation of cybersecurity  
✔ Strengthens fundamentals needed for **DFIR, Red Teaming, Blue Teaming & Threat Hunting**

---

## 🛠️ **Tools Used**

- **Wireshark** (Packet Capture & Protocol Analyzer)
- Any Web Browser (Generate HTTP/HTTPS traffic)
- Command Line (Ping, DNS lookup)

---

## ⚡ **Step-by-Step Practical Guide (Deep Technical Walkthrough)**

### **1️⃣ Install & Configure Wireshark**

- Download from Wireshark.org
- Install **Npcap** (required for capturing live traffic)
- Enable **promiscuous mode** (optional but useful)

---

### **2️⃣ Start a Live Capture**

- Open Wireshark → Select your network interface (Wi-Fi/Ethernet)
- Click **Start Capturing**
- Packets begin flowing instantly

> 🔍 Wireshark shows **real-time packets** including source, destination, protocol, length, and detailed packet breakdown.

---

### **3️⃣ Generate Traffic for Analysis**

Perform activities to create diverse packets:
- Visit websites (HTTP/HTTPS)
- Run: `ping google.com`
- Use apps like Instagram/YouTube
- DNS lookup: `nslookup openai.com`

This ensures **multi-protocol traffic** is captured.

---

### **4️⃣ Apply Advanced Wireshark Filters**
#### 🔹 **Common Filters**
```
tcp
udp
http
https
dns
icmp
arp
```

#### 🔹 **Advanced Filters**
```
tcp.flags.syn == 1
http.request
dns.qry.name contains "google"
ssl.handshake
icmp.type == 8
```
These filters help isolate specific packet types.

---

### **5️⃣ Deep Analysis of Captured Protocols**

Below is an **impressive technical breakdown** you can include in your report:

---
### 🧩 **🔹 TCP (Transmission Control Protocol)**

- Connection-oriented (3-way handshake)
- Ensures reliability (ACK, retransmissions)
- Used by HTTPS, HTTP, SSH, FTP

#### **Handshake Breakdown**

1. SYN → Client → Server
2. SYN‑ACK → Server → Client
3. ACK → Client → Server

Wireshark Filter:
```
tcp.flags.syn == 1
```

---
### 🧩 **🔹 UDP (User Datagram Protocol)**

- Fast & connectionless
- No handshake
- Used by DNS, VoIP, streaming

Wireshark Filter:
```
udp
```

---
### 🧩 **🔹 DNS (Domain Name System)**

Converts domain names into IP addresses.

Example query:
```
A www.google.com
```

Wireshark Filter:
```
dns
```

---
### 🧩 **🔹 HTTP / HTTPS**
#### **HTTP (Readable)**
Shows:
- GET/POST requests
- Host headers
- Cookies

Filter:
```
http
```

#### **HTTPS (Encrypted)**
You will only see:
- TLS handshake
- Certificates

Filter:
```
ssl
```

---
### 🧩 **🔹 ICMP (Ping)**

Used for connectivity testing.

Filter:
```
icmp
```

---
### 🧩 **🔹 ARP (Address Resolution Protocol)**

Maps IP → MAC addresses.

Filter:
```
arp
```

---

## 📊 **Sample Professional Summary for GitHub**

| Protocol | Purpose | Key Observation | Filter |
|---------|----------|----------------|--------|
| TCP | Reliable communication | 3‑way handshake visible | `tcp` |
| DNS | Domain to IP mapping | Multiple queries created by browsing | `dns` |
| HTTPS | Secure web traffic | TLS negotiation packets | `ssl` |
| ICMP | Connectivity testing | Echo request & reply | `icmp` |
| ARP | LAN mapping | Broadcast & MAC discovery | `arp` |

---

## 📤 **Exporting the Capture**
Go to:  
**File → Save As → `.pcap`**

Include this file in your GitHub repo.

---

## 🧠 **Interview Questions (Advanced & Impressive Answers)**

### **1. What is Wireshark used for?**  
Wireshark is a network forensic tool for capturing, analyzing, visualizing, and troubleshooting network packets.

### **2. What is a packet?**  
A structured unit of data transmitted over a network.

### **3. How do you filter packets in Wireshark?**  
Using display filters like: `tcp`, `dns`, `ssl.handshake`, etc.

### **4. Difference between TCP & UDP?**  
TCP = Reliable, connection-oriented.  
UDP = Fast, connectionless, no delivery guarantee.

### **5. What is a DNS query packet?**  
A request made to resolve a domain name into an IP address.

### **6. How does packet capturing help troubleshooting?**  
It reveals delays, reconnections, handshake failures, DNS misconfigurations, and malware traffic.

### **7. What is a protocol?**  
A set of rules governing network communication.

### **8. Can Wireshark decrypt encrypted traffic?**  
Only with access to private/session keys. Otherwise HTTPS stays encrypted.

---

## 📂 **Highly Attractive Project Structure**
```
📁 wireshark-network-analysis
 ├── captures/
 │    └── traffic.pcap
 ├── screenshots/
 │    ├── tcp-handshake.png
 │    ├── dns-query.png
 │    └── tls-handshake.png
 ├── report/
 │    └── detailed-analysis.md
 └── README.md
```

---

## 🌟 **Outcome**
By completing this task, I achieve: 
- A strong understanding of live packet capturing
- Practical knowledge of core protocols: TCP, UDP, DNS, HTTPS, ARP, ICMP
- Ability to analyze packet structures, handshakes, and encrypted sessions
- Skills to identify anomalies, latency issues, DNS failures, or suspicious traffic
- Experience exporting `.pcap` files and documenting network behavior
- Hands‑on capability required for roles like SOC Analyst, Network Analyst, DFIR & Threat Hunter
