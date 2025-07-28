## 📘 Chapter 2: Binary Systems and Representations

---

### 🧮 Boolean Algebra (Recap)

- **Boolean variables**: Only two values — `0` (false) and `1` (true).
- **Basic operations**:
    - **AND (·)**: True if _both_ inputs are 1.
    - **OR (+)**: True if _at least one_ input is 1.
    - **NOT (‾)**: Inverts the value — `NOT 1 = 0`, `NOT 0 = 1`.

---

### 🔢 Binary Number Representation

#### ➤ Positive Numbers

- Represented using **standard binary notation**.
- Example: `5` in binary → `101`.

#### ➤ Negative Numbers

##### 1. **Sign-Magnitude Representation**

- MSB (Most Significant Bit) = sign bit (0 for positive, 1 for negative).
- Example (with 8-bit word size):
    - `+5`: `00000101`
    - `-5`: `10000101`
- **Disadvantage**: Two representations for 0 (`+0` and `-0`).

##### 2. **1's Complement**

- Negative numbers are the **bitwise NOT** of their positive version.
- Example:
    - `+5`: `00000101`
    - `-5`: `11111010`
- Still has **two representations for 0**: `00000000` and `11111111`.

##### 3. **2's Complement** (Most commonly used)

- Steps:
    1. Take binary of the positive number.
    2. Invert all bits (1's complement).
    3. Add 1 to the result.
- Example:
    - `+5`: `00000101`
    - `-5`:
        - Step 1: `00000101`
        - Step 2: `11111010`
        - Step 3: `11111011`
- Only **one representation for 0**.
- Simplifies arithmetic and logical operations.

---

### 🧬 Floating-Point Representation

#### ➤ Concept

- Required for representing **real numbers** (fractions, very large/small values).
- General format:  
    `Number = Mantissa × Base^Exponent`

#### ➤ IEEE 754 Standard

##### 1. **Single Precision (32-bit)**

- **1 bit**: Sign
- **8 bits**: Exponent
- **23 bits**: Mantissa (fractional part)

##### 2. **Double Precision (64-bit)**

- **1 bit**: Sign
- **11 bits**: Exponent
- **52 bits**: Mantissa

#### ➤ Example Representation

- Decimal number is normalized → binary → stored using the above format.

---

### 🔡 Character Encoding

#### ➤ ASCII (American Standard Code for Information Interchange)

- 7-bit encoding (values from 0 to 127).
- Common characters:
    - `A = 65`, `a = 97`, `0 = 48`

#### ➤ Unicode

- Covers **all global languages and symbols**.
- Uses:
    - UTF-8 (variable length, backward compatible with ASCII)
    - UTF-16, UTF-32 (for broader character sets)

---

### 🧠 Summary

- Boolean algebra is foundational for digital systems.
- Binary representation is the basis for data in computers.
- **2's complement** is preferred for representing signed integers.
- **Floating-point** allows efficient storage of real numbers.
- **IEEE 754** is the standard for floating-point.
- Characters are stored using encodings like **ASCII** and **Unicode**.