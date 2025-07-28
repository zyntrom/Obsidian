## 📘 Chapter 2 (Continued): Binary Arithmetic and Overflow

---

### 🔢 Binary Addition

#### ➤ Rules for Binary Addition (like decimal, but with 0 and 1):

|A|B|Carry-in|Sum|Carry-out|
|---|---|---|---|---|
|0|0|0|0|0|
|0|1|0|1|0|
|1|0|0|1|0|
|1|1|0|0|1|
|1|1|1|1|1|

- Binary addition is **associative and commutative**, just like decimal.

---

### ➕ Signed Binary Arithmetic

#### ➤ Using 2's Complement

- Easy arithmetic because both positive and negative numbers are in one system.
- No special handling needed while adding:
    - Add both numbers directly.
    - Discard carry beyond MSB (if it exists).

##### Example:

```c
  +5  = 00000101   
  -2  = 11111110  
  (2's complement of 2: invert 00000010 → 11111101, add 1)   
  Sum = 00000011 = +3
```

---

### ⚠️ Overflow Detection in Binary Arithmetic

#### ➤ Unsigned Overflow

- If a carry-out from the **MSB** occurs → **overflow**.
- Example (8-bit):
```
11111111 (255) + 00000001 = 00000000 → overflow
```

#### ➤ Signed Overflow (2's Complement)

- Happens **only when adding two numbers of same sign** gives a result of opposite sign.

##### Overflow occurs if:

- Positive + Positive = Negative
- Negative + Negative = Positive

##### Example:

```
  +100 = 01100100   
  +40  = 00101000   
  ----------------   
  Sum  = 10001100 → -116 in 2's complement → Wrong → Overflow
```

##### Detection Rule:

- **Check the sign of the operands and result**.
    - If signs of operands are same, and sign of result is different → **overflow**.

---

### ➖ Binary Subtraction

- Use **2's complement method**:
    - `A - B` = `A + (2's complement of B)`

##### Example:

```c
  A = 00000101  (+5)   
  B = 00000010  (+2)    
  2’s complement of B = 11111110   
  Sum = 00000101 + 11111110 = 00000011 → +3

```
---

### ✅ Advantages of 2's Complement Arithmetic

- **Only one representation for 0**
- **Same circuitry** for addition and subtraction
- **Simpler overflow detection logic**
- Arithmetic is **consistent and fast**

---

### 🧠 Summary

- Binary arithmetic follows strict rules and needs overflow detection.
- Unsigned overflow = carry out of MSB.
- Signed overflow = sign anomaly.
- 2’s complement simplifies binary arithmetic and hardware design.