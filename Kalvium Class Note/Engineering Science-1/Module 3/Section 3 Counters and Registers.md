# Counters and Registers – Notes

## Learning Objectives

- Understand roles of **registers** and **counters** in digital systems
- Differentiate between **General-Purpose Registers (GPRs)** and **Special-Purpose Registers (SPRs)**
- Explain register operations: **Load, Store, Shift, Increment/Decrement**
- Identify types of **shift registers** and their uses
- Compare **asynchronous (ripple)** and **synchronous counters**
- Explain **up, down, up/down counters**
- Recognize real-world applications

---

## Registers

### Definition

- **Tiny high-speed storage units inside the CPU**
- Made up of **flip-flops**
- Provide **faster access than RAM**
- Hold temporary values for immediate processing

### Why Registers Are Important

- **Super-fast access** (same speed as CPU)
- **Quick processing** (no need to fetch repeatedly from RAM)
- **Smooth execution** (hold instructions & data during program run)

### Difference: Register vs RAM

| Feature  | Registers              | RAM                  |
| -------- | ---------------------- | -------------------- |
| Speed    | Very fast (CPU speed)  | Slower               |
| Size     | Very small (few bytes) | Large (GBs)          |
| Location | Inside CPU             | Outside CPU          |
| Purpose  | Immediate data use     | General data storage |

---

## Types of Registers

### 1. General-Purpose Registers (GPRs)

- Store temporary data, variables, and intermediate results
- Flexible use depending on the program
- Example: Storing operands for arithmetic

### 2. Special-Purpose Registers (SPRs)

- Have **fixed roles** in CPU operation

**Examples:**

- **PC (Program Counter):** Holds address of next instruction
- **IR (Instruction Register):** Holds current instruction being executed
- **SP (Stack Pointer):** Tracks top of stack (for function calls, local vars, CPU states)
- **AC (Accumulator):** Used for arithmetic & logic results
- **MAR (Memory Address Register):** Stores memory location address
- **MDR (Memory Data Register):** Stores actual data being transferred

---

## Register Operations

1. **Load (Memory → Register)**  
    `LOAD R1, 1000` → Load value from address 1000 to R1
2. **Store (Register → Memory)**  
    `STORE R1, 1000` → Store R1’s value into address 1000
3. **Shift (Bit Movement)**
    - **Left shift (SHL)** → multiply by 2
    - **Right shift (SHR)** → divide by 2  
        `SHL R1, 1`
4. **Increment/Decrement**
    - `INC R1` → add 1
    - `DEC R1` → subtract 1

---

## Shift Registers

### Definition

- Sequential circuit made of flip-flops
- Moves data **bit by bit** like a conveyor belt

### Types

|Type|Description|
|---|---|
|SISO (Serial-in Serial-out)|Data enters and leaves bit by bit|
|SIPO (Serial-in Parallel-out)|Input serially, output all bits together|
|PISO (Parallel-in Serial-out)|Input all at once, output bit by bit|
|PIPO (Parallel-in Parallel-out)|Input and output all at once|

---

## Counters

### Definition

- Sequential circuits made of flip-flops
- Count **clock pulses** (binary counting)

### Applications

- Digital clocks, timers
- Event counters
- Frequency division

---

## Types of Counters

### 1. Asynchronous (Ripple) Counter

- Flip-flops triggered one after another (like falling dominoes)
- **Drawback:** Slower due to propagation delay
- Example: 4-bit ripple counter (counts 0000 → 1111)

### 2. Synchronous Counter

- All flip-flops triggered **simultaneously** by same clock
- **Faster, no ripple delay**
- Example: 4-bit synchronous counter (0000 → 1111 smoothly)

---

## Advanced Counters

### Up Counter

- Counts upward (0 → 1 → 2 → …)
- Example: Stopwatch, digital clock

### Down Counter

- Counts downward (n → n-1 → … → 0)
- Example: Countdown timer, rocket launch

### Up/Down Counter

- Can count **both directions** using control input
- Example: Elevators, digital volume control

---

## Summary

- **Registers:** High-speed CPU storage
    - GPRs & SPRs (PC, IR, SP, AC, MAR, MDR)
    - Operations: Load, Store, Shift, Increment/Decrement
- **Shift Registers:** Move data serially/parallel (SISO, SIPO, PISO, PIPO)
- **Counters:** Count clock pulses
    - Asynchronous (slow), Synchronous (fast)
    - Up, Down, Up/Down counters for real-world use