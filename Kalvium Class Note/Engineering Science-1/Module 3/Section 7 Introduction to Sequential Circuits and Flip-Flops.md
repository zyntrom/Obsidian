# Notes: Sequential Circuits and Flip-Flops (SPE 2025)

## 1. Sequential Logic Circuits – Introduction

- **Definition**: Circuits whose output depends on **current inputs + past states** (memory).
- **Key Difference from Combinational Circuits**:
    - Combinational → Output depends only on present inputs.
    - Sequential → Output depends on present inputs **and** stored information from past.
- **Analogy**: Robot making decisions based on **current surroundings + memory of past actions**.
- **Usefulness**: Essential for tasks like **counting, state tracking, memory storage**.
![[Pasted image 20250826101636.png]]
---

## 2. Components of Sequential Circuits

### (a) Flip-Flops – Building Blocks

- **Definition**: Basic memory element that stores **1 bit** (0 or 1).
- **Controlled by clock signal** → synchronizes changes.
- **Types**:
    1. **SR (Set-Reset) Flip-Flop**
        - Inputs: S (Set), R (Reset).
        - Output: Q = 1 when S=1, Q=0 when R=1.
        - Problem: Invalid when S=R=1 simultaneously.
    2. **D (Data/Delay) Flip-Flop**
        - Stores input value (D) at clock edge.
        - Q follows D only on clock pulse.
        - Used in **RAM & registers**.
![[Pasted image 20250826101717.png]]
    3. **JK Flip-Flop**
        - Extension of SR flip-flop (removes invalid state).
        - Inputs: J, K.
        - When J=K=1 → toggles output.
    4. **T (Toggle) Flip-Flop**
        - Input: T.
        - Toggles output (Q ↔ Q̅) on each clock pulse if T=1.
        - Used in **counters**.

---

### (b) Registers

- **Definition**: Group of flip-flops storing multiple bits.
- Example: 4-bit register = 4 flip-flops → can store 4-bit number.
- **Analogy**: Attendance sheet → stores data temporarily.

---

### (c) Counters

- **Definition**: Circuits that count events using flip-flops.
- **Types**:
    - **Up Counter** → counts 0 → max, then resets. (e.g., digital clock seconds).
    - **Down Counter** → counts from max → 0. (e.g., countdown timer).
    - **Binary Counter** → counts in binary (e.g., 4-bit: 0000 → 1111).
- **Clocking**:
    - **Asynchronous (Ripple) Counter** → only first flip-flop gets clock, others triggered in sequence → slower, more delay.
    - **Synchronous Counter** → all flip-flops triggered simultaneously by clock → faster, less delay.
![[Pasted image 20250826101648.png]]
---

### (d) Finite State Machines (FSMs)

- **Definition**: Sequential circuit model with finite number of states.
- **Types**:
    - **Mealy Machine** → Output depends on **state + input**. Faster but sensitive to input changes.
    - **Moore Machine** → Output depends **only on state**. More stable but slightly slower.
- **Examples**: Vending machines, traffic lights, gaming consoles, network protocols.

---

## 3. Key Differences: Combinational vs Sequential Circuits

| Feature               | Combinational Circuits        | Sequential Circuits                 |
| --------------------- | ----------------------------- | ----------------------------------- |
| **Memory**            | No memory (stateless)         | Has memory (stateful)               |
| **Output depends on** | Current inputs only           | Current inputs + past states        |
| **Feedback loops**    | No                            | Yes                                 |
| **Example**           | Multiplexer, Adder            | Flip-Flop, Counter                  |
| **Applications**      | Arithmetic, Encoding/Decoding | Memory units, FSMs, Control systems |

---

## 4. Flip-Flop Operation (Detailed)

- **Analysis tools**:
    - **Truth Table** → lists input-output behavior.
    - **Characteristic Equation** → equation describing next state.
    - **Excitation Table** → required inputs for a desired state change.
- **Clocking**:
    - **Rising edge trigger** → activates when clock goes 0 → 1.
    - **Falling edge trigger** → activates when clock goes 1 → 0.
- **Analogy**: Like a camera snapshot → captures data at exact clock edge.

---

## 5. Applications of Sequential Circuits

- **FSMs** → vending machines, traffic controllers, robots, protocol handling.
- **Counters & Timers** → digital clocks, event tracking, pulse generation.
- **Memory (RAM, Registers)** → store instructions and data for CPU.
- **Edge Detection Circuits** → detect signal transitions.
- **Debouncing Circuits** → remove mechanical switch noise (clean signal input).

---

## 6. Applications of Flip-Flops

- Bit storage (1 flip-flop = 1 bit).
- Registers (group of flip-flops).
- Counters (event tracking, clock cycles).
- RAM cells (temporary storage).
- Digital clocks (timekeeping).

---

## 7. Sequential Circuit Design Process

1. Define system behavior.
2. Draw **State Diagram** (states + transitions).
3. Create **State Transition Table**.
4. Derive flip-flop input equations.
5. Simplify using K-Maps.
6. Draw logic circuit.
7. Test & verify.

---

## 8. Summary

- Sequential circuits → **memory-based** (depend on inputs + past states).
- Flip-flops (SR, D, JK, T) are fundamental storage elements.
- Registers store multiple bits; counters track events.
- FSMs (Mealy & Moore) model real-world sequential behavior.
- Used in RAM, CPUs, timers, clocks, vending machines, and robotics.
![[Pasted image 20250826101740.png]]