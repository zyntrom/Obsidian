# Introduction to Digital Logic and Number Systems

## 1. Learning Objectives

By the end of this lesson, you should be able to:

- Explain the **fundamental concepts of digital logic**.
- Convert between **binary, octal, decimal, and hexadecimal** number systems.
- Perform **basic binary arithmetic** (addition, subtraction, multiplication, division).
- Understand **1’s and 2’s complement methods** and overflow/underflow.
- Articulate the **importance of digital logic** in electronics.
- Recognize the **role of number systems** in representing and processing data.

---

## 2. What is Digital Logic?

- **Digital logic** is like a **light switch**: either **on (1)** or **off (0)**.
- Unlike **analog systems** (continuous values), digital logic works with **discrete states**.
- These states represent:
    - **True / False**
    - **Yes / No**
    - **On / Off**

**Foundation of all digital devices:**

- Computers, smartphones, calculators, processors, and memory.
- Example: Pressing "5" on a calculator → internally converted into **binary**, then used in calculations.

---

## 3. Number Systems Demystified

### Binary (Base-2)

- Uses **digits: 0, 1**.
- Each digit = **bit** (binary digit).
- Example of counting:
    - 0 → 0
    - 1 → 1
    - 2 → 10
    - 3 → 11
    - 4 → 100
- Analogy: Like light switches (on/off).

### Octal (Base-8)

- Digits: **0–7**.
- Shortcut for binary: each octal digit = **3 binary bits**.

### Decimal (Base-10)

- Digits: **0–9**.
- Our everyday system.

### Hexadecimal (Base-16)

- Digits: **0–9, A–F** (A=10 … F=15).
- Shortcut for binary: each hex digit = **4 binary bits**.

---

## 4. Number System Conversions

### Binary → Decimal

Formula: multiply each bit × (2^position), then sum.  
Example: 1011₂ = 1×2³ + 0×2² + 1×2¹ + 1×2⁰ = 11₁₀
```embed
title: "The binary number system"
image: "https://i.ytimg.com/vi/sXxwr66Y79Y/maxresdefault.jpg"
description: "Learn about the binary number system, a system where each digit represents a power of 2. Computers store everything in binary, using one bit for each digit."
url: "https://youtu.be/sXxwr66Y79Y"
favicon: ""
aspectRatio: "56.25"
```

### Decimal → Binary

Method: divide repeatedly by 2, record remainders (read bottom → top).  
Example: 13₁₀ = 1101₂

### Binary ↔ Octal

- Group binary into **3 bits**.
- Example: 101101₂ = 55₈

### Binary ↔ Hexadecimal

- Group binary into **4 bits**.
- Example: 10111110₂ = BE₁₆
### Octal ↔ Binary

- Each octal digit → **3-bit binary**.
- Example: 47₈ = 100111₂

### Hexadecimal ↔ Binary

- Each hex digit → **4-bit binary**.
- Example: 2A₁₆ = 00101010₂

---

## 5. Gray Code Conversion

- Special binary system → **successive values differ by only 1 bit**.
- Conversion:
    1. First (MSB) is same as binary.
    2. Each next bit = binary bit XOR previous binary bit.

Example: Binary 10110 → Gray = 11101
```embed
title: "Binary to gray code conversion  | very very easy"
image: "https://i.ytimg.com/vi/ipLNA_JVrUE/maxresdefault.jpg"
description: "binary to gray code conversion || made easyvisit our website for more (easy explanation) www.raulstutorial.comHow to add two binary numbers?https://youtu.be/..."
url: "https://youtu.be/ipLNA_JVrUE"
favicon: ""
aspectRatio: "56.25"
```

---

## 6. Binary Arithmetic

### Addition Rules

- 0 + 0 = 0
- 0 + 1 = 1
- 1 + 0 = 1
- 1 + 1 = 10 (0 carry 1)

### Subtraction (Borrow Method)

Similar to decimal, but only with 0 and 1.
```embed
title: "Lec-17: Binary Addition➕ and Subtraction➖ | Number System"
image: "https://i.ytimg.com/vi/4cjs2GrOf6Y/maxresdefault.jpg"
description: "👉Subscribe to our new channel:https://www.youtube.com/@varunainashots►Digital Logic(Complete Playlist):https://www.youtube.com/playlist?list=PLxCzCOWd7aiGmX..."
url: "https://youtu.be/4cjs2GrOf6Y"
favicon: ""
aspectRatio: "56.25"
```

### Multiplication Rules

- 0 × 0 = 0
- 0 × 1 = 0
- 1 × 0 = 0
- 1 × 1 = 1
```embed
title: "Lec-14: Binary Multiplication with example"
image: "https://i.ytimg.com/vi/mVcoDEXzcOg/maxresdefault.jpg"
description: "👉Subscribe to our new channel:https://www.youtube.com/@varunainashotsThis video is Binary Multiplication with example. ►Number System (Complete Playlist):ht..."
url: "https://youtu.be/mVcoDEXzcOg"
favicon: ""
aspectRatio: "56.25"
```

### Division

- Same as decimal long division, but simpler (divisor = 0 or 1).
```embed
title: "Binary Division"
image: "https://i.ytimg.com/vi/VKemv9u40gc/maxresdefault.jpg"
description: "Digital Electronics: Binary DivisionTopics discussed:1) Division of binary numbers.2) Examples of dividing two binary numbers.Follow Neso Academy on Instagra..."
url: "https://youtu.be/VKemv9u40gc"
favicon: ""
aspectRatio: "56.25"
```

---

## 7. Complements in Binary

### 1’s Complement

- Invert bits (0 → 1, 1 → 0).
- Example: 1010 → 0101.

### 2’s Complement

- Take 1’s complement + 1.
- Example: 1010 → 0101 + 1 = 0110.

**Use in Subtraction:**

- Subtract A – B by adding A + (2’s complement of B).
- Example: 1011 – 0110 → Add (1011 + 1010) = 10101 → Discard carry → 0101 (5).

### Overflow & Underflow

- **Overflow:** result too large for fixed bits.
- **Underflow:** result too small/negative to represent.
```embed
title: "Lec-11: Find 1's Complement & 2's Complement in 5 seconds | Best Trick"
image: "https://i.ytimg.com/vi/pXIfEklKsOQ/maxresdefault.jpg"
description: "👉Subscribe to our new channel:https://www.youtube.com/@varunainashotsFind 1's Complement & 2's Complement in less than 5 seconds for any binary number. In t..."
url: "https://youtu.be/pXIfEklKsOQ"
favicon: ""
aspectRatio: "56.25"
```

---

## 8. Why Digital Logic Matters

- **Accuracy:** less prone to noise than analog.
- **Speed:** calculations are faster.
- **Reliability:** consistent, fewer errors.

**Real-world applications:**

- Processors, memory, calculators, communication systems, networks.

---

## 9. Summary

- Digital logic = foundation of computing (0 and 1).
- Number systems: Binary, Octal, Decimal, Hexadecimal.
- Conversions are like translating languages.
- Arithmetic: addition, subtraction, multiplication, division.
- Complements (1’s and 2’s) simplify subtraction.
- Gray code prevents multi-bit errors.
- Digital systems are fast, reliable, and accurate.
![[Pasted image 20250826094831.png]]