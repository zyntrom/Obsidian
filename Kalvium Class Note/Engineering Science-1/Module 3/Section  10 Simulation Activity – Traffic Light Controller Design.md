# Traffic Light Controller – Sequential Logic System

## 🔹 Core Idea

- Use **D Flip-Flops + Logic Gates** to build a **traffic light controller**.
- Works as a **sequential logic circuit** (depends on **current + past states**).
- Simulation: **CircuitVerse** (online digital circuit simulator).

---

## 🔹 Sequential Logic

- **Combinational Logic:** Output = f(Current Input) only.
- **Sequential Logic:** Output = f(Current Input + Previous State).
- Needs **memory** → implemented using **flip-flops**.

---

## 🔹 Flip-Flops (Memory Makers)

- Hold state until changed by clock/input.
- Types:
    - **SR:** Basic, can be unstable.
    - **D:** Stable, stores 1 bit → **used in traffic light design**.
    - **JK:** Flexible, toggles.
    - **T:** Toggles each clock cycle.

---

## 🔹 Logic Gates (Decision Makers)

- Control state transitions.
- Example: AND gate ensures green only after yellow + timer.

---

## 🔹 Real-World Applications

- Traffic lights (state cycle).
- Digital counters.
- Memory (RAM).

---

## 🔹 Traffic Light Controller Design

### 1. States

- Red → Stop
- Green → Go
- Yellow → Caution
- **Sequence:** Red → Green → Yellow → Red → …

---

### 2. State Table

| Current State | Next State  |
| ------------- | ----------- |
| Red (00)      | Green (01)  |
| Green (01)    | Yellow (10) |
| Yellow (10)   | Red (00)    |

---

### 3. Binary Encoding

- Red = **00**
- Green = **01**
- Yellow = **10**
- Stored using 2 **D Flip-Flops** (Q1 = MSB, Q0 = LSB).

---

### 4. Logic Derivation (Next State Equations)

Use Boolean algebra / K-map:

- **D1 = Q0**
    
- **D0 = !Q1** (NOT Q1)
    

Where:

- Q1 = current MSB
    
- Q0 = current LSB
    

---

### 5. Circuit Steps in CircuitVerse

1. Add **2 D Flip-Flops**.
    
2. Connect outputs (Q1, Q0) → Logic gates → Inputs (D1, D0).
    
3. Equations:
    
    - D1 = Q0
        
    - D0 = NOT Q1
        
4. Add **3 LEDs** (Red, Green, Yellow).
    
    - Red ON when state = 00
        
    - Green ON when state = 01
        
    - Yellow ON when state = 10
        
5. Add a **Clock** signal.
    
6. Simulate → Watch sequence cycle correctly.
    

---

## 🔹 Testing & Debugging

- Run simulation → check sequence order.
    
- Adjust **clock frequency** for timing.
    
- If wrong sequence → check wiring & logic.
    

---

## 🔹 Key Takeaways

- **Sequential Logic** = depends on history.
    
- **D Flip-Flops** provide memory.
    
- **Logic Gates** control state transitions.
    
- Traffic Light Cycle → implemented via state machine with binary encoding.
    

---

👉 This is the **final simplified implementation**:

- **D1 = Q0**
    
- **D0 = NOT Q1**