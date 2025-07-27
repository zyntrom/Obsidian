# **TCP/IP Protocol Stack - Part 2: IP Layer & Datagram Structure**

---

## **1. Overview of IP Layer in TCP/IP**

- The **IP layer** resides in the **Network layer** of the TCP/IP stack.
- Main functions:
    - **Routing** of packets across networks.
    - **Fragmentation**: Breaking large packets into smaller ones.
- **Type**: Provides **connectionless** and **unreliable** delivery of packets (datagram service).
- IP is **stateless**: No tracking or relationship between packets.

---

## **2. Characteristics of IP Packets**

- Each packet (datagram) is **independent**.
- **No guarantees** on delivery, reliability, or order.
- Duplicate packets or out-of-order delivery is possible.
- Requires **source and destination IP addresses** in the header for routing and potential reply.

---

## **3. Encapsulation in IP Layer**

- When a data packet reaches the IP layer:
    - IP **adds a header** of **minimum 20 bytes**.
    - Header includes:
        - Source address
        - Destination address
        - Routing info
        - Other control fields
- This encapsulated packet is then passed to the **data link layer**.

---

## **4. Structure of an IP Datagram**

### **Header (Minimum 20 bytes)** + **Data**

- IP Header is **organized into 4-byte (32-bit) rows**.
- Can have up to **15 rows (60 bytes)** including options.
- Most common is **5 rows = 20 bytes** (no options).

---

## **5. Key Fields in IP Header**

|Field|Description|
|---|---|
|**Version (4 bits)**|IP version (e.g., IPv4 = `0100`)|
|**Header Length (4 bits)**|Length of the header in 32-bit words (e.g., 5 means 20 bytes)|
|**Service Type (8 bits)**|Type of service/priority (rarely used)|
|**Total Length (16 bits)**|Total size of IP packet (header + data), max = 65,535 bytes|
|**Identification (16 bits)**|Used for fragmentation and reassembly|
|**Flags (3 bits)**|Control fragmentation (e.g., don’t fragment)|
|**Fragment Offset (13 bits)**|Position of fragment in the original packet|
|**Time to Live – TTL (8 bits)**|Limits packet lifespan in the network; decremented at each hop|
|**Protocol (8 bits)**|Indicates higher layer protocol (e.g., TCP = 6, UDP = 17)|
|**Header Checksum (16 bits)**|Error checking for the header only|
|**Source IP (32 bits)**|IP address of sender|
|**Destination IP (32 bits)**|IP address of recipient|
|**Options (variable)**|Optional; used for advanced features like source routing|

---

## **6. Explanation of Important Fields**

### 🔹 **TTL (Time to Live)**

- Prevents infinite looping of packets.
- Initial TTL (e.g., 50 or 128) set by sender.
- Decremented at each hop; if TTL = 0 → packet discarded.

### 🔹 **Protocol Field**

- Tells IP which higher-layer protocol data belongs to.
- Examples:
    - TCP → `6`
    - UDP → `17`

### 🔹 **Header Checksum**

- **Used to detect transmission errors in the header.**
- Calculated using **one’s complement addition** of all 16-bit words in the header.
- Final result is **one’s complement** of the total sum.
- Recalculated at every hop.

---

## **7. Fragmentation-Related Fields**

- **Identification**, **Flags**, and **Fragment Offset** used to:
    - Break packets into smaller fragments (if size exceeds MTU).
    - Reassemble fragments at the destination.
- To be discussed in detail in fragmentation lecture.

---

## **8. Options Field**

- Used **only when required**, e.g., for **source routing**.
- Source routing allows sender to specify the exact path the packet should take.
- Optional and variable in size.

---

## **9. Packet Sniffing Tools**

- Software tools used to **capture and analyze** network packets.
- Can capture **IP packets** and **inspect header fields**.

### Examples:

- **Wireshark** (most popular)
- **tcpdump**
- **Ettercap**
- **Snort**

### Wireshark Features:

- Real-time packet capture.
- Displays protocol (TCP, UDP, HTTP, DNS, etc.), IP addresses, and header info.
- Allows filtering and deep inspection of headers (TTL, Protocol, Checksum, etc.).

---

## **10. Importance of Understanding IP**

- Core to understanding **network communication**.
- Critical for **network analysis**, **troubleshooting**, and **ethical hacking**.
- All hacking involves understanding **packet flow, protocol behavior**, and **vulnerabilities**.

---

## ✅ Summary

- IP provides best-effort, connectionless packet delivery.
- Each datagram is treated independently.
- IP header has crucial routing and control info.
- TTL prevents routing loops.
- Checksum ensures header integrity.
- Sniffer tools like Wireshark are vital for analyzing network behavior and learning how attacks may be performed.

---