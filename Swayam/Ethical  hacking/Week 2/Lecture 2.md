# 📘 IP Addressing and Routing – Part II: IP Address Classes and Notation

---

## 🌐 What is IP Addressing?

- **IP** is a protocol at the **Network Layer** in the **TCP/IP model**.
- It **uniquely identifies** every **host or computer** connected to the Internet.
- **Uniqueness** is essential for correct packet delivery — routers need to know **exactly** where to send a packet.
- An IP address is a **32-bit number**, allowing **2³² = ~4.3 billion** unique addresses.

---

## 🔢 Dotted Decimal Notation

|Concept|Explanation|
|---|---|
|Binary Form|IP is 32 bits, e.g., `01010101 10000010 00011011 10101100`|
|Dotted Decimal|To simplify, split into 4 **octets** (8 bits) and convert each to decimal|
|Example|`66.134.48.126` = easier to read and remember|

---

## 🧭 Hierarchical Structure of IP Addresses

|Part|Description|
|---|---|
|**Network ID**|Identifies the specific network (like a country/city)|
|**Host ID**|Identifies the specific device (like a house on the street)|
|Purpose|Routers use **network part** to forward packets. Once at the right network, local router uses **host part** to deliver it.|

- This is similar to real-world addressing: **Country → City → Street → House**

---

## 🏷️ IP Address Classes

|Class|Starting Bits|Network Bits|Host Bits|No. of Networks|Hosts per Network|Address Range|
|---|---|---|---|---|---|---|
|**A**|`0`|7 bits|24 bits|2⁷ - 2 = 126|2²⁴ - 2 ≈ 16 million|`0.0.0.0` to `127.255.255.255`|
|**B**|`10`|14 bits|16 bits|2¹⁴ - 2 ≈ 16,384|2¹⁶ - 2 ≈ 65,534|`128.0.0.0` to `191.255.255.255`|
|**C**|`110`|21 bits|8 bits|2²¹ ≈ 2 million|2⁸ - 2 = 254|`192.0.0.0` to `223.255.255.255`|
|**D**|`1110`|Multicast|—|—|—|`224.0.0.0` to `239.255.255.255`|
|**E**|`1111`|Reserved|—|—|—|`240.0.0.0` to `255.255.255.255`|

> `Note:` The first few bits help determine the class quickly.

---

## 🎯 Class Usage Summary

|Class|Use Case|
|---|---|
|**A**|Very large networks (e.g., ISPs)|
|**B**|Medium-sized organizations/universities|
|**C**|Small organizations/offices|
|**D**|Multicasting (sending to multiple hosts)|
|**E**|Experimental/Reserved (not used in practice)|

---

## 🏠 Private IP Address Ranges (Non-routable, Internal Use Only)

|Class|Private Range|Size|
|---|---|---|
|A|`10.0.0.0` to `10.255.255.255`|1 Class A block|
|B|`172.16.0.0` to `172.31.255.255`|16 Class B blocks|
|C|`192.168.0.0` to `192.168.255.255`|256 Class C blocks|

> Used for **intranet** communication; not routable over the Internet.

---

## ♻️ Special IP Addresses

|Address|Purpose|
|---|---|
|`127.0.0.1` or `127.x.x.x`|**Loopback Address** (Refers to self – used for testing)|
|`0.0.0.0`|**Default Network** / "This host on this network"|
|`255.255.255.255`|**Limited Broadcast** to all hosts in the local network|
|`<Network>.0.0.0`|Identifies the **network address**|
|`<Network>.255.255.255`|**Broadcast address** for that specific network|

---

## 🔄 Role of Routers in IP Addressing

- Routers use **only the Network ID** to decide where to forward a packet.
- Once the packet reaches the correct network, **host ID** is used to deliver the packet.
- This keeps routing tables smaller and routing more efficient.

---

## 🧠 Classful vs Classless Addressing (Brief Note)

- This lecture focuses on **Classful Addressing**, where:
    - IP addresses are divided into Classes A–E based on fixed boundaries.
- **Classless Inter-Domain Routing (CIDR)** came later to improve address space utilization (covered in advanced lectures).

---

## 🔐 Address Conventions (All-0s and All-1s)

- **Host ID all 0s**: Refers to the **network address** (used by routers)
- **Host ID all 1s**: Refers to the **broadcast address** (sends to all hosts in the network)
- These **cannot be assigned to hosts**

**Example (Class B):**

- Network: `118.0.0.0`
- Broadcast: `118.255.255.255`

---

## 📊 Distribution of IP Addresses

- **Class A**: Few networks, large number of hosts
- **Class B**: Moderate number of networks and hosts
- **Class C**: Many networks, few hosts each

This imbalance led to **waste of IP address space**, motivating the move to **CIDR and IPv6** later.

---

## ✅ Summary

- IP addresses are 32-bit hierarchical identifiers, split into **network** and **host** parts.
- IP classes (A–E) define how many bits are used for each.
- **Dotted decimal notation** is used to make IPs human-readable.
- **Private and special addresses** exist for internal or specific purposes.
- **Routers** use network IDs to forward packets efficiently.