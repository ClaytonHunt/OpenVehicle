# Roadster Platform v0.2 Layout

- **Status:** Draft baseline for initial chassis geometry
- **Date:** 2026-04-08
- **Applies to:** Roadster Platform v0

## Purpose

This document converts the Roadster v0 assumptions and accepted ADRs into a first-pass geometric layout baseline that is specific enough to begin:

- chassis bay definition
- envelope placement
- node map development
- first tube table planning
- corner-module prototype design

This is not the final vehicle layout. It is the **first stable geometry baseline** intended to get the platform out of abstract planning and into buildable dimensional work.

## Governing References

This layout assumes the following accepted decisions:

- ADR-001: Chassis Material and Structural Tubing Specification
- ADR-002: Chassis Grid and Modular Geometry System
- ADR-003 / ADR-003A: Node and Plate System v1 baseline
- ADR-004: Initial Platform Architecture Selection (Roadster v0)
- Component Envelopes v0.1

## Coordinate System

The chassis uses the datum strategy defined in ADR-002.

### Datum Definition

- **Origin (0,0,0):** front axle plane intersection with chassis longitudinal center plane at table datum height
- **X-axis:** forward to rearward along vehicle centerline
- **Y-axis:** left to right
- **Z-axis:** bottom to top

### Reference Planes

- **Front Axle Plane:** `X = 0`
- **Firewall Plane:** `X = 32 in`
- **Seat Reference Plane:** `X = 52 in`
- **Rear Axle Plane:** `X = 92 in`
- **Table Datum Plane:** `Z = 0`
- **Vehicle Center Plane:** `Y = 0`

## Locked First-Pass Dimensions

These values are intentionally specific so layout work can begin.

- **Wheelbase:** 92 in
- **Nominal track width target:** 60 in
- **Front module length:** 32 in
- **Cockpit module length:** 40 in
- **Rear module length:** 30 in

### Interpretation

- Front axle to firewall: 32 in
- Firewall to seat reference plane: 20 in
- Seat reference plane to rear axle plane: 40 in
- Total front-to-rear axle spacing: 92 in

These values may be revised later, but only after envelope checks and early node-map work demonstrate a need.

## Chassis Zones

The initial chassis is divided into four structural zones.

### Zone 1: Front Module
**Extent:** `X = -12 in` to `X = 32 in`

Includes:
- front bumper/support structure
- radiator/cooling support zone
- front suspension pickup structure
- steering rack region
- engine front accessory clearance

### Zone 2: Cockpit Front / Firewall Transition
**Extent:** `X = 32 in` to `X = 52 in`

Includes:
- firewall structure
- pedal box region
- steering column routing
- forward footwell package
- front engine / bellhousing transition

### Zone 3: Cockpit / Tunnel Core
**Extent:** `X = 52 in` to `X = 72 in`

Includes:
- seat structure region
- side-impact structure
- transmission tunnel core
- shifter region
- main torsional center section

### Zone 4: Rear Module
**Extent:** `X = 72 in` to `X = 104 in`

Includes:
- differential mounting structure
- rear suspension pickup structure
- rear shock/spring structure
- rear body support region

## Width Strategy

### Initial Width Targets

- **Outer lower chassis width at cockpit:** 52 in
- **Inner cockpit/tunnel opening target before trim/interior:** 42 in
- **Transmission tunnel outer width target:** 10 in to 12 in initial planning band
- **Front module width planning band:** taper or expand as needed to support front suspension and engine envelope

### Notes

- Final outermost body width is not locked by this document.
- Structural width should prioritize occupant packaging, side structure, and suspension pickup efficiency.
- Width values should remain grid-aligned where practical.

## Height Strategy

This document defines planning heights rather than final ride-height-validated chassis elevations.

### Initial Planning Heights

- **Lower main rail baseline:** `Z = 0 in`
- **Secondary lower structure / tunnel floor references:** `Z = 0 in` to `Z = 4 in`
- **Seat base structure planning band:** `Z = 2 in` to `Z = 6 in`
- **Upper side structure planning band:** `Z = 16 in` to `Z = 24 in`
- **Firewall upper tie region:** `Z = 20 in` to `Z = 28 in`

These numbers are placeholders for first-pass node planning and are expected to evolve when occupant package and suspension travel are modeled.

## Envelope Placement Baseline

This layout does not yet lock exact component dimensions. It reserves zones for the envelope classes defined in `component-envelopes-v0.1.md`.

### Engine Envelope Zone

Reserved primarily in:
- `X = 6 in` to `X = 30 in`
- centered on `Y = 0`

Planning intent:
- compact longitudinal engine class
- front accessory clearance ahead of the engine envelope
- bellhousing transition behind engine toward firewall region

### Transmission Envelope Zone

Reserved primarily in:
- `X = 24 in` to `X = 64 in`
- centered on `Y = 0`

Planning intent:
- tunnel-centered transmission path
- serviceable mount band near the rear of the main case
- shifter zone in cockpit/tunnel region

### Front Suspension Envelope Zones

Reserved primarily in:
- left and right corners around `X = -4 in` to `X = 18 in`
- outboard of main chassis center section

Planning intent:
- independent front suspension
- wheel/tire steering sweep
- steering rack placement behind or near axle line depending on detailed geometry later

### Rear Differential / Rear Suspension Zone

Reserved primarily in:
- `X = 76 in` to `X = 96 in`
- centered on `Y = 0` for differential envelope
- outboard left/right regions for uprights, links, shocks, and tire travel

Planning intent:
- compact independent rear suspension class
- small independent rear differential

## First Structural Box Definitions

The initial frame should be conceived as three connected structural boxes plus the tunnel spine.

### Front Box
Approximate extent:
- `X = -8 in` to `X = 32 in`
- centered on vehicle center plane

Intent:
- provide front module stiffness
- support suspension pickup nodes
- support steering and cooling mounts
- tie into firewall structure

### Cockpit Box
Approximate extent:
- `X = 32 in` to `X = 72 in`
- widest and most torsionally important region of chassis

Intent:
- support occupants
- provide side-impact structure
- anchor tunnel spine and upper/lower side rails

### Rear Box
Approximate extent:
- `X = 72 in` to `X = 104 in`

Intent:
- support differential and rear suspension
- carry rear body support structure
- close torsional load path from cockpit to rear axle region

### Tunnel Spine
Approximate extent:
- `X = 24 in` to `X = 88 in`
- centered on `Y = 0`

Intent:
- driveshaft/transmission clearance
- central stiffness contribution
- transmission and shifter packaging support

## Node Planning Baseline

The first node map should focus on a limited set of critical nodes rather than attempting to define the entire chassis at once.

### First Critical Node Groups

1. **Front lower rail to front suspension region**
2. **Firewall lower corner nodes**
3. **Firewall upper tie nodes**
4. **Seat/tunnel mid-structure nodes**
5. **Rear differential support nodes**
6. **Rear suspension pickup nodes**

### Node Type Guidance

- Use **N3** as the baseline node type for major chassis intersections.
- Use **N4** for suspension, differential, engine-mount-adjacent, and seatbelt/harness-adjacent high-load zones.
- Use **N2** sparingly for simple branch or secondary member intersections.

## First Tube Planning Intent

At this stage, do not attempt a full cut list.

Instead, the first-pass tube study should identify:
- lower perimeter rails
- upper side rails
- tunnel rails
- major diagonals
- firewall crossmembers
- rear module support members

These should be laid out so that most lengths remain aligned with the 2-inch grid where practical.

## Immediate Next Deliverables

1. Create a **named node map v0.1** for the chassis baseline.
2. Create a **top-view chassis sketch** with front box, cockpit box, tunnel, and rear box.
3. Create a **side-view chassis sketch** with key height bands and firewall/rear module planes.
4. Publish a **first critical-node list** with intended node class (N2/N3/N4).
5. Publish a **donor compatibility validation checklist** tied to the envelope model.

## Open Questions (Deliberately Deferred)

The following remain open and should not block early layout work:
- exact donor selection
- exact engine and transmission dimensions
- exact suspension geometry
- exact roll structure geometry
- exact seating position and steering-wheel package
- final body width and body styling

## Guidance for CAD Start

When CAD work begins, the first model should not try to capture the entire vehicle.

The preferred order is:
1. datum planes
2. major box extents
3. tunnel band
4. critical node coordinates
5. lower rails
6. upper rails
7. major diagonals
8. envelope placeholders

The goal of the first CAD pass is **clarity and changeability**, not detail completeness.
