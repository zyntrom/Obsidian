# Multi-bit Addition and Ripple Carry Adders — Notes

## Recap

- **Full Adder (FA):** Adds 2 input bits (A, B) + carry-in (Cin).
    - Outputs: Sum (S), Carry-out (Cout).
- **Needed for multi-bit addition** where numbers have multiple bits.

---

## Multi-bit Addition

- Works like decimal addition with carry-over.
- To add N-bit numbers: use N **full adders** in series.

---

## Ripple Carry Adder (RCA)

- **Definition:** A chain of full adders, each handling one bit.
- **Connection:**
    - Inputs: Two N-bit numbers (A, B).
    - First FA’s Cin = 0.
    - Each FA passes its Cout → next FA’s Cin.
    - Outputs: N-bit Sum + final Cout.

### Example: 4-bit RCA

- Uses 4 full adders.
- Cout from FA0 → Cin of FA1 → Cin of FA2 → Cin of FA3.

---

## Ripple Carry Effect (Delay)

- Carry signal must travel through **each adder sequentially**.
- Known as **carry propagation delay**.
- **Limitation:** Delay grows linearly with number of bits (O(N)).
    - 4-bit RCA → 4 stages of delay.
    - 64-bit RCA → 64 stages of delay (very slow).
```embed
title: "Carry Propagation Delay in Ripple Carry Adder || Lesson 86 || Digital Electronics || Learning Monkey"
image: "https://i.ytimg.com/vi/WfhWsAWXsFM/maxresdefault.jpg"
description: "Here we will try to understand Carry Propagation Delay in Ripple Carry Adder.In our previous video, we understood the ripple carry adder.There whenever we do..."
url: "https://youtu.be/WfhWsAWXsFM"
favicon: ""
aspectRatio: "56.25"
```

---

## Limitations & Solutions

- **Slow for large N** due to ripple effect.
- **Alternatives:**
    - **Carry Lookahead Adders (CLA):** Calculate carries in parallel.
    - **Carry Select Adders:** Speed up by precomputing sums for possible carry values.

---

## Use Cases

- **Simple calculators** (low-cost, small designs).
- **Digital signal processing (DSP)** (basic additions).
- **Embedded systems** where speed is less critical.
![[Pasted image 20250923105407.png]]
---

## Quick Summary

- **Ripple Carry Adder = Multiple FAs in series.**
- Easy to design, but **slow due to carry propagation delay**.
- Used in simple devices; **advanced adders (CLA, CSA)** improve speed for high-performance CPUs.

![[Pasted image 20250923105349.png]]

![[Pasted image 20250923105415.png]]