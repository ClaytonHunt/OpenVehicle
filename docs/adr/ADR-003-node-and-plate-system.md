# ADR-003: Node and Plate System for Straight-Tube Chassis

- **Status:** Proposed
- **Date:** 2026-04-08

## Context

To avoid mandatory tube bending while preserving strength and repeatability, the chassis needs a standardized connection method for intersecting straight tubes. The method must be feasible for hobbyist tools, compatible with CNC/plasma suppliers (including SendCutSend-like workflows), and aligned with the 2-inch grid system.

## Proposal

Adopt a **node-and-plate system** where structural tubes terminate into standardized node regions using flat cut plates, gussets, and tabs/slots.

### 1) Node taxonomy

Define a small set of reusable node classes:

- **N2:** Two-member inline or T-joint node
- **N3:** Three-member corner/intersection node
- **N4:** Four-member high-load intersection node
- **NX:** Special-case node with documented rationale

Each node instance gets a unique ID (e.g., `N3-FL-012`) linked to CAD, cut list, and weld map.

### 2) Plate roles

At each node, use one or more of:

- **Shear plates** to transfer in-plane loads
- **Cap/closure plates** to box high-load zones
- **Gusset plates** to increase local stiffness and spread loads
- **Doubler plates** for localized reinforcement at brackets/pickups

### 3) Manufacturing constraints

- Plate stock thickness targets:
  - 3 mm (light brackets)
  - 4.8 mm / 3/16" (general structural plates)
  - 6.35 mm / 1/4" (high-load local reinforcement)
- Internal corners should include relief suitable for common cutting processes.
- Prefer tab-and-slot self-jig features where they improve assembly repeatability.

### 4) Weld and assembly philosophy

- Prioritize access for full weld paths during staged assembly.
- Avoid hidden joints requiring blind welding.
- Use balanced tacking and sequence control to reduce distortion.
- Define “weld critical” nodes requiring documented fit-up tolerances and inspection points.

### 5) Data model and documentation

For each node:

- Node ID and class
- Connected tube IDs and cut lengths
- Plate part IDs and material thickness
- Datum-referenced coordinates
- Required jig references
- Weld notes and inspection checklist

### 6) SendCutSend-compatible workflow preference

Where possible, prefer geometry compatible with online cut-part ordering constraints:

- Single-plane plate parts
- Minimum hole sizes and edge clearances appropriate to vendor constraints
- Explicit deburr/chamfer notes where fit-up depends on them

(Exact vendor limits should remain in a separate, updateable manufacturing guideline rather than hard-coded in this ADR.)

## Rationale

- Keeps fabrication approachable while supporting modular design.
- Improves repeatability versus ad-hoc cope/fishmouth methods.
- Bridges CAD-to-fab handoff through explicit part IDs and node metadata.

## Risks / Tradeoffs

- Additional plate count can increase weight and cost if overused.
- Poor node standardization could produce complexity creep.
- Requires disciplined documentation to prevent part/version mismatch.

## Validation Plan (before acceptance)

1. Build and inspect a representative subframe section using N2/N3/N4 nodes.
2. Record distortion, fit-up time, and rework rates.
3. Perform practical static load checks on critical nodes (non-certification-level).
4. Compare mass/cost against a simpler non-standardized baseline.
5. Gather community fabrication feedback from at least two independent builds.

## Non-Goals

- This ADR does not claim crash certification.
- This ADR does not define suspension kinematics or powertrain hardpoints.
