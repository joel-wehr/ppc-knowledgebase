# Airplane Systems and Powerplant
## The Machinery of a Fixed-Wing Airplane

---

> **AI-DRAFTED — PENDING CFI REVIEW.** This airplane-category chapter was drafted from FAA source documents and has **not yet been reviewed by a certificated flight instructor**. Treat it as study support, not an authoritative reference. Verify every system detail against the current FAA handbooks and — above all — your aircraft's POH before relying on it. Sources are cited inline.

---

## How This Chapter Fits

Airplane **category-specific** content. The shared GA core applies unchanged; this chapter covers the systems that differ fundamentally from a powered parachute: a four-stroke engine, fuel and induction systems, a (possibly constant-speed) propeller, an electrical system, landing gear and brakes, flaps, and the pitot-static and avionics systems.

Sources: *Pilot's Handbook of Aeronautical Knowledge* (FAA-H-8083-25C, Aircraft Systems / Flight Instruments), *Airplane Flying Handbook* (FAA-H-8083-3C), and the *Private Pilot — Airplane ACS* (FAA-S-ACS-6C). System specifics vary by airplane — the POH is authoritative.

---

## The Powerplant: Four-Stroke Reciprocating Engine

Most training airplanes use an air-cooled, horizontally opposed, **four-stroke** reciprocating engine (vs. the two-stroke common on PPCs). The four strokes (the "Otto cycle"): **intake → compression → power → exhaust** (PHAK).

### Ignition — dual magnetos
Airplane engines use **two independent magnetos**, each firing its own set of spark plugs. Magnetos are **self-powered** (engine-driven) and independent of the electrical system — the engine keeps running if the battery/alternator fails. The **run-up mag check** verifies each magneto: a small RPM drop on each is normal; an excessive drop or no drop indicates a fault (*specific allowable drop and max differential are in the POH*).

### Fuel/air metering: carburetor vs. fuel injection
- **Carburetor**: meters fuel into the induction air via a venturi. Susceptible to **carburetor icing** — the temperature drop across the venturi can form ice even in warm, humid air at low power, causing a gradual power loss (fixed-pitch: RPM drop). The cure is **carburetor heat** (applied before icing-prone conditions; expect a small RPM drop when applied). 
- **Fuel injection**: meters fuel directly to each cylinder; no carb-ice risk, but requires a **priming/hot-start** technique and is more susceptible to **vapor lock** when hot (*follow the POH start procedure*).

### Mixture control
Air thins with altitude, so the pilot **leans the mixture** to maintain the correct fuel/air ratio at altitude — improving efficiency and preventing rough running/fouled plugs. Lean per the POH (often referencing EGT). Full rich for takeoff at low elevations; lean for cruise and for high-density-altitude takeoffs per the POH. *(Procedures are airplane-specific.)*

### Engine instruments
Tachometer (RPM), oil pressure and oil temperature (primary engine-health gauges), cylinder-head temperature (CHT), exhaust-gas temperature (EGT, for leaning), and — on constant-speed installations — a **manifold pressure** gauge.

---

## The Propeller

- **Fixed-pitch propeller**: one blade angle; RPM (tachometer) is the power reference. Simple; common on basic trainers.
- **Constant-speed (variable-pitch) propeller**: a **governor** varies blade pitch to hold a selected RPM, letting the pilot set power with **two controls** — the **throttle** (sets manifold pressure) and the **propeller control** (sets RPM). General technique: avoid high-manifold-pressure/low-RPM combinations; for power changes increase RPM before manifold pressure and reduce manifold pressure before RPM (*the exact sequence and limits are in the POH*). A constant-speed prop extracts more efficient performance across the flight regime and is part of the **complex airplane** definition.

> A **complex airplane** has retractable landing gear, flaps, and a controllable-pitch propeller; operating one requires specific training/endorsement (*verify the current definition and endorsement requirement in 14 CFR 61.31*).

---

## Fuel System

- **Tanks** (usually in the wings) feed the engine by **gravity** (high-wing) or **fuel pumps** (low-wing, which add an engine-driven pump plus an electric auxiliary/boost pump).
- **Fuel selector** (e.g. BOTH/LEFT/RIGHT/OFF) manages tank feed; mismanagement (selector position, uneven feed) is a leading cause of fuel starvation.
- **Avgad/100LL** is the common piston aviation fuel (blue); some airplanes are approved for unleaded alternatives or are diesel/Jet-A (*type-specific*). **Sumping** fuel from each drain at preflight checks for water and correct grade/color.
- Fuel **quantity** gauges are required but notoriously imprecise — **visually verify** fuel and compute endurance from known burn rates, not just the gauges.

---

## Electrical System

- A typical light airplane has a **14- or 28-volt DC** system with an engine-driven **alternator** (or generator) and a **battery**.
- The **master switch** energizes the bus; the **alternator/field switch** brings the alternator online; an **ammeter or loadmeter** shows charge/discharge.
- The electrical system powers radios, lights, electric flaps/gear, and most instruments — but **not the magnetos** (engine ignition is independent) and **not the basic pitot-static instruments**. An alternator failure means running on battery: shed load and land.
- **Circuit breakers/fuses** protect circuits; a popped breaker may be reset once per the POH.

---

## Landing Gear and Brakes

- **Fixed gear**: simplest; nothing to forget.
- **Retractable gear**: raised/lowered hydraulically or electrically with a gear-position indicator and warning horn (sounds with gear up + low power). The classic failure is the **gear-up landing** from a missed checklist — use the GUMPS/landing checklist on every approach (*see emergencies, PR4*).
- **Tricycle vs. tailwheel**: most trainers are **tricycle** (nosewheel) — more directionally stable on the ground; **tailwheel** ("conventional") airplanes need active directional control and a tailwheel endorsement.
- **Brakes** are independent left/right (toe brakes) for differential braking and steering; nosewheel steering is via the rudder pedals.

---

## Flaps

**Flaps** extend from the trailing edge to increase camber (and on some types, area), raising the lift coefficient and allowing a **steeper, slower approach** at a lower stall speed. Types include plain, split, slotted (most common on trainers), and Fowler. Use per the POH: partial flaps for normal takeoff/short-field as specified, full flaps for landing. Flaps increase drag (especially at higher settings) — expect a pitch change and added drag when extending/retracting, and follow the POH airspeed limits (**white arc, V_FE**) for flap operation.

---

## Pitot-Static Instruments

The **pitot-static system** drives three instruments from ram air (pitot) and static pressure (PHAK, Flight Instruments):
- **Airspeed indicator** (pitot + static) — a blocked **pitot** makes it read like an altimeter (rises in a climb); a blocked **static** freezes the reading and corrupts altimeter/VSI. The **pitot heat** and **alternate static source** address blockages.
- **Altimeter** (static) — set to the local altimeter setting (§ 91.121).
- **Vertical speed indicator / VSI** (static) — rate of climb/descent.

### Airspeed color codes (the arcs)
- **White arc**: flap operating range (V_S0 to V_FE).
- **Green arc**: normal operating range (V_S1 to V_NO).
- **Yellow arc**: caution range (smooth air only).
- **Red line**: V_NE, never-exceed speed.
*(The exact speeds are airplane-specific — read them off your airspeed indicator and POH.)*

### Gyroscopic instruments
Vacuum- or electrically-driven gyros drive the **attitude indicator**, **heading indicator**, and **turn coordinator** (the latter also shows coordination via the inclinometer "ball"). Modern airplanes may use a solid-state **electronic flight display (glass cockpit)** instead. Know your airplane's instrument power sources and failure modes.

### Magnetic compass
The wet magnetic compass is the basic direction reference with known errors: **variation, deviation, dip (UNOS — Undershoot North, Overshoot South), and acceleration/deceleration errors (ANDS — Accelerate North, Decelerate South)** — *verify the mnemonics' applicability for your hemisphere.*

---

## Summary

1. **Four-stroke engine** with **dual magnetos** (engine-independent ignition) — verify both at run-up.
2. **Carb heat** prevents/clears carburetor ice; fuel injection avoids carb ice but needs a hot-start technique.
3. **Lean the mixture** with altitude per the POH.
4. **Constant-speed prop** = two power controls (throttle = manifold pressure, prop = RPM); part of a complex airplane.
5. **Fuel management** (selector, sumping, visual check) prevents starvation.
6. **Electrical**: alternator + battery; magnetos and pitot-static are independent of it.
7. **Retractable gear** → run the landing checklist to avoid a gear-up landing.
8. **Flaps** lower approach/stall speed and add drag — respect the white-arc limits.
9. **Pitot-static** drives airspeed/altimeter/VSI; know the arcs and blockage failures.

---

**Document Version**: 1.0 (AI-drafted, pending CFI review)
**Last Updated**: 2026-06-04
**Sources**: FAA-H-8083-25C (PHAK), FAA-H-8083-3C (AFH), FAA-S-ACS-6C (Private Airplane ACS), 14 CFR 61.31.
**For Training Purposes**: Educational content on airplane systems, not yet reviewed by a CFI. Your POH is the authoritative source for your airplane.
