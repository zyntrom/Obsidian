# Notes: Combinational Logic Circuits (SPE 2025)

## 1. What are Combinational Circuits?

- **Definition**: Circuits where the **output depends only on the current inputs**.
- **No Memory**: They don’t store past input values (unlike sequential circuits).
- **Components**: Built from **logic gates** (AND, OR, NOT, NAND, NOR, XOR).
- **Analogy**: Like a **light switch** – output (light on/off) depends only on present input (switch position).
![[Pasted image 20250826101233.png]]
---

## 2. Design Process

Designing combinational circuits follows a systematic process:

1. **Specification** – Define what the circuit must do.
2. **Truth Table** – Map all possible inputs → outputs.
3. **Boolean Expression** – Derive logic from truth table.
4. **Simplification** – Use Boolean algebra or K-Maps to reduce.
5. **Logic Diagram** – Draw simplified circuit with gates.
6. **Implementation** – Build with logic gates.
7. **Testing** – Verify outputs against truth table.

---

## 3. Basic Building Blocks

### (a) Adders

- **Half Adder**:
    - Inputs: A, B
    - Outputs:
        - Sum (S = A ⊕ B)
        - Carry (C = A • B)
- **Full Adder**:
    - Inputs: A, B, Carry-in (Cin)
    - Outputs:
        - Sum (S = A ⊕ B ⊕ Cin)
        - Carry-out (Cout = AB + BCin + ACin)
- **Use**: Multi-bit binary addition in processors.

---

### (b) Multiplexer (MUX)

- Selects **1 input from many** and forwards it to a single output.
- Inputs: n data inputs + log₂(n) select lines.
- Analogy: **Railway switch** selecting one track.
- Example: 4-to-1 MUX → 4 inputs, 2 select lines, 1 output.

---

### (c) Demultiplexer (DEMUX)

- Takes **1 input** and routes it to **one of many outputs**.
- Analogy: **Water pipe** directing flow into one room at a time.
![[Pasted image 20250826101243.png]]
---

### (d) Encoders

- Converts **active input line → binary code output**.
- Example: 4-to-2 encoder → 4 inputs → 2-bit binary output.
- Analogy: Translator converting signals to binary language.

---

### (e) Decoders

- Reverse of encoder: **binary input → activates one output line**.
- Example: 3-to-8 decoder → 3 inputs → 8 outputs.
- Analogy: Guide that maps digital input → specific action.
![[Pasted image 20250826101315.png]]
---
```embed
title: "Lec -25: Introduction to Encoder and Decoder | Digital Electronics"
image: "https://i.ytimg.com/vi/DqCDQH44y9w/maxresdefault.jpg"
description: "What is Encoder and Decoder in Digital Electronics? In this video, Varun Sir will break down the basics of Encoders and Decoders—what they are, how they work..."
url: "https://youtu.be/DqCDQH44y9w"
favicon: ""
aspectRatio: "56.25"
```

### (f) Arithmetic Logic Unit (ALU)

- Performs **arithmetic (add, subtract, multiply)** and **logic (AND, OR, XOR, NOT, comparisons)**.
- Central to **CPUs, GPUs, DSPs**.

---

## 4. Applications

- **ALU** → Arithmetic & logic in CPUs.
- **Memory Address Decoding** → Select correct memory cell in RAM/ROM.
- **Encryption Circuits** → Hardware-based AES, RSA for secure communication.
- **Adders** → Used in calculators, processors.
- **MUX/DEMUX** → Communication systems, data routing.
- **Encoders** → Keyboards (convert key press → binary code).
- **Decoders** → Memory selection, instruction decoding.

---

## 5. Real-World Relevance

- Microwave timers, washing machine controllers → simple combinational logic.
- Smartphones, supercomputers → complex ALUs, encoders/decoders, multiplexers.
- Everywhere digital systems require **instant, predictable output from inputs**.

---

## 6. Summary

- **Combinational circuits**: Output depends only on current inputs.
- **Design flow**: Specification → Truth Table → Simplify → Implement → Test.
- **Building blocks**: Adders, MUX/DEMUX, Encoders/Decoders, ALU.
- **Applications**: CPUs, memory, encryption, keyboards, communication systems.
![[Pasted image 20250826101338.png]]