# ⚙️ ALU Instructions – Part 2 (8086 Architecture)

---

## 🔼 INC / 🔽 DEC Instructions

### 🔹 `INC` – Increment

```
INC AL     ; AL ← AL + 1 
INC AX     ; AX ← AX + 1 
INC EAX    ; EAX ← EAX + 1
```

### 🔹 `DEC` – Decrement

```
DEC AL     ; AL ← AL - 1 
DEC AX     ; AX ← AX - 1 
DEC EAX    ; EAX ← EAX - 1
```

- These are **ALU operations**.
- **Flags** are affected (ZF, SF, OF, etc.).
- Example:
    - `AL = 0x01`
    - `DEC AL` → `AL = 0x00`, **Zero Flag (ZF)** set.

---

## ⚖️ `CMP` – Compare Instruction

### 🔹 Syntax:
```
CMP AX, BX
```
### 🔹 Behavior:
- Performs: `AX - BX`
- **No register is updated**
- Only **flag registers** are affected:
    - ZF (Zero), CF (Carry), SF (Sign), OF (Overflow)

### 🔹 Use:

- For **conditional branching and loops**
- Comparison types:
```
 CMP BL, CL        ; 8-bit 
CMP BX, CX        ; 16-bit 
CMP EAX, EBX      ; 32-bit 
CMP BX, [ECX-4]   ; register-indirect with offset
```
    

---

## 🔍 String Operation: `SCAS` (Scan String)

### Goal:

Search an **array in memory** for a **specific byte (or word/dword)**.

---

### ✅ Scenario:

- Memory has 256 bytes starting at `data_address`
- Search for `0x21` in that array

---

### 💡 Instruction: `SCASB`

#### Behavior:

```
SCASB
```

- Compares: `AL` ↔ `[ES:DI]`
- Then auto-increments or decrements `DI` (Destination Index):
    - `+1` for `SCASB` (Byte)
    - `+2` for `SCASW` (Word)
    - `+4` for `SCASD` (Double Word)

---

### 🧭 Setup Instructions:

```
CLD                ; Clear Direction Flag → auto-increment 
MOV AL, 0x21       ; Value to search 
MOV CX, 0x0100     ; Count (256 bytes) 
MOV DI, data_address ; Starting memory address 
REPNE SCASB        ; Repeat until equal or CX = 0
```

---

## 📦 How It Works:

1. **Load search value** into `AL`
2. **Set counter** to 256 in `CX`
3. **Point `DI`** to start of array
4. `CLD` ensures **auto-increment**
5. `REPNE SCASB`:
    - Compares `AL` with `[DI]`
    - Increments `DI`
    - Decrements `CX`
    - Repeats until:
        - Match found (ZF = 1), or
        - `CX == 0`

---

## 🧠 Two Possible Outcomes:

### Case 1: Match Found

- `AL == [DI]`
- ZF = 1, loop exits
- Remaining `CX = 256 - n`, where `n` is match index

### Case 2: No Match Found

- Loop runs 256 times
- Final `CX = 0`, ZF = 0

---

## 🔁 About `REPNE`

- **Prefix** to string instructions
- `REPNE SCASB` means:
    > "Repeat while Not Equal and CX ≠ 0"

---

## 🚀 Performance Note

- This is a **hardware loop**, not a software loop
- **Efficient and fast**, only one instruction is issued

---

## 📝 Summary

|Instruction|Meaning|Flags Affected|
|---|---|---|
|`INC reg`|Increment register by 1|Yes|
|`DEC reg`|Decrement register by 1|Yes|
|`CMP A, B`|Subtract B from A, set flags only|Yes|
|`SCASB`|Compare `AL` with `[DI]`, inc DI|Yes|
|`REPNE`|Repeat while not equal, CX ≠ 0|—|

---

## 📌 Pro Tips

- Always **clear the direction flag** with `CLD` before string operations (for forward scanning).
- Use `CX` as the counter for `REP/REPNE` loops.
- `DI` must point to the **start of the data array**.