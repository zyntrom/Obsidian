# Momentum and Impulse in Data Transmission

## Introduction

- Everyday data transfer (WhatsApp, video calls, web browsing) works on physics concepts.
- Physics principles like **momentum** and **impulse** explain how digital communication flows smoothly and handles errors.
- Analogy: A football kick (momentum) or hammer strike (impulse) ≈ how data packets move or face bursts of interference in networks.

---

## Can Data Packets Have Momentum?

- Data is broken into **packets** (small chunks of information).
- Packets travel across routers, switches, and networks until they reach the destination.

```embed
title: "Data Packets - How does the internet send data?"
image: "https://i.ytimg.com/vi/KjD3KANH-xc/maxresdefault.jpg"
description: "Visit http://brilliant.org/PowerCert/ for a free 30 day trial and a 20% discount on the annual premium subscriptionHow does the internet work?  This is an an..."
url: "https://youtu.be/KjD3KANH-xc"
favicon: ""
aspectRatio: "56.25"
```


### Physics Analogy:

- Momentum = Mass × Velocity
- In Networks:
    - **Mass → Packet size (bytes)**
    - **Velocity → Transfer speed (Mbps)**
    - **Momentum → Communication flow strength (data momentum)**
- Larger packets + higher speed = stronger **data momentum** → faster, more efficient communication.

---

## What If Data Packets Didn’t Exist?

- Without packets, sending large data would be slow, inefficient, and prone to errors.
- Packets allow **efficient routing, retransmission of errors, and fast delivery**.

```embed
title: "Data Packets - How does the internet send data?"
image: "https://i.ytimg.com/vi/KjD3KANH-xc/maxresdefault.jpg"
description: "Visit http://brilliant.org/PowerCert/ for a free 30 day trial and a 20% discount on the annual premium subscriptionHow does the internet work?  This is an an..."
url: "https://youtu.be/KjD3KANH-xc"
favicon: ""
aspectRatio: "56.25"
```

---

## How Does Impulse Show Up in Communication?

### Physics Concept:

- Impulse = Force × Time
- Example: Hammer hitting nail → strong force in short time.

### In Networks:

- **Data bursts**: sudden short transmissions of a lot of information.
- **Impulse noise**: unwanted sudden spikes of interference.

### Causes of Impulse Noise:

- Switching circuits
- Lightning or electrical surges
- Electromagnetic interference (nearby devices)

### Problems Caused:

- Bit flips
- Packet loss
- Disrupted synchronization
- Bad for **real-time communication** (calls, streaming, banking).

---

## Protecting Systems from Impulse Noise

1. **Parity Checks**
    - Add an extra bit to ensure data bits are odd/even.
    - If mismatch occurs → error detected.
    - Simple, but not always enough for burst errors.
```embed
title: "Error Detecting Code : Parity Explained | Odd Parity and Even Parity"
image: "https://i.ytimg.com/vi/Bwih7_AT1oI/maxresdefault.jpg"
description: "In this video, the parity is explained and the use of parity bit in the error detection is explained with examples. The  following topics covered in the vide..."
url: "https://youtu.be/Bwih7_AT1oI"
favicon: ""
aspectRatio: "56.25"
```

1. **Cyclic Redundancy Check (CRC)**
    - Data treated as a long number, divided by a polynomial (generator).
    - Remainder = CRC value, sent with data.
    - Receiver recomputes:
        - If match → correct data.
        - If not → corrupted.
    - Very effective for burst errors.
```embed
title: "Cyclic Redundancy Check (CRC) - Part 1"
image: "https://i.ytimg.com/vi/A9g6rTMblz4/maxresdefault.jpg"
description: "Computer Networks: Cyclic Redundancy Check in Computer NetworksTopics Discussed:1) Cyclic Redundancy Check (CRC).2) Operation of CRC at the sender side.3) Ho..."
url: "https://youtu.be/A9g6rTMblz4"
favicon: ""
aspectRatio: "56.25"
```


---

## Impulse Response in Communication

### Definition:

- Impulse Response = system’s output when given a very short pulse (impulse).

### Why Useful?

- Reveals how system reacts to all signals.
- Like testing a building’s strength by giving it a push.

### Applications:

- Understand how channels distort, delay, or interfere with signals.
- Predict **real-world channel behavior**.
- Identify **inter-symbol interference** (overlapping signals).

### Filters in Systems:

- Shape signals, remove noise, or isolate frequencies.
- Types:
    - **Low-pass filter** → allows low frequencies.
    - **High-pass filter** → allows high frequencies.
    - **Band-pass filter** → allows specific range.

![[Pasted image 20250826093539.png]]

### Importance:

- Stable impulse response → clear, isolated signals.
- Ensures reliable high-speed communication.

---

## Summary

1. **Data packets** = momentum (size × speed).
2. **Impulse in communication** = data bursts (useful) or impulse noise (harmful).
3. **Error detection** = parity checks & CRC fix corrupted packets.
4. **Impulse response** = system test with short input → shows distortion & reliability.
5. **Filters** ensure noise removal & signal clarity.
6. Physics concepts of momentum, impulse, and response are essential for fast, accurate data transmission.

---

## Real-World Applications

- **Messaging & Streaming**: fast packet transfer = smooth communication.
- **Banking Transactions**: CRC ensures no data corruption.
- **Voice Calls**: filters remove noise for clarity.
- **High-Speed Internet**: impulse response testing ensures channel stability.

![[Pasted image 20250826093551.png]]