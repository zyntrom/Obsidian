# Boolean Arithmetic – Notes

## 1. Introduction

- Boolean algebra = branch of algebra where variables take **binary values**: 1 (true) or 0 (false).
- Foundation of **digital circuits**, **computer arithmetic**, and **programming logic**.
- Enables **decision-making**, **circuit simplification**, and **control flow** in digital systems.

---

## 2. Boolean Operations

|Operation|Symbol|Output|Example|
|---|---|---|---|
|AND|·|1 if both inputs 1|1 · 0 = 0|
|OR|+|1 if at least one 1|1 + 0 = 1|
|NOT|¬ or ’|Inverts input|¬1 = 0|
|XOR|⊕|1 if inputs differ|1 ⊕ 0 = 1|

- Example: Activate alarm if door open (d=1) **AND** system armed (a=1): alarm = d · a

---

## 3. Boolean Laws (Simplification)

- **Identity:** a + 0 = a, a · 1 = a
- **Null:** a + 1 = 1, a · 0 = 0
- **Inverse:** a + ¬a = 1, a · ¬a = 0
- **Distributive:** a · (b + c) = a·b + a·c
- **DeMorgan's Laws:** ¬(a + b) = ¬a · ¬b, ¬(a · b) = ¬a + ¬b

---

## 4. Binary Arithmetic

### Addition Rules

```
0 + 0 = 0  
1 + 0 = 1  
1 + 1 = 10 (0 carry 1)
```

**Example:**  
```
1011 + 0110 = 10001
```

### Subtraction Rules

```
0 − 0 = 0  
1 − 0 = 1  
0 − 1 = 1 (borrow 1)
```

**Example:**  
1011 − 0110 = 0101

### 1’s and 2’s Complement

- 1’s complement: flip all bits (1011 → 0100)
    
- 2’s complement: add 1 to 1’s complement (0100 + 1 = 0101)
    
- Subtraction: use 2’s complement of subtrahend, then add.
    

---

## 5. Logic-Level Implementation

### Adders

- **Half Adder:**
    
    - Sum = a ⊕ b
        
    - Carry = a · b
        
- **Full Adder:**
    
    - Sum = (a ⊕ b) ⊕ carry-in
        
    - Carry-out = (a · b) + (carry-in · (a ⊕ b))
        

### Carry & Borrow

- **Carry** → propagates when addition > 1
    
- **Borrow** → occurs when subtracting 1 from 0
    
- Important for **multi-bit arithmetic performance**
    

---

## 6. Simplifying Expressions

- Use **Boolean identities** to reduce circuit complexity.
    

**Example:** f = (a · b) + (a · ¬b)  
f = a · (b + ¬b) = a · 1 = a

---

## 7. Arithmetic Logic Units (ALUs)

- Combine adders, subtractors, and logic gates.
    
- Found in **CPU**, perform addition, subtraction, comparisons, bitwise operations.
    

---

## 8. Summary

- Boolean algebra = language of digital logic (0s & 1s).
    
- Binary arithmetic enables addition & subtraction in circuits.
    
- Logic gates implement these operations physically.
    
- Simplification = smaller, faster, efficient circuits.
    
- ALU = hardware implementation of arithmetic & logic operations.