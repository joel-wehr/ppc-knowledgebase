# Weight and Balance for Powered Parachutes
## How Much You Can Load, and Where the Cart Hangs

---

## Introduction

The preflight lesson (`01_preflight_operations.md`) reminds you to
"calculate total weight and verify it's within limits." This lesson is
the *how* — and the *why* it's different for a powered parachute than for
an airplane. Weight and balance is a full area of the Sport Pilot ACS
(Area VI), it appears in the practical-test oral, and it's a leading
factor in the kind of accidents that happen on a hot day with two big
adults and full fuel.

A PPC is unusual: the **wing sets your maximum weight and stall behavior**,
while the **cart's hang point** (where the cart attaches to the wing's
lines) sets your pitch attitude and trim. There is no movable cargo to
slide fore and aft, and the "CG" question is more about *hang-point geometry*
and *total load* than about a long arm of baggage. But the consequences of
getting it wrong — sluggish or impossible climb, a higher stall speed, a
nose-down or tail-heavy attitude, a longer takeoff roll on a hot day — are
just as real.

**Key Principle**: The wing can only lift so much, and it lifts it best at
a designed trim attitude. Overload it or hang the load badly and you don't
get a warning bell — you get a takeoff that won't climb, a stall that
arrives early, or a flare that mushes. The check happens **on the ground,
before you commit.**

> Authoritative sources: **PHAK FAA-H-8083-25C, Chapter 10 (Weight and
> Balance)** and **Chapter 11 (Aircraft Performance)** for the general
> method; **FAA-H-8083-29 (PPC Flying Handbook)** and **your wing and cart
> manufacturer's documentation** for the PPC-specific limits and the
> hang-point concept. Use *your* aircraft's published numbers for any real
> computation — the figures in the worked example below are **illustrative
> only**.

---

## Section 1: Why Weight Matters in a PPC

Every pound you add does three things, all bad if you overdo them:

1. **Raises stall speed.** A more heavily loaded wing must fly faster to
   produce the lift to hold you up. Stall speed rises with the square root
   of the weight increase — so a heavier load shrinks your already-narrow
   speed margin.
2. **Hurts climb and takeoff.** More weight means more lift required, more
   induced drag, a longer ground run, and a shallower climb. Combine heavy
   load with **density altitude** (hot, high, humid) and a PPC that climbs
   fine on a cool morning may barely clear the trees in the afternoon.
3. **Loads the structure and wing.** Exceeding max gross weight stresses
   the cart, lines, and wing beyond their design margins.

Because a PPC is *already* a low-performance aircraft (slow, limited
climb), it has **less margin to absorb an overload** than a faster
airplane. Respect the max-gross number.

---

## Section 2: The Vocabulary (Datum, Arm, Moment)

These are the standard FAA weight-and-balance terms (PHAK Ch 10). They
apply to a PPC, though as you'll see, the *balance* arithmetic is simpler
than an airplane's.

- **Datum**: an arbitrary reference point (set by the manufacturer) from
  which all distances are measured.
- **Arm**: the horizontal distance from the datum to a point where weight
  acts (in inches).
- **Moment**: weight × arm. It's a measure of the *turning effect* of a
  weight about the datum (in inch-pounds).
- **Center of gravity (CG)**: the point where the total weight is
  considered to act — found by dividing total moment by total weight.
- **Empty weight**: the aircraft as it sits, without occupants or usable
  fuel (but *including* fixed equipment; for Part 103 the BRS and floats
  are excluded from the 254-lb limit specifically — see the certification
  module).
- **Useful load**: max gross weight minus empty weight — everything you're
  allowed to add (you + passenger + fuel + gear).
- **Max gross weight**: the manufacturer's maximum allowable total weight
  for takeoff. The hard ceiling.

The general balance formula (used for airplanes, and the method the ACS
expects you to know):

```
CG = total moment ÷ total weight
```

---

## Section 3: What's Different About a PPC — the Hang Point

Here is the PPC-specific part the airplane W&B chapter doesn't cover.

A powered parachute doesn't have a fixed wing bolted to a fuselage. The
**cart hangs from the wing's lines/risers at the hang point** (sometimes
two attach points on a hang bar or mast). That geometry — *where* the cart
hangs relative to the wing's lift, and the relationship between the
**center of gravity** of the cart-plus-occupants and the **center of
lift/thrust line** — sets:

- **Pitch attitude and trim airspeed.** Move the hang point or shift the
  load and you change the wing's angle of attack at trim, hence your
  hands-off airspeed.
- **Thrust line vs. CG relationship.** On a PPC the prop thrust acts along
  the engine's thrust line, while drag and weight act elsewhere; the offset
  is what causes the **power-on pitch/surge behavior** you trim and fly
  around (and why a sharp power change can pitch the cart — see the
  emergency lesson on surge/dive).

**Practical implications for the pilot:**

- **Trim is your pitch control.** Many PPCs have an adjustable trim
  (foot-bar or hang-point adjustment) that's set partly for **pilot
  weight**. A heavier pilot may need a different trim setting than a light
  one for the wing to fly at its designed attitude. This is why the
  preflight checklist says "adjust trim if needed for pilot weight."
- **Solo vs. dual changes the hang loading.** Adding a passenger doesn't
  just add weight — it changes how and where the cart hangs, affecting
  pitch and the power response. Fly a familiar solo cart before assuming a
  loaded one handles the same.
- **Follow the manufacturer's loading guidance.** Cart and wing makers
  publish how to set the hang point/trim for different loads. This is
  equipment-specific; don't improvise hang-point changes.

> **Bottom line:** in a PPC, "balance" is less about *moving cargo* and
> more about **staying within max gross** and **setting the hang
> point/trim correctly for the load you're carrying.** Both are set on the
> ground.

---

## Section 4: Wing Loading

**Wing loading** is the aircraft's weight divided by the wing's area
(lb per square foot). It's a useful single number for understanding how a
given load will behave:

- **Higher wing loading** (heavier load on the same canopy) → **higher
  stall/flying speed, faster sink, faster but firmer flare, more
  responsive but less forgiving.**
- **Lower wing loading** (lighter load) → slower flight, gentler, more
  affected by wind and turbulence.

A wing is certified/sized for a **range** of wing loading (an occupant
weight range, effectively). Flying a small canopy heavily loaded, or a big
canopy very lightly loaded, both push toward the edges of good behavior.
Match the wing to the load — this is part of why make/model and wing-size
matter, and why a solo-rated light wing isn't automatically fine for two
adults.

---

## Section 5: Weight, Density Altitude, and Performance Together

Weight rarely acts alone. The dangerous combination is **heavy load +
high density altitude**:

- **Density altitude** is the altitude the air "feels like" to the wing
  and engine — it rises with heat, elevation, and humidity. High density
  altitude means thinner air: **less lift, less prop thrust, less engine
  power.**
- A PPC near max gross on a hot, humid afternoon at a higher-elevation
  field is being asked to climb out on a wing that makes less lift, behind
  an engine making less power. **Takeoff roll lengthens and climb rate
  drops** — sometimes to near zero.

**The performance-planning habit:**

1. Compute today's **weight** (Section 6).
2. Estimate today's **density altitude** (high temperature + field
   elevation + humidity push it up).
3. Ask honestly: *with this weight, in this air, will this aircraft climb
   and clear obstacles?* On a marginal day the right answer is **fly
   lighter** (less fuel, solo, or wait) or **fly in the cool of the
   morning.**

(Density altitude theory is developed further in the Principles of Flight
module; the point here is that **weight is one of the levers you control**
to keep performance in the safe column.)

---

## Section 6: A Worked Weight Computation (Illustrative)

> **These numbers are illustrative only** to show the method. Use your own
> aircraft's empty weight, max gross weight, and limits — they vary by cart
> and wing. Fuel is figured at **6 lb per U.S. gallon** (consistent with
> the preflight lesson).

**Scenario:** a two-place PPC. Suppose the manufacturer lists:
- Empty weight: **340 lb**  *[VERIFY against your cart's actual weighed empty weight]*
- Max gross weight: **750 lb**  *[VERIFY against your cart/wing limit]*

You want to fly with a passenger and a near-full tank.

| Item | Weight |
|---|---|
| Empty weight (cart, ready to fly) | 340 lb |
| Pilot | 200 lb |
| Passenger | 180 lb |
| Fuel (8 gal × 6 lb/gal) | 48 lb |
| Gear (helmets, water, kit) | 10 lb |
| **Total** | **778 lb** |

**Compare to max gross (750 lb):**
778 − 750 = **28 lb over.** Not legal, not safe — especially on a warm
day.

**Fixing it — adjust the lever you control (fuel/load):**
- Carry **less fuel.** To save 28 lb you'd drop ~5 gallons (5 × 6 = 30 lb),
  leaving 3 gallons — too little for a useful flight with reserve.
- So the honest answer is: **this pilot + this passenger can't both fly in
  this cart with useful fuel.** Options: a lighter passenger, a single
  occupant, a higher-gross cart/wing, or splitting into two solo flights.

**The lesson of the example**: with two adults, a PPC's useful load gets
tight fast, and **fuel is usually the only variable you can trim** — which
trades directly against endurance and your 30-minute reserve (§ 91.151).
Run the numbers *before* you strap in, not after the cart won't climb.

### If your aircraft has a CG/hang-point range

Some carts publish a CG or hang-point range as well as a weight limit. If
yours does, build the full table (weight × arm = moment for each item),
sum the moments, divide by total weight, and confirm the CG falls within
the published range — the standard PHAK Ch 10 method. For many simple PPC
carts the manufacturer instead expresses this as an **occupant weight
range and a hang-point/trim setting** rather than an inch-based CG
envelope; follow whichever form your manufacturer publishes.

---

## Section 7: Required Records (LSA)

For a registered light-sport PPC operated by a sport pilot, **current
weight-and-balance data must be aboard the aircraft** (the "W" in the
ARROW documents — see the General Operating Rules module, § 91.9 /
§ 91.203). For a **Part 103 ultralight**, no such documents are required —
but the *physics* of overload still applies, so a Part 103 pilot should
know the empty weight, max gross, and occupant limits all the same.

---

## Summary

| Concept | What to remember |
|---|---|
| Max gross weight | The hard ceiling — never exceed it |
| Useful load | Max gross − empty weight = you + pax + fuel + gear |
| Stall speed vs. weight | Heavier load → higher stall speed, smaller margin |
| Hang point / trim | Sets pitch attitude; adjust for pilot/load weight |
| Wing loading | Match wing size to the load; both extremes handle poorly |
| Weight + density altitude | The dangerous combo — fly lighter or earlier |
| Fuel | ~6 lb/gal; usually your only adjustable weight lever |
| Records (LSA) | Current W&B data must be aboard (ARROW) |

**Remember**: a PPC won't tell you it's overloaded until you're committed —
a takeoff that won't climb, a stall that comes early, a flare that mushes.
The two-adults-and-full-fuel day is exactly when the numbers matter most.
Compute the load, account for density altitude, set the hang point/trim
for what you're carrying, and when the arithmetic says "too heavy," the
answer is to **lighten the load, not the standards.**

---

**Companion lesson**: [Pre-Flight Operations](01_preflight_operations.md)
**Related**: density altitude theory in
[Principles of Flight](../01_foundations/01_principles_of_flight.md);
required documents (ARROW) in
[General Operating Rules](../13_general_operating_rules/01_part_91_for_sport_pilots.md).

**Document Version**: 1.0
**Last Updated**: 2026-06-03
**Primary sources**: PHAK FAA-H-8083-25C, Ch. 10 (Weight & Balance) and
Ch. 11 (Performance); FAA-H-8083-29 (PPC Flying Handbook); manufacturer
cart/wing documentation. The worked-example figures are illustrative —
always use your own aircraft's published limits.
