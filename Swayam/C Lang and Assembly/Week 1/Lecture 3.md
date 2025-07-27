# 💻 x86 Instruction Set & Addressing Modes

---

## 🔄 Instruction Cycle Recap

Every CPU instruction goes through three steps:
1. **Fetch** – Get instruction from memory
2. **Decode** – Understand what to do
3. **Execute** – Perform the action

---

## 🧠 Instruction Categories

|Category|Purpose|
|---|---|
|**Data Transfer**|Move data (register ↔ memory, etc.)|
|**ALU Operations**|Arithmetic and logical operations|
|**Stack Operations**|Push/Pop (indirect data transfers)|
|**Control Transfer**|Call, return (subroutines), jumps|

---

## 🛠️ Data Transfer Instructions

### ✅ Syntax (Intel):

```
MOV destination, source
```

- Moves data **from source to destination**
- **Source is unaltered**
- **Direction is right → left**

### 🧪 Examples:

#### 🔹 Register to Register

```
MOV AX, BX    ; AX ← BX
```

#### 🔹 Immediate to Register

```
MOV AX, 0x40  ; AX ← 0x0040 (immediate data)
```

- **Immediate addressing**: data is part of instruction

#### 🔹 Memory to Register (Direct Addressing)

```
MOV [1320h], AX   ; Memory[1320h] ← AX
```

#### 🔹 Register Indirect Addressing

```
MOV AX, [BX]      ; AX ← Memory[BX]
```

- `BX` holds an address
- Requires a segment (typically `DS`)

---

## 🧮 Data Size Keywords

|Keyword|Size|Meaning|
|---|---|---|
|`BYTE PTR`|8-bit|Byte-sized|
|`WORD PTR`|16-bit|Word-sized|
|`DWORD PTR`|32-bit|Double-word-sized|

Example:

```
MOV EAX, DWORD PTR [BX] ; EAX ← 32 bits at address in BX 
MOV BX, WORD PTR [CX]   ; BX ← 16 bits at address in CX
```

---

## 📦 Addressing Modes Summary

|Mode|Example|Description|
|---|---|---|
|**Register Direct**|`MOV AX, BX`|Register-to-register transfer|
|**Immediate**|`MOV AX, 0x1234`|Constant to register|
|**Direct Addressing**|`MOV AX, [1320h]`|Memory location to/from register|
|**Register Indirect**|`MOV AX, [BX]`|Address is held in a register|
|**Register Indirect + Offset**|`MOV AX, [BX + 4]`|Address = BX + 4|
|**Scaled Index** (advanced)|`MOV EAX, [EBX + ECX*4 + 8]`|Complex memory access (beyond scope)|

---

## 🧮 ALU Instructions (Arithmetic & Logic Unit)

### ➕ ADD

```
ADD AX, BX     ; AX ← AX + BX
```

### ➖ SUB

```
SUB AX, BX     ; AX ← AX - BX
```

### ✖️ MUL (Unsigned Multiply)

```
MOV AX, 0x4500 MUL BX         ; AX × BX → DX:AX
```

- **Implicit operand**: AX
- Result spans **DX:AX**

### 🧮 Bitwise Logic

|Operation|Syntax|Meaning|
|---|---|---|
|AND|`AND AX, BX`|AX ← AX & BX|
|OR|`OR AX, BX`|AX ← AX \| BX|
|XOR|`XOR AX, BX`|AX ← AX ^ BX|
|NOT|`NOT AX`|AX ← ~AX|

#### Clear a Register (Fast)

```
XOR AX, AX     ; AX ← 0 (sets Zero Flag)
```

---

## 🚩 Flag Register Behavior

ALU operations **update flags**:

|Flag|Set When...|
|---|---|
|**ZF** (Zero)|Result is zero|
|**CF** (Carry)|Carry out from MSB|
|**SF** (Sign)|Result is negative (MSB = 1)|
|**OF** (Overflow)|Signed overflow occurred|

Example:

```
AND AX, AX ; If AX was zero → ZF = 1
```

---

## 📌 Notes on Segment:Offset Addressing

- Memory addresses in x86 are calculated using:
```
Physical Address = Segment × 16 + Offset
```
- Example:
```
MOV AX, [DS:CX]  ; DS = segment, CX = offset
```

---

## 🧠 Summary

- Assembly provides **fine control** over memory and CPU
- **Data transfer** and **ALU instructions** are the most common
- Addressing modes determine how operands are fetched
- Flags enable **conditional branching**

---

## 📚 Addressing Modes for This Course

You only need to master:

1. **Register Direct**
2. **Immediate**
3. **Direct**
4. **Register Indirect**
5. **Register Indirect + Offset**

(Scaled addressing is out of scope)