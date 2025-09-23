# **CPU Datapath**

The **CPU datapath** is the internal route data and instructions follow during execution. It connects all functional units—ALU, registers, memory, and control logic—to execute instructions step by step.

---

## **Learning Objectives**

After this lesson, you should be able to:

- Identify CPU datapath components and their roles.
- Explain instruction fetch, decode, and execution.
- Understand memory’s role in datapath.
- Describe control signals and multiplexers for data flow.
- Trace data flow with an example instruction.
- Recognize how pipelining improves CPU performance.

---

## **Major Components**

### 1. **ALU (Arithmetic Logic Unit)**

- Performs arithmetic (add, subtract) and logical (AND, OR, NOT) operations.
- Inputs: Registers; Output: Result stored back in registers or memory.
    

### 2. **Registers**

- Fast, temporary storage for operands and results.
    
- Types:
    
    - **General-purpose registers** (R1–Rn)
        
    - **Special-purpose registers**:
        
        - Instruction Register (IR): Holds current instruction
            
        - Program Counter (PC): Points to next instruction
            

### 3. **Memory**

- **Instruction Memory**: Stores program instructions (read-only during execution).
    
- **Data Memory**: Stores variables, constants, and intermediate results.
    

### 4. **Control Unit**

- Decodes instructions and generates control signals.
    
- Coordinates all datapath activities.
    

### 5. **Multiplexers (MUX)**

- Selects one input from several based on control signals.
    
- Common uses:
    
    - ALU input (register vs immediate)
        
    - Write-back destination (register vs memory)
        
    - Next PC (PC+4 vs branch target)
        

### 6. **Buses and Interconnects**

- Connects all components for data transfer.
    

---

## **Instruction Cycle (Steps)**

1. **Fetch**
    
    - PC provides instruction address.
        
    - Instruction is fetched into IR.
        
2. **Decode**
    
    - Control Unit reads opcode from IR.
        
    - Generates control signals for registers, ALU, memory.
        
3. **Operand Fetch**
    
    - Read operands from register file or immediate value (selected via MUX).
        
4. **Execute**
    
    - ALU performs operation (add, subtract, AND, etc.).
        
    - Result stored temporarily.
        
5. **Memory Access** (if needed)
    
    - Load: Read data from memory
        
    - Store: Write data to memory
        
6. **Write Back**
    
    - Result written back to register (or memory if required).
        

---

## **Memory Integration**

- **Instruction Memory**:
    
    - Stores executable instructions
        
    - Interacts with PC to fetch next instruction
        
- **Data Memory**:
    
    - Stores operands, variables, intermediate results
        
    - Works with ALU, MAR, and MDR
        
- **Control signals**:
    
    - **MemRead**, **MemWrite**: Enable proper memory access
        
    - **RegWrite**, **ALUOp**, **MemtoReg**, **RegDst**: Direct data flow
        

---

## **Example: ADD R1, R2, R3**

Instruction: **R1 = R2 + R3**

|Step|Action|
|---|---|
|**Fetch**|PC provides address; instruction fetched; PC incremented|
|**Decode**|Control unit reads opcode; sets ALUOp=ADD, RegDst=1, ALUSrc=0, RegWrite=1|
|**Operand Fetch**|R2 and R3 read from register file|
|**Execute**|ALU computes R2 + R3|
|**Write Back**|Result written to R1 via MUX and RegWrite enabled|

- All components (ALU, registers, MUX, memory, control unit) work together.
    

---

## **Key Points to Remember**

- CPU datapath = ALU + registers + memory + control unit + MUX
    
- Instructions flow through: **Fetch → Decode → Execute → Memory → Write Back**
    
- Control signals guide data along the correct paths
    
- Multiplexers select between multiple data sources
    
- Instruction memory = code, Data memory = variables/results