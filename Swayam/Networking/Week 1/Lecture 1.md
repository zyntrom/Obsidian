# 🌐 Computer Networks – Lecture 1: Introduction

**Course**: Computer Networks  
**Platform**: SWAYAM  
**Lecture Focus**: Overview of computer networks, types, goals, evolution, models, topologies, devices, protocols, performance, and security.

---

## 📘 What is a Computer Network?

- A **computer network** is a system of interconnected devices that **exchange data** and **share resources**.
- Devices include: computers, servers, mobile devices, routers, switches, IoT systems.
- Enables:
    - Centralized data management
    - Collaboration
    - Remote access
- 📌 Example: Office LAN where employees access shared files, printers, and the internet from their desks.

---

## 🔑 Key Components of a Network

1. **Hosts (End Devices)**:
    - Laptops, desktops, smartphones—initiate or receive data.
2. **Networking Hardware**:
    - **Routers**: Forward data between networks.
    - **Switches**: Direct traffic within networks.
    - **Cables/Wireless Signals**: Transmission media.
3. **Protocols**:
    - Rules for communication.
    - Example: **TCP/IP** ensures proper formatting, addressing, delivery.

---

## 🕸️ Types of Networks

|Type|Description|Example|
|---|---|---|
|**LAN** (Local Area Network)|Small geographic area|Office, school lab|
|**WAN** (Wide Area Network)|Large areas across cities/countries|Internet|
|**MAN** (Metropolitan Area Network)|City-wide coverage|City Wi-Fi, surveillance|
|**PAN** (Personal Area Network)|Close-range connectivity|Phone ↔ Bluetooth earbuds|

---

## 🎯 Goals of Networking

1. **Resource Sharing**: Share printers, apps, storage.
2. **Communication**: Email, video conferencing, chat.
3. **Centralized Data Access**: Better backup, security, control.
4. **Remote Access**: Work or learn from anywhere.
5. **Scalability**: Add devices/bandwidth as needed.

---

## 🕰️ Evolution of Networking

|Era|Key Developments|
|---|---|
|**1960s**|ARPANET, packet switching|
|**1980s**|Ethernet becomes LAN standard|
|**1990s**|Internet and World Wide Web emerge|
|**2000s**|Wireless, broadband, cloud services|
|**Today**|5G, edge computing, AI-driven networks|

---

## 🖥️ Network Models

### 1. **Client-Server Model**

- **Centralized**: Clients (user devices) request data; server provides it.
- 📌 Example: Browser → request page → Web server sends it.
- **Pros**: Efficient, secure, centrally managed.
- **Cons**: Server failure can disrupt service → need redundancy/load balancing.

### 2. **Peer-to-Peer (P2P) Model**

- **Decentralized**: Devices act as both client and server.
- 📌 Examples: BitTorrent, Blockchain.
- **Pros**: Robust, cost-effective.
- **Cons**: Harder to manage and secure.

---

## 🌐 Network Topologies

|Topology|Description|Pros|Cons|
|---|---|---|---|
|**Star**|All devices connect to a central hub|Simple, isolated failures|Hub failure breaks network|
|**Ring**|Devices form a closed loop|Predictable performance|One failure affects entire loop|
|**Bus**|Shared backbone cable|Easy to implement|Not scalable, collisions|
|**Mesh**|Each node connects to many others|High redundancy|Expensive, complex|
|**Hybrid**|Mix of above|Custom design|Complexity depends on combination|

---

## 🧰 Basic Networking Devices

|Device|Function|
|---|---|
|**Router**|Connects networks, routes data (IP-based)|
|**Switch**|Connects devices in LAN (MAC-based forwarding)|
|**Hub** (obsolete)|Broadcasts data to all devices (causes collisions)|

---

## 🌐 Protocols and Standards

- **Protocols** = rules for data transmission.
    - **TCP**: Ensures reliable delivery.
    - **IP**: Handles addressing and routing.
    - **HTTP, FTP, SMTP**: Application-level protocols.
- **Standards bodies**: IEEE, IETF ensure interoperability across devices/vendors.

---

## 🧭 IP Addressing

- **Purpose**: Unique identifier for each device.
- **IPv4**: 32-bit, ~4.3 billion addresses.
- **IPv6**: 128-bit, practically unlimited.
- **Static vs Dynamic**: Manually assigned or via DHCP.
- **Public vs Private**:
    - Public: Internet-visible
    - Private: LAN-only

---

## 🪪 MAC Address & Data Link Layer

- **MAC Address**: Unique hardware ID (on NICs).
- **Layer**: Operates at OSI **Layer 2** (Data Link).
- **Use**: Switches forward frames based on MAC address.

---

## 📶 Bandwidth & Latency

|Metric|Meaning|Units|
|---|---|---|
|**Bandwidth**|Max data transfer rate|Mbps/Gbps|
|**Latency**|Delay in data transfer|ms|

- **High bandwidth**: Needed for streaming.
- **Low latency**: Critical for gaming, calls.

---

## 🚀 Modern Networking Trends

1. **Cloud Computing**: Centralized, on-demand infrastructure.
2. **Edge Computing**: Local processing near data source (e.g., IoT).
3. **5G**: Faster speeds, lower latency, more connections.
4. **AI in Networking**: Self-healing, analytics, threat detection.

---

## 🛡️ Network Security

- **Goals**: Confidentiality, integrity, availability.
- **Techniques**:
    - Firewalls
    - Encryption (HTTPS, VPNs)
    - Authentication (e.g., login credentials)
- **Threats**: Phishing, ransomware, DoS attacks.
- Security must be **multi-layered** and proactive.

---

## 🌍 The Role of the Internet

- A **network of networks** spanning the globe.
- Uses:
    - Browsing, communication, cloud apps, banking
- Data travels through:
    - Routers, switches, undersea cables
- Runs on **TCP/IP** and **DNS** protocols.

---

## 📡 Wireless Networking

- Eliminates cables, increases flexibility.
- Technologies:
    - **Wi-Fi**: High-speed local access.
    - **Bluetooth**: Short-range personal device connection.
    - **Cellular (4G/5G)**: Long-range mobile broadband.

---

## 📊 Network Performance Metrics

|Metric|Description|
|---|---|
|**Throughput**|Actual data delivery rate|
|**Jitter**|Variation in packet arrival time|
|**Packet Loss**|Packets that don’t reach destination|

- Monitoring helps optimize performance, reduce lag, and plan upgrades.

---

## 🔁 Summary & Recap

- Introduced **networking basics**, including:
    - What networks are and why they matter
    - Types, goals, and components
    - Models (Client-Server & P2P), topologies, devices
    - Protocols, IP/MAC, bandwidth, and latency
    - Trends, security, performance, and the internet