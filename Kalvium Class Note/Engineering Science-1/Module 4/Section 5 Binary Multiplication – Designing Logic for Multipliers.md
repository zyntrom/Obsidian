## Binary Multiplication – Designing Logic for Multipliers (Kalvium AL 4.5)

### Learning Objectives

- Understand binary multiplication via **shift-and-add** method.
- Learn how **logic gates** and **adders** build multiplier circuits.
- Differentiate between **signed** and **unsigned** multiplication.
- Explore **real-world applications** of binary multipliers.

---

### Concept of Binary Multiplication

- Works like decimal multiplication:
    1. Multiply each bit of multiplier with multiplicand.
    2. Shift and add partial products.
- **Binary rules:**
    - 0 × 0 = 0
    - 0 × 1 = 0
    - 1 × 0 = 0
    - 1 × 1 = 1
- Advantage: Simple rules → hardware efficient.

![[Pasted image 20250923110222.png]]
---

### Shift-and-Add Algorithm

1. Scan each bit of the multiplier (from LSB to MSB).
2. For each bit:
    - If 1 → add shifted multiplicand to result.
    - If 0 → skip.
3. Shift multiplicand left after each iteration.
4. Accumulate results → final product.

Used in **CPUs/ALUs** for efficient multiplication.

---

### Hardware Implementation

- **AND gates:** Generate partial products (bitwise multiplication).
- **Adders:** Combine partial products.
    - Half Adder → adds 2 bits (sum + carry).
    - Full Adder → adds 3 inputs (sum + carry-out).
- Adders are layered to handle shifted sums.

---

### Designing Binary Multiplier Circuits

- **2-bit Multiplier:**
    - 4 AND gates for partial products.
    - Adders sum them with shifts.
- **4-bit Multiplier:**
    - 16 AND gates for all bit combinations.
    - Multiple full adders combine results.
- Complexity grows **quadratically** with bit size → optimized designs are crucial for speed.
```embed
title: "2-Bit Multiplier Using Half Adders"
image: "https://i.ytimg.com/vi/7Bz9IgFNhDo/maxresdefault.jpg"
description: "Digital Electronics: 2-Bit Multiplier Using Half AddersTopics discussed:1) Introduction to 2-bit Multiplier.2) Circuit for 2-bit multiplier.3) Example on 2-b..."
url: "https://youtu.be/7Bz9IgFNhDo"
favicon: ""
aspectRatio: "56.25"
```

---

### Signed vs. Unsigned Multiplication

**Unsigned Multiplication**

- Assumes all numbers are positive.
- Straightforward application of shift-and-add.
- Example: 5 (0101) × 3 (0011) = 15 (1111).

**Signed Multiplication (Two’s Complement)**

- MSB = sign (0 → positive, 1 → negative).
- Negative numbers → two’s complement form.
- Steps:
    1. Convert negatives to two’s complement.
    2. Multiply as if unsigned.
    3. Determine result sign:
        - (+ × +) → +
        - (+ × –) → –
        - (– × –) → +
- Important for real-world systems (DSP, control, AI).
```embed
title: "Lec-6 What are Signed & Unsigned Numbers | Arithmetic Operations | Number system"
image: "https://i.ytimg.com/vi/XV91bg6KvmQ/maxresdefault.jpg"
description: "👉Subscribe to our new channel:https://www.youtube.com/@varunainashotsArithmetic Operations(Addition, Subtraction, Multiplication, Division). It is of two ty..."
url: "https://youtu.be/XV91bg6KvmQ"
favicon: ""
aspectRatio: "56.25"
```

---

### Simulation & Testing

- Tools: **ModelSim, Verilog/VHDL simulators.**
- Features:
    - Visualize waveforms.
    - Step-by-step execution.
    - Debug timing.
- Ensures correctness before physical hardware.

---

### Real-World Applications

- **ALUs:** Fast arithmetic in CPUs.
- **Digital Signal Processing (DSP):** Filtering, convolution, transforms.
- **Image & Audio Processing:** Scaling, noise reduction, rendering.
- **Cryptography:** Secure, fast large-number multiplications.
- **GPUs:** Matrix/vector ops in graphics and simulations.
- **AI/ML Accelerators:** Neural network multiplications.
![[Pasted image 20250923110327.png]]
---

### Summary

- Binary multiplication → shift-and-add method.
- AND gates form partial products; adders combine them.
- Multiplier circuits grow complex as bit-size increases.
- Signed multiplication uses **two’s complement** for negatives.
- Simulation validates designs before implementation.
- Multipliers are essential in **CPUs, GPUs, DSP, AI, cryptography**.

---

### Bonus Content

- _Design Binary Multiplier Circuit_ | YouTube
- _Signed vs. Unsigned_ | Testbook
- _Binary Multiplier_ | Elprocus
![[Pasted image 20250923110344.png]]