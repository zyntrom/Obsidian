## 🔹 String Instructions in x86 Assembly

### 1. **SCAS (Scan String)**

- **Instructions**: `SCASB`, `SCASW`, `SCASD`
- **Purpose**: Compares a register (`AL`, `AX`, or `EAX`) with the memory content pointed to by `DI` (Destination Index).
- **Direction**: Controlled by the **Direction Flag** (DF). Use `CLD` to auto-increment, `STD` to auto-decrement.
- **After Operation**:
    - `DI` increments/decrements by 1 (byte), 2 (word), or 4 (dword).
    - Flags are updated based on the result.
- **Prefix Usage**:
    - `REPNE SCASB`: Repeats until not equal or `ECX = 0`.
    - Useful for searching a **byte pattern** in a memory block.

> **Example**: Searching for `0x21` in a 256-byte array:

```
CLD                     ; Clear direction flag (auto-increment) 
MOV AL, 0x21            ; Load pattern 
MOV CX, 256             ; Set count 
MOV DI, data_address    ; Point to start of array 
REPNE SCASB             ; Scan until match or end
```

---

### 2. **CMPS (Compare String)**

- **Instructions**: `CMPSB`, `CMPSW`, `CMPSD`
- **Purpose**: Compares contents at `[SI]` and `[DI]` (source & destination indexes).
- **Effect**:
    - Flags are affected.
    - `SI` and `DI` auto-increment/decrement depending on DF and operand size.
- **Prefix Usage**:
    - `REPE CMPSB`: Repeat **while equal** and `ECX != 0`.
    - Stops at first mismatch or when count ends.

> **Example**: Compare two 100-byte arrays:

```
CLD                          ; Auto-increment 
MOV SI, ADDR_1               ; Source address 
MOV DI, ADDR_2               ; Destination address 
MOV CX, 100                  ; Count 
REPE CMPSB                   ; Compare strings until mismatch or all                                     matched
```

---

### 3. **MOVS (Move String)**

- **Instructions**: `MOVSB`, `MOVSW`, `MOVSD`
- **Purpose**: Moves data from `[SI]` in DS to `[DI]` in ES.
- **Effect**:
    - `SI` and `DI` auto-increment or decrement.
    - **No flags affected**.
- **Prefix Usage**:
    - `REP MOVSB`: Repeats unconditionally until `ECX = 0`.

> **Example**: Copy 100 bytes from one memory area to another:

```
CLD                          ; Auto-increment 
MOV SI, SRC_ADDR             ; Source in 
DS MOV DI, DEST_ADDR         ; Destination in 
ES MOV CX, 100               ; Count 
REP MOVSB                    ; Copy all bytes
```

---

## 🔸 Summary of Prefixes

|Prefix|Meaning|Typical Use Case|
|---|---|---|
|`REP`|Repeat until `ECX = 0`|Unconditional repeat (e.g., `MOVS`)|
|`REPE`|Repeat while equal & `ECX != 0`|`CMPS` (Compare)|
|`REPNE`|Repeat while not equal & `ECX != 0`|`SCAS` (Scan)|

---

## 🔹 Final Notes

- These string instructions are **hardware-accelerated**, so they are **very efficient** compared to writing manual loops.
- Direction is critical: use `CLD` to ensure incrementing when scanning/copying forward in memory.
- Always initialize `ECX` as the loop counter for these instructions.
- Segment registers matter:
    - `SI` uses **DS**
    - `DI` uses **ES**