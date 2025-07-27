## 🧠 **Lecture Summary: TCP and UDP (Part 1)**

### 🔹 **Overview**

- Focuses on the **Transport Layer** of the TCP/IP model.
- Explains the two main protocols used at this layer:
    - **TCP (Transmission Control Protocol)**
    - **UDP (User Datagram Protocol)**
- Discusses how **port numbers** help in identifying user processes.

---

## 🔄 **Role of the Transport Layer**

- The **Transport Layer** ensures communication between **processes** on different hosts.
- Applications interact with TCP or UDP.
- **TCP/UDP → IP → Data Link Layer → Physical Layer** (for actual data transmission).

---

## 🔹 **TCP: Transmission Control Protocol**

### ✅ **Key Features**

1. **Connection-Oriented**: Requires connection setup before data transfer (like a phone call).
2. **Reliable**: Ensures delivery, order, and correctness of data.
3. **Full Duplex**: Supports two-way communication.
4. **Byte-Stream Oriented**: Manages data as a continuous stream of bytes.
5. **Sequencing**: Assembles data in the correct order at the receiver.
6. **Error Detection & Recovery**:
    - **Checksum** for detecting corruption.
    - **Acknowledgements (ACKs)** for confirming receipt.
    - **Timeouts & Retransmissions** if ACKs are missing.
7. **Flow Control**: Matches the rate of sender and receiver to avoid overload.
8. **Connection Establishment and Termination**:
    - Uses a **handshake** process to establish/terminate connections.

---

## 🔹 **UDP: User Datagram Protocol**

### ⚠️ **Key Features**

1. **Connectionless**: No setup required; sends independent packets.
2. **Unreliable**: No guarantees on delivery, ordering, or duplication.
3. **Lightweight**: Minimal overhead.
4. **Checksum Support**: Basic error detection.
5. **Faster but less secure** than TCP.

---

## 🔹 **Port Numbers**

### 🛠️ **Purpose**

- Identify individual processes (not just machines).
- Each packet includes:
    - **Source Port** (where it's from)
    - **Destination Port** (where it’s going)

### 📊 **Details**

- Port numbers are **16-bit integers** (0 to 65535).
- Common standards:
    - **0–1023** (or up to 4095): **Well-known ports**
        - SMTP: 25
        - FTP: 21
        - HTTP: 80
        - Telnet: 23
    - **Above 4095**: Ephemeral or temporary ports (used by clients)
- Defined in the **`services`** file:
    - Unix/Linux: `/etc/services`
    - Windows: Found under `C:\Windows\System32\drivers\etc\services`

### 🔁 **Client-Server Example**

- **Client** uses:
    - Random **ephemeral port**
    - Destination: Server’s **well-known port**
- **Server** replies:
    - Source: Server’s port
    - Destination: Client’s ephemeral port

---

## 🔹 **Establishing a TCP Connection**

### ✋ **Needs:**

1. **Protocol** (TCP)
2. **IP addresses** of both sender and receiver
3. **Port numbers** of both processes

This combination is known as a **5-tuple** or **association**:

```
<Protocol, Local IP, Local Port, Remote IP, Remote Port>
```

---

## 📌 **Important Terms**

|Term|Description|
|---|---|
|TCP|Reliable, connection-oriented protocol.|
|UDP|Fast, connectionless, unreliable protocol.|
|Port Number|Unique 16-bit identifier for user processes.|
|Ephemeral Port|Temporary port number used by clients.|
|Well-known Port|Predefined port number used by popular services (e.g., HTTP – 80).|
|Services File|Stores service names and corresponding port numbers on a system.|
|Byte-Stream|Data handled as a stream of bytes with sequencing and reliability.|
|Flow Control|Mechanism to adjust speed between sender and receiver.|

---

## ⏭️ **Next Lecture Teaser**

- TCP and UDP **header formats**
- TCP **connection setup (three-way handshake)** and **termination**
- Deeper look into reliability and congestion control