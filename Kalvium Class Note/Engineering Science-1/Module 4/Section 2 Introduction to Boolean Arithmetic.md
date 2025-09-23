# Boolean Arithmetic — Quick Notes (Kalvium AL 4.1)

## 1. Boolean Algebra

- Variables: **1 (true), 0 (false)**
- Uses:
    - Logic gate design (AND, OR, NOT, XOR)
    - Programming decisions (if, else, while)
    - Circuit simplification with Boolean laws

---

## 2. Importance

- **Foundation of digital circuits** (mathematical logic for CPUs).
- **Decision-making** in computers (logic & arithmetic).
- **Simplification** reduces size, speed, and power of circuits.
- **Everywhere**: phones, PCs, supercomputers.
- Basis for **programming logic** and **ALUs**.

---

## 3. Boolean Operations

- **AND (·)** → 1 if both inputs are 1.
- **OR (+)** → 1 if at least one input is 1.
- **NOT (¬)** → inverts input.
- **XOR (⊕)** → 1 if inputs differ.

_Example:_ Alarm = d · a (door open AND system armed).

---

## 4. Boolean Laws (Simplification)

- **Identity:** a + 0 = a, a · 1 = a
- **Null:** a + 1 = 1, a · 0 = 0
- **Inverse:** a + ¬a = 1, a · ¬a = 0
- **Distributive:** a · (b + c) = a·b + a·c
- **DeMorgan:**
    - ¬(a + b) = ¬a · ¬b
    - ¬(a · b) = ¬a + ¬b

---

## 5. Binary Arithmetic

- **Addition rules:**
    - 0+0=0, 1+0=1, 1+1=10 (carry 1).
    - Example: 1011 + 0110 = 10001
- **Subtraction rules:**
    - 0−0=0, 1−0=1, 0−1=1 (borrow 1).
    - Example: 1011 − 0110 = 0101

---

## 6. Complements

- **1’s comp:** Flip bits (1011 → 0100).
- **2’s comp:** 1’s comp + 1 (0100 + 1 = 0101).
- _Subtraction with 2’s comp:_  
    1011 + (2’s comp of 0110 → 1010) = 0101 (after carry discard).

---

## 7. Logic-Level Circuits

- **Half Adder:**
    
    - Sum = a ⊕ b
        
    - Carry = a · b
        
- **Full Adder:**
    
    - Sum = (a ⊕ b) ⊕ Cin
        
    - Carry = (a · b) + (Cin · (a ⊕ b))
        

---

## 8. Carry & Borrow

- **Carry:** occurs when addition > 1 (propagates).
    
- **Borrow:** occurs when subtracting 1 from 0.
    
- Both affect multi-bit operation speed.
    

---

## 9. Simplification Example

f = (a·b) + (a·¬b)  
= a·(b+¬b)  
= a·1 = **a**

---

## 10. Arithmetic Logic in Circuits

- Digital circuits = logic gates + adders/subtractors.
    
- **ALU** = performs addition, subtraction, comparison, bitwise ops.
    
- Found in **every CPU**.
    

---

## 🔑 Summary

- Boolean algebra → computers work with 0s & 1s.
    
- Binary addition/subtraction → via 1’s & 2’s complement.
    
- Logic gates implement arithmetic.
    
- Simplification saves cost, power, and time.
    
- ALU = core of arithmetic in processors.