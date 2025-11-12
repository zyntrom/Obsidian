# Notes on Instruction Memory & Data Memory in ALU Execution

## 1. Role of Memory in CPU–ALU Operations

- **Registers** = tiny, fast storage (but limited).
- **Memory** = extended workspace for CPU.
- **Instruction Memory:** Stores program code (what to compute).
- **Data Memory:** Stores operands, variables, constants (with what to compute).
- **ALU workflow:**
    - Fetch instruction from instruction memory.
    - Fetch operands from data memory.
    - Perform operation.
    - Store result back in data memory.

---

## 2. Instruction Memory vs Data Memory

|Aspect|Instruction Memory|Data Memory|
|---|---|---|
|Stores|Program code|Operands, variables, constants|
|Access|Sequential (via Program Counter)|Random/non-sequential|
|Type|Read-only during execution|Read & Write|
|Predictability|Highly predictable → supports prefetching & pipelining|Less predictable (depends on program logic)|
|Hardware|Optimized for speed|More complex control logic|

- **Von Neumann Architecture:** Shared instruction + data memory → risk of bottlenecks.
- **Harvard Architecture:** Separate memory for instructions & data → allows parallel access.

---

## 3. Instruction Fetch Cycle

Steps:

1. **Program Counter (PC):** Holds address of next instruction.
2. **Fetch:** CPU reads instruction from instruction memory.
3. **Increment PC:** PC moves to next instruction.
4. **Decode:** Instruction interpreted before execution.

Example (C-like pseudo):  
int instruction = memory[PC];  
PC++;

---

## 4. Accessing Operands (Data Memory)

Steps:

1. Instruction specifies operand addresses.
2. CPU reads values from data memory.
3. Operands sent to ALU.
4. ALU performs computation.
5. Result stored in a register or back to data memory.


Example:  
```
int op1 = memoryA;  
int op2 = memoryB;  
int result = op1 + op2;
```

---

## 5. ALU–Memory Interaction

- ALU requests operands from memory.
- Memory provides data.
- ALU executes operation.
- Result written back to memory (if needed).
- **Registers speed up this process**, but memory holds the bulk of data/instructions.

---

## 6. Control Signals

- Manage data flow like **traffic lights**.
- **Memory Read:** Enable fetch from memory.
- **Memory Write:** Enable store into memory.
- **ALU Enable:** Activate computation.

Example:  
if (memoryRead) data = memory[address];  
if (memoryWrite) memory[address] = data;

---

## 7. Executing a Sample Instruction: `ADD A, B`

1. **Fetch Instruction:** Read `ADD A, B` from instruction memory (PC → increment).
2. **Decode Instruction:** Understand operands A & B must be added.
3. **Fetch Operands:** Read values from memory addresses A and B.
4. **ALU Operation:** Perform addition → A + B.
5. **Store Result:** Write sum back to memory location C.

---

## 8. Memory-Mapped I/O

- CPU communicates with peripherals via **assigned memory addresses**.
- Devices behave like memory locations.
- Example:
    - Write to printer’s address → sends print data.
    - Read from keyboard’s address → retrieves keystrokes.
- **Advantage:** Unified method for memory + device communication.

---

## 9. Summary

- **Instruction Memory:** Stores program code, sequentially accessed.
- **Data Memory:** Stores variables/operands, randomly accessed.
- **PC:** Guides instruction fetch.
- **Operands:** Retrieved from data memory before ALU executes.
- **Control Signals:** Direct memory read/write and ALU enable.
- **Memory-Mapped I/O:** Integrates CPU–device communication via memory addressing.
- **Together:** Instruction memory, data memory, and ALU enable step-by-step CPU execution.
![[Pasted image 20250923114702.png]]