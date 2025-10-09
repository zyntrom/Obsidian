# 🧠 **Lesson 5.3 — Etching and Deposition in Microchip Fabrication**

---

## ⚙️ **Introduction**

Every microchip — from your **smartphone** to a **satellite computer** — is built through **microscopic precision**.  
Two critical processes make this possible:

- **Deposition:** Adding ultra-thin layers of materials.
- **Etching:** Removing or carving patterns from those layers.

Together, they **build and sculpt** the microscopic circuits that power modern electronics.

---

## 🧩 **Overview of Microchip Fabrication Steps**

|Step|Process|Description|
|---|---|---|
|1️⃣|**Substrate Preparation**|A clean silicon wafer is polished and prepared as the base.|
|2️⃣|**Photoresist Application**|A light-sensitive coating (photoresist) is applied.|
|3️⃣|**Lithography**|UV light through a mask hardens selective areas to create a pattern.|
|4️⃣|**Development**|Unwanted photoresist is removed, revealing the design.|
|5️⃣|**Etching**|Material is removed from unprotected regions to form circuits.|
|6️⃣|**Photoresist Removal**|Remaining photoresist is stripped away.|
|7️⃣|**Result**|A single patterned layer is formed — this process repeats for multiple layers.|

---

## 🧱 **Thin Film Deposition**

### 🔹 Definition:

Deposition is the process of **adding thin layers (nanometers thick)** of materials (like metals, oxides, or semiconductors) onto a **wafer**.

👉 Think of it like **spray-painting with atoms** — each layer changes how the chip behaves (conducting, insulating, or semiconducting).

---

## 🧪 **Types of Thin Film Deposition**

### 1️⃣ **Physical Vapor Deposition (PVD)**

**Principle:**  
A **solid material** is **vaporized physically** (using heat or plasma) and then **condensed** onto the wafer as a thin layer.

**Analogy:**  
Like **spray painting with metal vapor**.

**Key Features:**
- No chemical reactions.
- Works in vacuum.
- Common methods:
    - **Sputtering** (ions hit a target → atoms ejected)
    - **Thermal Evaporation**
    - **Electron Beam Evaporation**

**Applications:**  
Used for **metals** (Al, Au, Ti), hard coatings, and optical layers.
```embed
title: "PVD Coating Explained"
image: "https://i.ytimg.com/vi/3fXAy0NzIa0/maxresdefault.jpg"
description: "This video explains how PVD works and the different methods, including thermal evaporation, e-beam and sputtering.  Feel free to comment any questions you ha..."
url: "https://youtu.be/3fXAy0NzIa0"
favicon: ""
aspectRatio: "56.25"
```

---

### 2️⃣ **Chemical Vapor Deposition (CVD)**

**Principle:**  
Reactive **gases (precursors)** are introduced into a **heated chamber**, where they **chemically react** to form a **solid thin film** on the wafer.

**Analogy:**  
Like **perfume vapor** reacting with air and forming a thin residue layer.

#### **Steps in CVD:**

1. **Precursor Gas Introduction** – Reactive gases (e.g., silane SiH₄) enter chamber.
2. **Substrate Heating** – Wafer heated (300°C–1100°C) to trigger reaction.
3. **Chemical Reaction** – Gas molecules react on/near surface to form solid film.
4. **Film Formation** – The solid material deposits as a thin layer.
5. **By-Product Removal** – Waste gases (H₂, CO₂) are removed.
6. **Film Quality Control** – Adjust gas flow, temp, and pressure for uniformity.

**Applications:**  
Used to deposit **SiO₂**, **Si₃N₄**, **tungsten**, **TiN**, etc.
![[Pasted image 20251009160624.png]]
---

## ⚖️ **Comparison: CVD vs. PVD**

|Feature|**Chemical Vapor Deposition (CVD)**|**Physical Vapor Deposition (PVD)**|
|---|---|---|
|**Basic Principle**|Chemical reaction forms film|Physical vaporization & condensation|
|**Material Source**|Gaseous precursors|Solid target material|
|**Operating Temperature**|High (200°C–1000°C)|Lower (50°C–500°C)|
|**Film Adhesion**|Excellent (chemical bonding)|Good (depends on prep)|
|**Film Purity**|May contain impurities|Very pure|
|**Step Coverage (Uniformity)**|Excellent (coats 3D shapes)|Moderate (directional)|
|**Common Materials**|SiO₂, Si₃N₄, tungsten|Al, Au, Ti, oxides|
|**Applications**|Semiconductors, solar cells|Microelectronics, optics|
|**Cost & Equipment**|Complex, expensive|Simple, cheaper|
|**Safety**|Toxic gases used|Safer, uses vacuum/inert gases|

---

## 🔍 **Etching in Microchip Fabrication**

Once the layers are deposited, **etching** removes selected areas to **create circuit paths**.

**Definition:**  
Etching is the process of **removing material** from a wafer’s surface to form patterns or features.

**Analogy:**  
Like a **sculptor carving a statue**, removing parts to reveal the design.
![[Pasted image 20251009160633.png]]
---
```embed
title: "The Etching Process"
image: "https://i.ytimg.com/vi/zkdQddMZSyM/maxresdefault.jpg"
description: "PCMI produced, animated process of Chemical Etching."
url: "https://youtu.be/zkdQddMZSyM"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Fetching"
image: "data:image/svg+xml;base64,PHN2ZyBjbGFzcz0ibGRzLW1pY3Jvc29mdCIgd2lkdGg9IjgwcHgiICBoZWlnaHQ9IjgwcHgiICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIiBwcmVzZXJ2ZUFzcGVjdFJhdGlvPSJ4TWlkWU1pZCI+PGcgdHJhbnNmb3JtPSJyb3RhdGUoMCkiPjxjaXJjbGUgY3g9IjgxLjczNDEzMzYxMTY0OTQxIiBjeT0iNzQuMzUwNDU3MTYwMzQ4ODIiIGZpbGw9IiNlMTViNjQiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM0MC4wMDEgNDkuOTk5OSA1MCkiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49IjBzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9Ijc0LjM1MDQ1NzE2MDM0ODgyIiBjeT0iODEuNzM0MTMzNjExNjQ5NDEiIGZpbGw9IiNmNDdlNjAiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM0OC4zNTIgNTAuMDAwMSA1MC4wMDAxKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMDYyNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iNjUuMzA3MzM3Mjk0NjAzNiIgY3k9Ijg2Ljk1NTE4MTMwMDQ1MTQ3IiBmaWxsPSIjZjhiMjZhIiByPSI1IiB0cmFuc2Zvcm09InJvdGF0ZSgzNTQuMjM2IDUwIDUwKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMTI1cyI+PC9hbmltYXRlVHJhbnNmb3JtPgo8L2NpcmNsZT48Y2lyY2xlIGN4PSI1NS4yMjEwNDc2ODg4MDIwNyIgY3k9Ijg5LjY1Nzc5NDQ1NDk1MjQxIiBmaWxsPSIjYWJiZDgxIiByPSI1IiB0cmFuc2Zvcm09InJvdGF0ZSgzNTcuOTU4IDUwLjAwMDIgNTAuMDAwMikiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49Ii0wLjE4NzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9IjQ0Ljc3ODk1MjMxMTE5NzkzIiBjeT0iODkuNjU3Nzk0NDU0OTUyNDEiIGZpbGw9IiM4NDliODciIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM1OS43NiA1MC4wMDY0IDUwLjAwNjQpIj4KICA8YW5pbWF0ZVRyYW5zZm9ybSBhdHRyaWJ1dGVOYW1lPSJ0cmFuc2Zvcm0iIHR5cGU9InJvdGF0ZSIgY2FsY01vZGU9InNwbGluZSIgdmFsdWVzPSIwIDUwIDUwOzM2MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiIGJlZ2luPSItMC4yNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iMzQuNjkyNjYyNzA1Mzk2NDE1IiBjeT0iODYuOTU1MTgxMzAwNDUxNDciIGZpbGw9IiNlMTViNjQiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDAuMTgzNTUyIDUwIDUwKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMzEyNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iMjUuNjQ5NTQyODM5NjUxMTc2IiBjeT0iODEuNzM0MTMzNjExNjQ5NDEiIGZpbGw9IiNmNDdlNjAiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDEuODY0NTcgNTAgNTApIj4KICA8YW5pbWF0ZVRyYW5zZm9ybSBhdHRyaWJ1dGVOYW1lPSJ0cmFuc2Zvcm0iIHR5cGU9InJvdGF0ZSIgY2FsY01vZGU9InNwbGluZSIgdmFsdWVzPSIwIDUwIDUwOzM2MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiIGJlZ2luPSItMC4zNzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9IjE4LjI2NTg2NjM4ODM1MDYiIGN5PSI3NC4zNTA0NTcxNjAzNDg4NCIgZmlsbD0iI2Y4YjI2YSIgcj0iNSIgdHJhbnNmb3JtPSJyb3RhdGUoNS40NTEyNiA1MCA1MCkiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49Ii0wLjQzNzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT48L2c+PC9zdmc+"
description: "Fetching https://youtu.be/2O1TyJGXuWY"
url: "https://youtu.be/2O1TyJGXuWY"
favicon: ""
```

## 🧰 **Types of Etching**

### 1️⃣ **Wet Etching**

- Uses **liquid chemicals** (acids/bases) to dissolve material.
- **Isotropic** — etches in all directions (may undercut mask).
- **Pros:** Simple, cheap, fast.
- **Cons:** Poor precision, can damage edges.
- **Example:** HF acid etching of SiO₂.

---

### 2️⃣ **Dry Etching**

- Uses **plasma or ion beams** in vacuum chambers.
- Offers **precise, directional (anisotropic)** etching.

#### Types:

|Method|Description|
|---|---|
|**Plasma Etching**|Ionized gas chemically reacts with material — may be isotropic.|
|**Reactive Ion Etching (RIE)**|Combines **chemical + physical** etching — very precise and vertical.|
|**Deep RIE (DRIE)**|Used for **deep trenches** in MEMS/3D chips.|

**Advantages:**

- High precision
- Better control of depth and shape
- Used for **modern nanometer-scale chips**

---

### 3️⃣ **Ion Milling (Ion Beam Etching, IBE)**

- Uses **high-energy ions** to physically bombard and remove material.
- **Very directional (anisotropic)**.
- **Pros:** No chemical residue.
- **Cons:** Slow and can damage surfaces.

---

## 🧭 **Etching Process Steps**

|Step|Description|
|---|---|
|**1. Photoresist Application**|Coat wafer with light-sensitive resist.|
|**2. Mask Alignment & Exposure**|Expose pattern using UV light and a mask.|
|**3. Development**|Remove exposed/unexposed regions depending on resist type.|
|**4. Etching**|Remove material in unprotected regions (wet or dry).|
|**5. Photoresist Removal**|Strip remaining resist, leaving etched pattern.|

---

## 🧠 **Key Differences Between Deposition & Etching**

|Process|Purpose|Type|Analogy|
|---|---|---|---|
|**Deposition**|Adds material|PVD or CVD|Painting a wall with atoms|
|**Etching**|Removes material|Wet or Dry|Carving a sculpture|

Together, they **build (deposition)** and **shape (etching)** every circuit layer.

---

## 🧾 **Summary**

1. **Microchips are built layer by layer** — using deposition (add) and etching (remove).
2. **Thin film deposition** adds ultra-thin coatings via **PVD** or **CVD**.
3. **Etching** precisely removes material using **wet**, **dry**, or **ion beam** techniques.
4. **Photoresist** defines which parts of the wafer are protected during etching.
5. **Deposition + Etching** together enable **tiny, fast, and efficient chips** — powering all modern electronics.

![[Pasted image 20251009160658.png]]