# Gravitational Forces and Satellite Communication

## 1. What is an Orbit?

- Orbit is **not a place**, but a **motion**.
- Defined as: _The curved path an object follows as it continuously falls toward a planet but keeps missing it because it moves forward fast enough._
- Example:
    - Cannonball Thought Experiment (Newton):
        - At low speed → cannonball falls to the ground.
        - At higher speed → travels farther before falling.
        - At ~28,000 km/h → keeps “falling around” Earth → continuous orbit.

**Key Point:** An orbit is a **continuous free fall** around Earth due to balance between speed and gravity.
```embed
title: "What Does Orbit Mean?"
image: "https://i.ytimg.com/vi/MTWMv9-9Zwg/maxresdefault.jpg"
description: "What's an Orbit?Instagram: https://www.instagram.com/kevinjdebruin/Website: https://www.kevinjdebruin.com/"
url: "https://youtu.be/MTWMv9-9Zwg"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Newton's cannonball Cosmos A Spacetime Odyssey episode 3  part 12"
image: "https://i.ytimg.com/vi/9BjC7NQuB_M/maxresdefault.jpg"
description: "Newton's original plan for Philosophiæ Naturalis Principia Mathematica was that it should consist of two books, the first analyzing basic laws of motion, and..."
url: "https://youtu.be/9BjC7NQuB_M"
favicon: ""
aspectRatio: "56.25"
```


---

## 2. 🛰️ What Keeps GPS Satellites in Orbit?

- GPS satellites orbit at ~20,200 km (Medium Earth Orbit).
- Complete one orbit in ~12 hours (2 orbits per day).
- Orbit maintained by **balance of forces**:
    - Gravity → pulls inward.
    - Forward velocity → keeps sideways motion.
- This balance creates a stable curved path (not crashing or drifting away).

**Impact on GPS:**

- Phones know satellite positions from predictable orbits.
- Distance measured using **signal travel time**.
- At least 4 satellites used for **triangulation** → precise location.
- Analogy: Like hearing shouts from different corners of a stadium to locate someone.

---

## 3. Why Orbits Matter for Connectivity

- **Gravitational Potential Energy (GPE):**
    - Energy due to position in Earth’s gravitational field.
    - Higher satellites → higher GPE → less atmospheric drag → more stability.
- Satellite Orbit Types & Uses:

|Orbit Type|Altitude|Use Case|
|---|---|---|
|LEO (Low Earth Orbit)|~200–2,000 km|Earth observation, Starlink internet|
|MEO (Medium Earth Orbit)|~20,200 km|GPS navigation|
|GEO (Geostationary Orbit)|~36,000 km|TV broadcasts, weather satellites|
```embed
title: "How do Satellites work? | ICT #10"
image: "https://i.ytimg.com/vi/ror4P1UAv_g/maxresdefault.jpg"
description: "We live our lives knowing that many satellites orbit our planet everyday, and that they are helping us in several ways. You might be surprised to know that t..."
url: "https://youtu.be/ror4P1UAv_g"
favicon: ""
aspectRatio: "56.25"
```

---

## 4. Kepler’s Third Law & Its Importance

- **Law:** T² ∝ R³
    - T = orbital period (time to complete one orbit)
    - R = average distance from Earth
- Application:
    - Predicts satellite speed and orbital period.
    - Ensures GPS/communication satellites are synchronized.

**Example:**

- GPS satellites (MEO):
    - Altitude = ~20,200 km
    - Period = ~12 hours
    - Timing must be precise (nanosecond-level).
    - Even tiny timing errors cause large location errors.
![[Pasted image 20250826094114.png]]
---

## 5. GPS Systems & Precise Timing

- GPS satellites transmit:
    1. **Exact position**
    2. **Exact timestamp of signal sent**
- Phone calculates:
    - Travel time of signals.
    - Distance from each satellite.
    - Uses triangulation with at least 4 satellites.

**Why accuracy matters:**

- Nanosecond errors → meter-level position errors.
- Precise orbits (via Kepler’s laws) make global GPS possible.

---

## 6. Satellite Constellations for Global Communication

- Example: **Starlink** (SpaceX).
- Satellites placed in **LEO** (~500–2,000 km).
- Characteristics:
    - Orbit time: 90–120 minutes.
    - Thousands needed for full Earth coverage.
- **Kepler’s laws** used to:
    - Predict positions.
    - Synchronize orbits.
- **Seamless handoff:** Devices switch automatically between satellites to maintain uninterrupted connection.
![[Pasted image 20250826094132.png]]
---

## 7. Summary

1. Orbit = continuous free fall due to gravity + forward speed.
2. GPS satellites in MEO orbit (20,200 km) → enable location via triangulation.
3. Gravitational potential energy keeps satellites stable against drag.
4. Kepler’s Third Law predicts satellite motion & period.
5. GPS accuracy depends on precise timing and orbital mechanics.
6. Satellite constellations (e.g., Starlink) use coordinated orbits for global communication.
7. Gravity is the invisible force enabling modern connectivity (GPS, internet, TV, weather, etc.).