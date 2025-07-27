# **TCP/IP Protocol Stack – Part 1**

## 📌 Introduction to TCP/IP

- **TCP/IP (Transmission Control Protocol / Internet Protocol)** is the **fundamental protocol suite of the Internet**.
- It enables different systems (with different OS and hardware) to communicate, acting as a **common language**.
- Originated in the **1970s** as a **US military project**, later adopted by universities, and is now the **de facto internet standard**.

---

## 🌐 Internet as a Network of Networks

- **Internet = Interconnected collection of networks**
- Networks use different:
    
    - Operating systems (Windows, Linux, macOS)
        
    - Network technologies (Ethernet, ATM, WAN protocols)
        
- **TCP/IP bridges the gap** between heterogeneous platforms.
    

---

## 📶 Layering in TCP/IP vs OSI Model

|OSI Model (7 Layers)|TCP/IP Model (4 Layers)|
|---|---|
|Application|Application|
|Presentation||
|Session||
|Transport|Transport|
|Network|Internet (Network)|
|Data Link|Link (Data Link + Physical)|
|Physical||

- **OSI Model:** 7 layers (3 point-to-point + 4 host-to-host)
    
- **TCP/IP Model:** 4 layers (simplified):
    
    1. **Application**
        
    2. **Transport**
        
    3. **Network (Internet)**
        
    4. **Link (Data Link + Physical)**
        

---

## 🔁 Data Flow in the TCP/IP Stack

- **Sender A → Intermediate B → Receiver C**
    
- Data flows **down the layers on sender side**, across the network, and then **up the layers on receiver side**.
    

### Data Transmission Path:

css

CopyEdit

`A (App) → Transport → Network → Link → B (Router) → Network → Link → C → Network → Transport → App`

- **Transport & Application Layers**: Host-to-host (A ↔ C)
    
- **Intermediate Routers** (e.g., B): Only concerned with **Network and Link Layers**
    

---

## 📦 TCP/IP Protocol Suite = Family of Protocols

- Based on **Datagram (connectionless)** communication, **not virtual circuits**
    
- Messages are divided into packets (datagrams), which may take **different paths**.
    

### Important Members of the Protocol Suite:

#### 🔹 Network (Internet) Layer:

- **IP (Internet Protocol)**: Handles packet routing
    
- **ICMP**: Error messages (e.g., service unavailable)
    
- **IGMP**: Multicast group management
    
- **ARP**: IP → MAC address translation
    
- **RARP**: MAC → IP address translation
    

#### 🔹 Transport Layer:

- **TCP** (Transmission Control Protocol): Reliable, connection-oriented
    
- **UDP** (User Datagram Protocol): Unreliable, connectionless
    

#### 🔹 Application Layer:

- Protocol examples:
    
    - **FTP, TFTP** – File Transfer
        
    - **SMTP** – Email
        
    - **DNS** – Domain Name Resolution
        
    - **SNMP** – Network Management
        

---

## 🔁 Protocol Stack Usage Examples

### Option 1 – Using TCP:

arduino

CopyEdit

`User Process → TCP → IP → Ethernet`

### Option 2 – Using UDP:

arduino

CopyEdit

`User Process → UDP → IP → Ethernet`

- **TCP or UDP** can be chosen based on application need
    
- Both **use IP** underneath for packet delivery
    

---

## ⚙️ Functions of Each Protocol

### 📍IP (Internet Protocol)

- Routes **datagrams** from source to destination
    
- May **fragment** large packets
    
- **Unreliable**: Packets may be lost, duplicated, or out-of-order
    

### 📍TCP (Transmission Control Protocol)

- **Reliable and connection-oriented**
    
- Adds features like:
    
    - Acknowledgements
        
    - Retransmission on failure
        
    - Packet ordering
        
    - Message reassembly
        
- Hides IP unreliability from applications
    

### 📍UDP (User Datagram Protocol)

- **Unreliable, connectionless**
    
- No ordering, error correction, or retransmission
    
- Used when **speed > reliability**
    
    - Example: real-time status updates, VoIP, streaming
        

---

## 🧾 Addressing in TCP/IP

|Layer|Address Type|Length|Purpose|
|---|---|---|---|
|Link Layer|**MAC / Ethernet**|48 bits|Uniquely identifies NIC hardware|
|Network Layer|**IP Address**|32 bits|Identifies host on the network|
|Transport|**Port Number**|16 bits|Identifies application/process|

- Every packet contains:
    
    - **Source & Destination IPs**
        
    - **Source & Destination MACs**
        
    - **Source & Destination Ports**
        

---

## 📦 Data Encapsulation Example

### Scenario:

- A **TFTP client** sends **200 bytes** of data using **UDP**.
    

### Headers and Trailers Added:

|Protocol Layer|Header Size|Trailer Size|Notes|
|---|---|---|---|
|TFTP (App)|4 bytes|—|Simple file transfer protocol|
|UDP|8 bytes|—|Transport layer|
|IP|20 bytes|—|Adds routing info|
|Ethernet (Link)|14 bytes|4 bytes|Frame + CRC trailer|
|**Total**|**46 bytes header + 4 bytes trailer** = **50 bytes overhead**|||

### Final Packet Size =

**200 (Data) + 50 (Overhead) = 250 bytes transmitted**

> The added headers/trailers are essential for proper delivery but contribute to **protocol overhead**.

---

## 📌 Summary of Key Points

- TCP/IP is a simplified, robust, and widely adopted protocol suite.
    
- It has **4 layers**: Application, Transport, Network, Link.
    
- **IP** handles routing but is unreliable.
    
- **TCP** ensures reliability through acknowledgment and retransmission.
    
- **UDP** is fast but unreliable; used in speed-critical or non-critical apps.
    
- Data encapsulation adds headers at each layer for proper communication.
    
- Three types of addresses involved:
    
    - **MAC Address**: Hardware
        
    - **IP Address**: Logical/Network
        
    - **Port Number**: Application
        

---