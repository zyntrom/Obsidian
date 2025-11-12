# Notes: Karnaugh Maps (K-Maps) for Logic Minimization (SPE 2025)

## 1. Logic Minimization – Why?

- Goal: Reduce number of logic gates while keeping same functionality.
- Benefits:
    - Smaller circuits → lower cost.
    - Faster operation → fewer gate delays.
    - Less power consumption → crucial for embedded/battery devices.
- Analogy: Like finding the shortest route (GPS) or building with fewer bricks.

---

## 2. K-Map Basics

- **Definition**: Visual method for simplifying Boolean expressions.
- **Structure**:
    - K-Map = grid of cells.
    - Each cell = a **minterm** (a unique input variable combination).
    - Arranged using **Gray Code** → adjacent cells differ in only one variable.
- **Variables & Grid Size**:
    - 2 variables → 2×2 grid (4 cells).
    - 3 variables → 2×4 grid (8 cells).
    - 4 variables → 4×4 grid (16 cells).

---

## 3. Populating the K-Map

Steps:

1. From truth table / expression, find **minterms** where output = 1.
2. Place **1** in K-Map cells for those minterms.
3. Fill others with **0**.
4. "Don’t Care" terms (X) can be treated as **1 or 0** for easier grouping.

---

## 4. Grouping Rules

- Group **1s** (or 0s, if using maxterms) to simplify expression.
- **Rules**:
    - Groups must be in **powers of 2** (1, 2, 4, 8...).
    - Groups can be horizontal or vertical, **not diagonal**.
    - Groups can **wrap around edges**.
    - Overlapping groups are **allowed** and often required.
- **Purpose**: Larger groups → fewer variables remain in the simplified term.

---

## 5. Deriving Simplified Expressions

- For each group:
    - Identify variables that **remain constant** in that group.
    - Drop variables that **change**.
- Final simplified expression = **OR** of all group terms.

---

## 6. Example Problem

Simplify: **F(A, B, C) = Σm(0, 2, 4, 5, 6)**

### Step 1 – 3-variable K-Map layout

```
BC      00 01 11 10 
A=0   1   0   0   1 
A=1   1   1   0   1
```

### Step 2 – Group 1s

- Group (0, 2, 4, 6) → simplifies to **C’**
- Group (4, 5) → simplifies to **AB**

### Step 3 – Final Expression

F = C’ + AB

---

## 7. K-Maps vs Boolean Algebra

- **Boolean algebra**: algebraic manipulation, can get complicated for many variables.
- **K-Maps**: visual, faster, less chance of error, especially for 3–4 variables.

---

## 8. Real-World Applications

- **Microprocessors** → faster ALU design.
- **Memory chips** → compact, efficient circuits.
- **Control systems** → washing machines, elevators, automation.
- **Embedded systems** → fitness trackers, smart thermostats (low power).
- **Industrial automation** → predictable, reliable sensor/actuator control.

---

## 9. Summary

- K-Maps: Visual tool for Boolean simplification.
- Gray Code ensures adjacency for grouping.
- Groups: powers of 2, wrapping allowed, overlapping possible.
- Output = simpler Boolean expression → fewer gates.
- Used in real-world digital systems for speed, power efficiency, and size reduction.