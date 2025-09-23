# Notes on Arithmetic Logic Unit (ALU)

## 1. Introduction to ALU

- **Definition**: Core component of CPU that performs **arithmetic (math)** and **logical (decision-making)** operations.
- **Role**: Brain of computation, ensures efficient processing.
- **Without ALU**: No addition, comparison, or data processing possible.

### Functions:

- Arithmetic: Addition, subtraction, multiplication, division.
- Logical: Comparisons (>, <, =) and Boolean operations (AND, OR, NOT, XOR).
- Data manipulation: Bitwise operations, shifting, masking.

---

## 2. Operations of ALU

### 2.1 Arithmetic Operations

- Work on binary numbers.
- Example: 5 + 3 → ALU converts to binary → outputs 8 (1000).

### 2.2 Logical Operations

- Based on Boolean logic (TRUE/FALSE or 1/0).
- Example: Check if `x > 10` → returns True/False.

### 2.3 Bitwise Operations

- Manipulate **individual bits**.
- **AND (&):** Keeps common 1s → `1010 & 1100 = 1000`.
- **OR (|):** Keeps any 1 → `1010 | 1100 = 1110`.
- **XOR (⊕):** 1 if bits differ → `1010 ⊕ 1100 = 0110`.
- **NOT (~):** Flips bits → `1010 → 0101`.
- **Shift (<<, >>):**
    - Left shift: multiply by 2 → `10 << 1 = 20`.
    - Right shift: divide by 2 → `10 >> 1 = 5`.

---

## 3. Difference: Bitwise vs Logical

|Aspect|Bitwise|Logical|
|---|---|---|
|Level|Works on **bits**|Works on **whole values**|
|Gates|AND, OR, XOR, NOT|Comparators|
|Output|New binary value|True (1) / False (0)|
|Use|Data manipulation (masking, encryption)|Decision-making (branching)|

---

## 4. Components of ALU

- **Arithmetic Unit**: Performs addition, subtraction, multiplication, division.
- **Logic Unit**: Executes AND, OR, XOR, NOT, comparisons.
- **Status Register (Flags)**:
    - Z (Zero) → result = 0
    - C (Carry) → overflow in addition
    - N (Negative) → result negative
    - V (Overflow) → result exceeds range
- **Multiplexer (MUX)**: Selects input/operation based on Control Unit.
- **Control Unit Interface**: Directs ALU on which operation to perform.

---

## 5. Working Mechanism

1. Control Unit sends instruction (e.g., ADD A, B).
2. MUX selects proper circuit (adder, subtractor, etc.).
3. ALU performs operation on input operands from registers.
4. Result stored in register or sent back to CPU.
5. Flags updated (e.g., Zero flag set if result = 0).

---

## 6. Role of ALU in Computing Systems

### Importance:

- Executes arithmetic & logical operations.
- Controls program flow (loops, conditions).
- Works with memory & I/O for efficient data processing.

### Interaction with Components:

- **Control Unit (CU):** Sends instructions, controls ALU.
- **Registers:** Hold operands & results (e.g., accumulator).
- **Memory (RAM/Cache):** Provides data & stores results.
- **I/O Devices:** ALU processes input and outputs results.

---

## 7. ALU in Different Systems

- **Microprocessors (PCs, smartphones):** Game physics, apps, AI.
- **Embedded Systems (washing machine, ATM, sensors):** Simple fixed tasks.
- **Supercomputers:** Multiple ALUs in parallel for heavy simulations (climate, science).

---

## 8. Applications

- Calculators, smartphones, computers.
- Gaming & graphics (physics, AI).
- Cryptography, image processing, compression.
- Data analysis & scientific research.

---

## 9. Summary

- ALU = **core of CPU**, executes all **math + logic**.
- Operations: arithmetic, logical, bitwise.
- Components: Arithmetic Unit, Logic Unit, Status Register, MUX, CU Interface.
- Works with registers, memory, and I/O for processing.
- Found in **all systems**: from simple embedded devices to powerful supercomputers.