### 🔹 **Overview**

- The lecture focuses on **TCP and UDP header structures**, **TCP connection establishment/termination**, and their implications in **network attacks** (e.g., DoS).

---

### 🔸 **TCP (Transmission Control Protocol)**

#### ✅ **Key Features of TCP**

- **Connection-oriented**
- **Reliable byte-stream delivery**
- **Full-duplex communication**
- **Multiplexing/demultiplexing**
- **Error control and retransmission**
- Uses **buffers** at both sender and receiver

#### 📦 **TCP Header Format (Minimum 20 bytes, Max 60 bytes)**

|Field|Description|
|---|---|
|Source Port|16-bit port number of sender|
|Destination Port|16-bit port number of receiver|
|Sequence Number|32-bit byte number for tracking sent data|
|Acknowledgment Number|32-bit number indicating next expected byte|
|Header Length|Specifies header size in 32-bit words|
|Flags|URG, SYN, ACK, FIN, RST, PSH (6 control flags)|
|Window Size|Flow control (how many bytes can be sent without ACK)|
|Checksum|Error detection for header + data + pseudo header|
|Urgent Pointer|Used when URG flag is set|
|Options|Optional TCP features|

#### 🚩 **TCP Flags (Control Bits)**

- **URG** – Urgent data
- **SYN** – Connection initiation
- **ACK** – Acknowledgment field is valid
- **FIN** – Finish, i.e., no more data
- **RST** – Reset connection
- **PSH** – Push function (send data immediately)

#### 🔁 **TCP Connection Establishment (3-Way Handshake)**

1. **Client → Server:** SYN with seq = X
2. **Server → Client:** SYN-ACK with seq = Y, ack = X+1
3. **Client → Server:** ACK with ack = Y+1  
    ✅ _Connection is now established_

#### 🧨 **Half-Open Connections**

- If ACK from client is missing, server holds incomplete (half-open) state
- Can lead to **Denial of Service (DoS)** if many such requests overwhelm server's connection table

#### 🔚 **TCP Connection Termination (4-Step Process)**

1. **FIN from client**
2. **ACK from server**
3. **FIN from server**
4. **ACK from client**  
    ✅ _Connection now closed_

---

### 🔸 **UDP (User Datagram Protocol)**

#### ✅ **Key Features**

- **Connectionless**
- **Unreliable**
- **Fast and minimal overhead** (no handshakes)
- Suitable for **real-time or simple request/response apps** (e.g., DNS, VoIP)

#### 📦 **UDP Header Format (8 bytes total)**

|Field|Description|
|---|---|
|Source Port|16 bits|
|Destination Port|16 bits|
|Length|16 bits (includes header + data)|
|Checksum|16 bits (includes pseudo header from IP)|

---

### 🛡️ **Security Insight**

- **TCP SYN flood attacks** exploit the 3-way handshake by sending many SYNs and not completing the connection, causing **server overload**.

---

### 🔜 **Next Topic**

- Introduction to **IP subnets**: how to segment IP networks and manage them efficiently.