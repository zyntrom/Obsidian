# Two’s Complement and Binary Subtraction

---

## 1. Binary Number Representation Recap

- Binary numbers use only **0** and **1**.
- Each digit (bit) position = power of 2.
- Example: `1011` → (1 × 2³) + (0 × 2²) + (1 × 2¹) + (1 × 2⁰) = 11 (decimal).
- **Why important?** → Computers store & manipulate numbers in binary.

---

## 2. What is Two’s Complement?

- A method to represent **signed integers** (both +ve and -ve) in binary.
- **MSB (Most Significant Bit)** indicates the sign:
    - `0` = positive
    - `1` = negative
- Benefits:
    - Same circuitry handles **addition & subtraction**.
    - No need for separate subtraction hardware.

---

## 3. How to Find Two’s Complement

**Steps:**

1. Invert all bits (0 → 1, 1 → 0) → _One’s complement_.
2. Add `1` to the result.

**Example 1:** Find 2’s complement of `0110` (6 decimal).

- Invert: `1001`
- Add 1: `1010` → represents `-6`

**Example 2:** Find 2’s complement of `10101010`.

- Invert: `01010101`
- Add 1: `01010110`

---

## 4. Performing Binary Subtraction Using Two’s Complement

**Steps:**

1. Find 2’s complement of the subtrahend (number being subtracted).
2. Add it to the minuend (number from which subtraction happens).
3. If there is a carry-out → discard it.

**Example:** `0101 (5)` − `0011 (3)`

- 2’s complement of `0011`:
    - Invert → `1100`
    - Add 1 → `1101`
- Perform addition: `0101 + 1101 = 10010`
- Discard carry: `0010 (2)` ✅

```embed
title: "Binary subtraction using 2’s complement | 2’s Complement subtraction"
image: "https://i.ytimg.com/vi/R64AJ5dptvA/maxresdefault.jpg"
description: "2’s complement subtraction is basically Binary subtraction using 2’s complement. The video focuses on how to do subtraction using 2’s complement. The initial..."
url: "https://youtu.be/R64AJ5dptvA"
favicon: ""
aspectRatio: "56.25"
```

---

## 5. Examples with Signed Numbers

### Example 1: Negative − Positive

```
1110 (-2) − 0010 (2)
```

- 2’s complement of `0010`: `1110`
- Add: `1110 + 1110 = 11100`
- Discard carry → `1100 (-4)` ✅

### Example 2: Positive − Negative

`0010 (2)` − `1110 (-2)`

- 2’s complement of `1110`: `0010`
- Add: `0010 + 0010 = 0100 (4)` ✅

---

## 6. Overflow Detection in Two’s Complement

- **Overflow**: result > range of representable values.
- Rule:
    - If **carry-in** ≠ **carry-out** of MSB → Overflow.
    - If they are same → No overflow.

**Example:** 4-bit addition: `0100 (4)` + `0100 (4)`

- Result = `1000`
- Carry-in = 0, Carry-out = 1 → Overflow!
- Wrong result: `1000` = -8 instead of +8.

---

## 7. Advantages of Two’s Complement

- **Simplified Circuits** → Addition & subtraction with same hardware.
- **No Separate Sign Bit** → Sign encoded in MSB.
- **Unique Zero** → Only one representation for `0`.
- **Efficient Arithmetic** → Faster operations.

---

## 8. Summary

- Two’s complement = invert bits + add 1.
- Binary subtraction = add two’s complement of subtrahend to minuend.
- Discard carry-out.
- Overflow = when MSB’s carry-in ≠ carry-out.
- Advantages: simple, efficient, unique zero, unified circuits.

---

## 9. Bonus Content 🎁

- **Overflow Rules** → [Sandbox]
- **Numericals** → [University of Buffalo]
- **Binary Subtraction** → [Neso Academy]