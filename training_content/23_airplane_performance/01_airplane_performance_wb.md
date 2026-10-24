# Airplane Performance, Weight and Balance
## Reading the Numbers Before You Fly

---

> **AI-DRAFTED — PENDING CFI REVIEW.** This airplane-category chapter was drafted from FAA source documents and has **not yet been reviewed by a certificated flight instructor**. Treat it as study support, not an authoritative reference. Verify every number, chart-reading method, and limit against your aircraft's POH before relying on it. Sources are cited inline.

---

## How This Chapter Fits

Airplane **category-specific** content. The shared GA core (weather, ADM, cross-country method) applies unchanged; this chapter covers the airplane-specific performance numbers and weight-&-balance method that a fixed-wing pilot computes from the POH — V-speeds, takeoff/landing distances corrected for density altitude, and a worked weight-&-balance example.

Sources: *Pilot's Handbook of Aeronautical Knowledge* (FAA-H-8083-25C, Aircraft Performance / Weight and Balance), *Airplane Flying Handbook* (FAA-H-8083-3C), and the *Private Pilot — Airplane ACS* (FAA-S-ACS-6C). **All performance numbers below are illustrative — your POH governs.**

---

## V-Speeds

V-speeds are the standardized airspeeds that define an airplane's operating envelope. The exact numbers are **airplane-specific (POH)**; the meanings are standard (PHAK):

| V-speed | Meaning |
|---|---|
| **V_S0** | Stall speed, landing configuration (full flaps, gear down) — bottom of the white arc |
| **V_S1** | Stall speed, a specified (usually clean) configuration — bottom of the green arc |
| **V_R** | Rotation speed (takeoff) |
| **V_X** | Best **angle** of climb — most altitude per distance (obstacle clearance) |
| **V_Y** | Best **rate** of climb — most altitude per time |
| **V_FE** | Maximum flap-extended speed — top of the white arc |
| **V_NO** | Maximum structural cruising speed — top of the green arc / start of the yellow arc |
| **V_NE** | Never-exceed speed — the red line |
| **V_A** | Maneuvering speed — decreases with weight (see Aerodynamics) |
| **V_G** | Best glide speed (engine-out — best L/D) |
| **V_GLIDE / V_REF** | Approach reference speed (often 1.3 × V_S0), per POH |

**V_X vs V_Y**: use **V_X** to clear an obstacle (steepest climb over the ground), then transition to **V_Y** (fastest gain of altitude) once clear. Both decrease with altitude and converge at the absolute ceiling.

---

## Density Altitude — the Master Variable

**Density altitude** is pressure altitude corrected for non-standard temperature — the altitude the airplane "feels." High density altitude (hot, high, humid) **degrades every aspect of performance**: less engine power, less propeller thrust, less wing lift (PHAK).

Consequences: **longer takeoff roll, shallower climb, higher true airspeed for the same indicated airspeed, and longer landing roll.** "Hot, high, and heavy" is the classic accident setup — run the numbers before committing on a hot day at a high-elevation airport.

- **Pressure altitude** = indicated altitude with the altimeter set to 29.92, or field elevation corrected for the difference from 29.92.
- High **humidity** further reduces power (water vapor displaces air) — not modeled on most charts, so add margin.

---

## Takeoff and Landing Distance Charts

The POH provides **takeoff** and **landing** distance charts (ground roll and total distance over a 50-ft obstacle) as a function of **weight, pressure altitude, temperature, wind, and runway surface/slope**. Reading method (PHAK):
1. Enter with the day's **pressure altitude and temperature** (or density altitude).
2. Correct for **weight**.
3. Correct for **headwind/tailwind** (a tailwind dramatically lengthens distance).
4. Correct for **runway surface** (grass/soft adds distance) and **slope**.
5. Apply the manufacturer's and your own **safety margin** — book numbers come from a new airplane and a test pilot; add margin (a common personal rule is +50%, *your call with your CFI*).

> **Worked illustration (numbers fictitious — use your POH):** at 3,000 ft pressure altitude, 30°C, max gross weight, no wind, paved level runway, the chart might give a ground roll of ~1,200 ft and ~2,000 ft over a 50-ft obstacle. The same airplane at sea level / 15°C might need only ~900 ft / ~1,600 ft. The difference is density altitude.

---

## Climb, Cruise, and Range

- **Climb performance** charts give rate of climb and time/fuel/distance to climb at V_Y for the weight, altitude, and temperature.
- **Cruise performance** tables give true airspeed and fuel flow at a chosen power setting (RPM/manifold pressure) and altitude — lean per the POH to get book fuel flows.
- **Range and endurance** follow from usable fuel ÷ fuel flow (endurance) and TAS × endurance (still-air range), corrected for winds aloft. Always apply the regulatory reserve (§ 91.151: 30 min day / 45 min night VFR).

---

## Weight and Balance

Two independent questions must both pass: is the airplane **within weight limits**, and is the **center of gravity (CG) within the forward/aft envelope** (PHAK, Weight and Balance)?

### Why it matters
- **Overweight**: longer takeoff, reduced climb and ceiling, higher stall speed, structural margin eroded.
- **CG too far forward**: heavy on the controls, higher stall speed, may lack elevator authority to flare/rotate.
- **CG too far aft**: reduced longitudinal stability, dangerously easy to stall, **degraded stall/spin recovery** — the more hazardous direction.

### The method (moment = weight × arm)
1. List each item's **weight** and its **arm** (distance from the datum, per the POH): empty airplane, pilot+front passenger, rear passengers, fuel, baggage.
2. Compute each **moment** = weight × arm.
3. Sum weights → **total weight** (must be ≤ max gross).
4. Sum moments → divide by total weight → **CG** (must fall within the POH envelope).
5. Re-check the CG **as fuel burns** — the CG shifts as fuel (and its moment) is consumed; it must stay in the envelope for the whole flight.

> **Worked illustration (numbers fictitious — use your POH):**
> | Item | Weight (lb) | Arm (in) | Moment (lb-in) |
> |---|---|---|---|
> | Empty airplane | 1,500 | 39.0 | 58,500 |
> | Pilot + front pax | 340 | 37.0 | 12,580 |
> | Fuel (40 gal × 6 lb) | 240 | 48.0 | 11,520 |
> | Baggage | 40 | 95.0 | 3,800 |
> | **Total** | **2,120** | — | **86,400** |
>
> CG = 86,400 ÷ 2,120 ≈ **40.8 in**. If max gross is 2,300 lb and the CG envelope at this weight is ~35-47 in, this load is **within limits**. (Aviation fuel ≈ **6 lb/gal**; arms and limits are POH-specific.)

---

## Summary

1. **Know your V-speeds** (POH): V_X for obstacles, V_Y for rate, V_A drops with weight, V_G for glide.
2. **Density altitude** is the master variable — hot/high/humid degrades takeoff, climb, and landing.
3. **Read the POH distance charts** for the day's conditions and add a personal safety margin.
4. **Weight and balance**: be within weight AND within the CG envelope — aft CG is the dangerous direction; recheck as fuel burns.
5. **Run the numbers before you fly** — "hot, high, and heavy" is a predictable, avoidable trap.

---

**Document Version**: 1.0 (AI-drafted, pending CFI review)
**Last Updated**: 2026-06-04
**Sources**: FAA-H-8083-25C (PHAK), FAA-H-8083-3C (AFH), FAA-S-ACS-6C (Private Airplane ACS), 14 CFR 91.151.
**For Training Purposes**: Educational content on airplane performance and W&B; all numbers illustrative. Your POH is the authoritative source.
