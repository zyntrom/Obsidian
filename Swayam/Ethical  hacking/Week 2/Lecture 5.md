## 📘 **Lecture Summary: IP Subnetting, VLSM, and CIDR**

### 🔹 **1. Introduction to Subnetting**

- IP networks (Class A, B, C) are typically structured using a two-level hierarchy: **Network** and **Host**.
- **Subnetting** introduces a third level: **Network → Subnetwork → Host**.
- Purpose: Divide larger networks into smaller, manageable **subnetworks** for efficient routing and organization.

---

### 🔹 **2. Network Masks**

#### 🌐 **Natural Masks**

- Defined by the class of the IP address.
- Example masks:
    - Class A: `255.0.0.0`
    - Class B: `255.255.0.0`
    - Class C: `255.255.255.0`
- Used to separate the network portion from the host portion.
- **Bitwise AND** between IP and mask gives the **network address**.

#### 🛠️ **Subnet Masks**

- Allow partitioning the host portion into subnetwork + host.
- Flexible: Customize how many bits to use for subnetting vs host.
- Example:
    - Original: Class A `10.0.0.0` (natural mask: `255.0.0.0`)
    - Subnetted: `255.255.0.0` → uses second byte for subnet
    - Address: `10.5.0.20` → subnet = `5`, host = `0.20`

---

### 🔹 **3. Subnetting Example**

- Class A Network: `10.0.0.0`
- Using `255.255.0.0` mask:
    - Network: First 8 bits
    - Subnet: Next 8 bits
    - Host: Remaining 16 bits
- Allows:
    - 256 Subnets (`2^8`)
    - 65,534 Hosts per subnet (`2^16 - 2`)

---

### 🔹 **4. Variable Length Subnet Mask (VLSM)**

- Allows different subnet masks within the same network.
- Enables:
    - More efficient IP address utilization
    - Allocation of IP addresses based on department/need

#### 🧮 **Example:**

- Class C Network: `192.2.0.0`
- Departments:
    - D1: 110 hosts
    - D2: 45 hosts
    - D3: 50 hosts
- Use VLSM to:
    - Split the network for D1 using `/25` → 128 addresses
    - Further divide the remaining half for D2 and D3 using `/26` → 64 addresses each

---

### 🔹 **5. CIDR (Classless Inter-Domain Routing)**

- **No class-based restrictions** (Class A/B/C).
- Addresses written as: `IP_address/M`
    - `M`: Number of bits for the network
- Example: `144.16.192.57/18`
    - Network: First 18 bits
    - Host: Remaining 14 bits
- Advantages:
    - More efficient address allocation
    - Smaller routing tables in routers

#### 📏 **CIDR Rules**

1. **Block size = Power of 2**
2. **Starting address divisible by block size**
    - E.g., `/4` → 16 addresses → starting address must be divisible by 16

#### 🔍 **Example**

- CIDR: `144.16.192.40/29`
    - 3 host bits → 8 addresses
    - Address range: `144.16.192.40` to `144.16.192.47`

---

### 🔹 **6. Final Remarks**

- CIDR replaces traditional class-based addressing.
- VLSM enhances flexibility within networks.
- Modern routers are CIDR-compliant, making IP address management more efficient.