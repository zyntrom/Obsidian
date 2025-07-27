# 📘 IP Addressing and Routing – Part I: Fragmentation and Reassembly

---

## 📌 Introduction

- IP layer (part of **TCP/IP**) is responsible for:
    - **Routing packets**
    - **Addressing packets**
- Works at the **Network Layer** of the OSI model
- Packet fragmentation is necessary when a packet exceeds the allowed size for a network

---

## 📦 Why Fragmentation?

- Networks have a limit on packet size, called **MTU (Maximum Transfer Unit)**
- A large IP packet may need to be **fragmented** to pass through a network with smaller MTU
- IP provides a **connectionless datagram service**:
    - Packets can be **lost, duplicated, or arrive out of order**
    - No guarantee of reliable delivery

---

## 🔍 Maximum Transfer Unit (MTU)

- **Definition**: Maximum size of a packet that a network layer can handle
- Varies by network (due to hardware, buffer sizes, header formats)
- If an IP packet size > MTU, **fragmentation** occurs
- **Reassembly** is needed at some point to restore the original packet

---

## 🔁 Fragmentation and Reassembly

- Fragmentation: Breaking down a large packet into smaller ones
- Reassembly: Reconstructing the original packet from fragments
- Each fragment is treated as an **independent IP packet**
- Fragmentation is mostly performed by **routers**
- Two types:
    - **Transparent Fragmentation**
    - **Non-Transparent Fragmentation**

---

## 🔹 Transparent Fragmentation

### ✅ Characteristics:

- **Intermediate networks are unaware** of fragmentation
- Fragmentation and reassembly are done **within a single network**
- **Same exit router** must be used for all fragments
- Reassembled packet is sent to the next network

### ✅ Example:

- Packet enters Network N2
- Fragmented by entry router of N2
- Reassembled by exit router of N2
- Next network sees **only the full reassembled packet**

### ⚠ Drawbacks:

1. **All fragments must pass through the same exit router**, which can cause:
    - **Router overload**
    - **Reduced efficiency**
2. **Multiple reassembly stages** if passing through several such networks:
    - Increases processing overhead

### ✅ Methods to detect last fragment:

- Use a **count field** to specify number of remaining fragments
- Use a **special delimiter** to mark the last fragment

---

## 🔸 Non-Transparent Fragmentation (**Used by IP**)

### ✅ Characteristics:

- **No intermediate reassembly**
- Fragments flow independently to the **final destination**
- Reassembly is done **only at the destination host**
- Each fragment is treated as a **full IP packet**

### ✅ Advantages:

- **Multiple exit routers** can be used
- **Better resource utilization**
- **Higher throughput**

### ⚠ Drawbacks:

- **Header overhead**: Each fragment has its own **20-byte IP header**
- More bits transmitted overall

---

## 🧱 IP Header Fields for Fragmentation

|**Field**|**Size**|**Purpose**|
|---|---|---|
|`Identification`|16 bits|Same for all fragments of a packet; helps group them|
|`Fragment Offset`|13 bits|Indicates the position of this fragment in the original packet (in multiples of 8 bytes)|
|`Flags`|3 bits|Used to control fragmentation|

### 🚩 Flags in Detail:

- **D (Don't Fragment)**:
    - 1 → Do not fragment
    - 0 → Fragmentation allowed
- **M (More Fragments)**:
    - 1 → More fragments follow
    - 0 → This is the last fragment

---

## 📊 Fragmentation Example

### Given:

- 1000 bytes of data to send
- IP header size = 20 bytes
- Total packet size = 1020 bytes

#### Case 1: MTU = 620 bytes

→ Maximum data per fragment = 600 bytes (620 - 20)
- **Fragment 1**:
    - Data: 600 bytes
    - Offset: 0
    - M = 1
- **Fragment 2**:
    - Data: 400 bytes
    - Offset: 75 (600 / 8)
    - M = 0

#### Case 2: MTU = 400 bytes

→ Must further fragment 600 and 400 byte fragments  
→ Use offsets in multiples of 8 bytes

- Example:
    - Fragment 1: Offset 0, M = 1
    - Fragment 2: Offset 47 (376 bytes), M = 1
    - Fragment 3: Offset 75, M = 1
    - Fragment 4: Offset 122, M = 0

**Resulting total data transmitted > original size due to multiple headers**

---

## 📶 Ethernet and MTU

- **Ethernet MTU = 1500 bytes**
- IP max packet size = 64 KB (approx 65535 bytes)
- If IP packet > 1500 bytes:
    - Ethernet fragmentation needed
    - To avoid, IP layer often limits its own MTU to 1500 bytes

---

## ✅ Summary

- **IP fragmentation** enables large packets to traverse networks with smaller MTUs
- **IP uses non-transparent fragmentation**
    - Fragments are not reassembled until they reach the destination
- **Important header fields** for fragmentation:
    - `Identification`
    - `Fragment Offset`
    - `Flags (D, M)`
- Fragmentation causes **overhead** due to repeated headers
- Understanding IP fragmentation is crucial for network performance tuning and protocol design