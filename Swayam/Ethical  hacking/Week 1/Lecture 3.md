## ✅ Basics of Computer Networking – Part 2

### 📌 Recap from Previous Lecture:

- Discussed **packet switching** and **virtual circuit approach**.
- Virtual Circuit: A **predefined route** (virtual path) is established **before** packets are transmitted.

---

## 📦 Datagram Approach

### 🔹 Key Characteristics:

- **No route is established beforehand**.
- Each packet is transmitted as an **independent entity**.
- Analogy: Like posting letters without knowing their exact path — just the destination.
- **Each packet carries its own header**:
    - **Source address**
    - **Destination address**

### 🔹 Routing:

- Intermediate nodes maintain a **routing table** to dynamically decide the next hop for each packet.

### 🔹 Issues with Datagram Approach:

|Problem|Description|
|---|---|
|**Out-of-order delivery**|Packets may arrive in a different order due to differing paths and delays.|
|**Packet loss**|If an intermediate node crashes, all buffered packets are lost.|
|**Duplicate packets**|Retransmission due to missed acknowledgments may result in duplicates.|

### 🔹 Advantages:

- No initial connection setup → **No initial delay**.
- **Flexible routing**: Can adapt to link failure or congestion.
- **Efficient** for smaller data transfers.

---

## 🔁 Comparison: Datagram vs Virtual Circuit

|Feature|Datagram|Virtual Circuit|
|---|---|---|
|Connection Setup|Not required|Required before transmission|
|Initial Delay|No|Yes (due to setup)|
|Routing|Dynamic (per packet)|Fixed route|
|Packet Order|May vary|Preserved|
|Overhead|Less for small data|Better for large data transfers|
|Flexibility|High|Low (less tolerant to link failure)|

---

## 🕒 Types of Delays in Networks

1. **Propagation Delay**:
    - Time for signal to travel from source to destination.
    - Depends on the **type of medium** (fiber, copper, satellite, etc.).
2. **Transmission Delay**:
    - Depends on **bandwidth** and **size of the message**.
    - Example: 1000 bits over 1 Mbps = 1 ms.
3. **Processing Delay**:
    - Time taken by routers to process packets (store, consult routing table, forward).

---

## 📐 Layered Network Architecture

### 🔸 Motivation:

- Divide complex networking tasks into manageable layers.
- Allows **modularity**, **maintenance**, and **flexibility**.

### 🔹 OSI 7-Layer Model:

|Layer|Name|Function|
|---|---|---|
|7|**Application**|User interface, software applications (e.g., browser, email)|
|6|**Presentation**|Data format conversion, encryption, compression|
|5|**Session**|Manages sessions, login/logout management|
|4|**Transport**|End-to-end communication, reliability, error recovery|
|3|**Network**|Routing of packets, logical addressing (IP)|
|2|**Data Link**|Error detection/correction, framing, flow control|
|1|**Physical**|Transmission of raw bits over medium (cables, signals)|

### 🔹 Layer Roles:

- **Upper Layers (4–7)**: End-to-end (host-to-host communication).
- **Lower Layers (1–3)**: Node-to-node (point-to-point communication).
- Intermediate routers only implement **layers 1–3**.

### 🔹 Data Flow in OSI Model:

- From sender: Data flows from **Application → Physical**.
- Across network: Via intermediate nodes (only 3 lower layers).
- At receiver: Data flows from **Physical → Application**.

---

## 🔌 Internetworking Devices & Layers

|Device|Layer|Description|
|---|---|---|
|**Hub**|Physical (Layer 1)|Broadcasts signal to all connected devices. No smart routing.|
|**Bridge / Layer-2 Switch**|Data Link (Layer 2)|Forwards data using MAC addresses.|
|**Router / Layer-3 Switch**|Network (Layer 3)|Routes packets using IP addresses. Connects different networks.|

### 📊 Example Setup:

- **Router**: Connects to external world.
- **Layer-3 Switch**: Core switch inside the organization.
- **Layer-2 Switches**: Connect to departments or sub-networks.
- **Hubs**: Used to connect individual devices within a network segment.

---

## 🧠 Key Takeaways:

- **Datagram networks** are **flexible**, scalable, and used in modern internet (e.g., IP).
- **OSI Model** provides a **structured framework** for network design and troubleshooting.
- Understanding the **functions and differences of each layer** and network device is crucial.

---

### ⏭️ What’s Next?

- Upcoming lecture: **TCP/IP protocol stack** – the practical model used on the Internet.