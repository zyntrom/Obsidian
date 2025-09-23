# Half Adders and Full Adders — Notes

## What are Adders?

- Circuits that perform **binary addition**.
- Two main types:
    - **Half Adder (HA):** Adds 2 single-bit inputs. No carry-in.
    - **Full Adder (FA):** Adds 3 inputs (2 bits + carry-in).

---
```embed
title: "Mastering the Half Adder Circuit: Binary Addition with AND & XOR Gates | Digital Electronics Ep 18"
image: "https://i.ytimg.com/vi/thkTzdnkL5U/maxresdefault.jpg"
description: "🔢 Mastering the Half Adder Circuit: Simple Binary Addition with AND & XOR GatesWelcome back to our Digital Electronics Series! 🚀 In this eighteenth episode..."
url: "https://youtu.be/thkTzdnkL5U"
favicon: ""
aspectRatio: "56.25"
```

## Half Adder (HA)

- **Inputs:** A, B
- **Outputs:**
    - Sum = A ⊕ B (XOR gate)
    - Carry = A · B (AND gate)
- **Truth Table (HA):**

|A|B|Sum|Carry|
|---|---|---|---|
|0|0|0|0|
|0|1|1|0|
|1|0|1|0|
|1|1|0|1|

- **Use case:** Basic two-bit addition.

![[Pasted image 20250923105052.png]]

![[Pasted image 20250923105059.png]]
---

## Full Adder (FA)

- **Inputs:** A, B, Cin (carry-in)
- **Outputs:**
    - Sum = (A ⊕ B) ⊕ Cin
    - Carry = (A · B) + (Cin · (A ⊕ B))
- Uses: 2 XORs, 2 ANDs, 1 OR.
- **Truth Table (FA):**

| A   | B   | Cin | Sum | Cout |
| --- | --- | --- | --- | ---- |
| 0   | 0   | 0   | 0   | 0    |
| 0   | 0   | 1   | 1   | 0    |
| 0   | 1   | 0   | 1   | 0    |
| 0   | 1   | 1   | 0   | 1    |
| 1   | 0   | 0   | 1   | 0    |
| 1   | 0   | 1   | 0   | 1    |
| 1   | 1   | 0   | 0   | 1    |
| 1   | 1   | 1   | 1   | 1    |
![[Pasted image 20250923105114.png]]

![[Pasted image 20250923105120.png]]
---

## Cascading Adders (Multi-Bit Addition)

- Connect multiple **full adders in series**.
- Carry-out of one stage → carry-in of next.
- Example: 4-bit adder needs 4 FAs.

```embed
title: "Full Adders, Multi-Bit Adders, and Modular Design"
image: "https://i.ytimg.com/vi/J8zGg78c8ws/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGDUgUChyMA8=&rs=AOn4CLDhM1ReS_-B0lV-VhjqSes1VUT9hw"
description: "Description of how we construct a circuit called a Full Adder and then how we use modular design to construct larger multi-bit adders"
url: "https://youtu.be/J8zGg78c8ws"
favicon: ""
aspectRatio: "56.25"
```

---

## Ripple-Carry Adder

- Simple method: carry ripples through adders one by one.
- **Limitation:** Slower for large numbers (carry propagation delay).
- Optimization: Use **Carry Lookahead Adders** for speed.

---

## Quick Summary

- **Half Adder:** XOR (sum), AND (carry).
- **Full Adder:** Handles carry-in, Sum = (A⊕B)⊕Cin, Carry = AB + Cin(A⊕B).
- **Truth tables** verify functionality.
- **Ripple-carry adders** are easy but slow; advanced designs overcome this.

![[Pasted image 20250923105145.png]]