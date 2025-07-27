## **Lecture 2: Basic Concepts of Networking**

---

### **1. Introduction**

- Ethical hacking relies heavily on understanding **computer networks**.
- This lecture covers:
    - **Types of computer networks**
    - **Circuit switching vs. packet switching**
    - **Virtual circuits** (a packet-switching method)

---

### **2. What is a Computer Network?**

- A **computer network** is a **communication system** between computing devices (not necessarily only computers—IoT devices, smart gadgets, etc.).
    
- Purpose of networking:
    - Better **connectivity**
    - **Resource sharing** (e.g., cloud storage, cloud computing)
    - **Communication** (e.g., social media, smart security systems)

---

### **3. Types of Computer Networks**

#### a) **Local Area Network (LAN)**

- Covers a **small geographical area**:
    
    - Same room, building, or campus
        
- Based on **Ethernet** standards
    
    - Early speeds: 10 Mbps
        
    - Modern speeds: 1 Gbps, 10 Gbps, up to 100 Gbps
        
- **Advantages**:
    
    - Fastest communication type
        
    - Cheaper in the long run (owned infrastructure)
        

#### b) **Wide Area Network (WAN)**

- Connects **geographically distant** devices/networks:
    
    - Cities, countries, continents
        
- **Slower and more expensive** than LAN
    
    - Requires payment to **service providers**
        
    - Long-term **rental charges**
        

---

### **4. Data Communication Concepts**

#### a) **Routing Scenario Example**

- Data from **Node A** to **Node H**
    
- Passes through intermediate nodes like B, C, D, G
    
- Intermediate devices = **Routers**
    

---

### **5. Circuit Switching**

- Traditional method (used in old telephone systems)
    
- A **dedicated path** is established before transmission
    

#### Steps:

1. **Connection Establishment**
    
    - Reserves path with guaranteed bandwidth (e.g., 64 kbps)
        
2. **Data Transfer**
    
    - Dedicated link allows **uninterrupted** high-speed data flow
        
3. **Connection Termination**
    
    - Frees up the reserved resources
        

#### Characteristics:

- Dedicated **logical channels** on each link
    
- **Guaranteed bandwidth**
    
- **Inefficient** for **bursty computer data**
    
- Introduces **initial delay** due to connection setup
    
- **Good for voice communication**
    

---

### **6. Packet Switching**

- **Modern, efficient** method
    
- **No dedicated path**
    
- All **links are shared**
    

#### Key Concepts:

- Message is **broken into packets**
    
- Each packet includes a **header** (destination, routing info)
    
- Follows **store and forward** principle:
    
    - Intermediate routers **buffer** incoming packets before forwarding
        

#### Features:

- Efficient for **bursty data traffic**
    
- No **guaranteed bandwidth** (unless QoS is applied)
    
- **High link utilization**
    
- Supports **data rate conversion** via buffering
    
- Packets may take **different routes**
    
- Routers maintain **routing tables** to decide forwarding paths
    

---

### **7. Advantages of Packet Switching**

- High **utilization of network resources**
    
- Suitable for **bursty computer traffic**
    
- **No resource reservation**, more scalable
    
- Supports **priority-based packet handling**
    
- Can **adjust to network load**
    

---

### **8. Packet Switching Modes**

#### a) **Virtual Circuits**

- Hybrid of **circuit switching** and **packet switching**
    
- **Path is fixed** before data transfer
    
- All packets **follow same path**
    
- Assigned a **Virtual Circuit Number (VCN)** in header
    
- **No dynamic routing**
    
- Links are **not dedicated**—can be shared
    

##### Steps:

1. **Connection establishment**
    
    - Decide route (e.g., A → B → E → H)
        
2. **Packet forwarding**
    
    - Based on VCN using **routing tables**
        
3. **No real-time adaptation**
    
    - Fixed path even if congested
        

#### b) **Datagram Approach** _(To be discussed in next lecture)_

- Dynamic routing per packet
    
- More flexible than virtual circuits
    

---

### **9. Summary**

- **LAN vs. WAN**: LAN is fast, local, and cheaper. WAN is for long-distance but more expensive.
    
- **Circuit switching**: Uses fixed, dedicated paths—good for continuous voice communication.
    
- **Packet switching**: Breaks data into packets—efficient and flexible.
    
- **Virtual circuits**: Fixed path for packets but **shared links**—used rarely in the Internet.
    
- **Routing tables** help routers decide where to forward packets.
    

---

### **10. Coming Up Next**

- **Datagram-based transmission**
    
- More on **dynamic routing** and **network issues**