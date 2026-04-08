# ADR-003A: Node and Plate System v1 Reference Implementations

- **Status:** Accepted
- **Date:** 2026-04-08
- **Supersedes/Clarifies:** `ADR-003: Node and Plate System for Straight-Tube Chassis`

## Purpose

This record converts ADR-003 from a conceptual proposal into a **buildable v1 baseline** by defining reference physical implementations for the initial node classes.

ADR-003 remains the governing conceptual document for taxonomy, plate roles, manufacturing constraints, weld philosophy, metadata, and validation. This companion ADR adds the minimum physical implementation guidance needed to design and fabricate first-pass prototype joints.

## Decision

The platform adopts the following **reference node implementations (v1)** for early prototype work.

These implementations are intentionally conservative and are expected to evolve after subframe and corner-module validation.

## 1. Global v1 Rules

- Structural tube members terminate square unless a documented exception is approved.
- Tube-to-tube fishmouth/cope joints are **not** the default for Phase 1 structural fabrication.
- Node geometry should prefer flat-cut plate interfaces, tab-and-slot self-location where useful, and visible weld access.
- Plate stacks and gussets must not create blind cavities that prevent welding, coating, drainage, or inspection.
- Node designs should privilege repeatability and assembly clarity over minimum part count.

## 2. Reference Node Implementations

### N2: Inline / T-Joint Node

**Use for:**
- Secondary crossmembers
- Non-critical member intersections
- Straight-through members with one branching member

**Reference implementation:**
- Tube ends terminate flush against a shared structural plate or boxed plate pair.
- General plate thickness: **3/16 in (4.8 mm)**
- Use a single shear plate only where load path and weld access are clearly adequate.
- For T-joints carrying meaningful secondary load, use opposing plates or one plate plus a gusset.
- Full weld path is preferred on all accessible tube-to-plate interfaces.

**v1 default rule:**
- If there is any uncertainty about out-of-plane stiffness, add a gusset.

### N3: Three-Member Corner / Junction Node

**Use for:**
- Perimeter frame corners
- Diagonal brace tie-in points
- Cockpit and bay corner transitions

**Reference implementation:**
- Two orthogonal structural plates minimum.
- Diagonal or non-collinear member tie-ins require at least one gusset plate.
- General plate thickness: **3/16 in (4.8 mm)**
- Tab-and-slot alignment features are recommended where they simplify jigging and reduce fit-up ambiguity.
- Tube ends should be captured against plate faces rather than relying on unsupported weld gaps.

**v1 default rule:**
- N3 nodes are the standard baseline node for major non-suspension chassis intersections.

### N4: Four-Member / High-Load Node

**Use for:**
- Suspension pickup regions
- Differential support regions
- Engine mount regions
- Seatbelt anchor support regions
- Other locally high-load intersections

**Reference implementation:**
- Fully boxed or partially boxed node region with closure plates as needed.
- Base structural plate thickness: **1/4 in (6.35 mm)** in local reinforcement regions.
- Tube ends should terminate into a captured node region, not an unsupported plate tab.
- Gussets and/or doubler plates are required wherever load introduction is concentrated.
- Designs must preserve weld access and inspection visibility.

**v1 default rule:**
- If a node carries suspension, powertrain, harness, or differential loads, treat it as N4 unless explicitly justified otherwise.

## 3. Weld and Assembly Baseline

- Fully welded joints are the default for structural node interfaces.
- Stitch welding is not the default structural assumption for Phase 1 chassis nodes.
- Tack sequence must maintain datum alignment before final welding.
- Node designs must be staged so a builder can realistically access welds without destructive rework.
- “Weld critical” nodes must include explicit fit-up and inspection notes in manufacturing documentation.

## 4. Plate Thickness Selection Baseline

Use the following as the default decision rule until testing suggests refinement:

- **3 mm**: light brackets and non-structural or lightly loaded mounting features
- **3/16 in (4.8 mm)**: standard structural node plates and gussets
- **1/4 in (6.35 mm)**: high-load local reinforcement, N4 closure plates, suspension and powertrain-adjacent reinforcement

If uncertain, choose the stronger baseline for prototype validation and record the mass/cost impact.

## 5. Acceptance Scope

ADR-003 is considered **accepted for v1 prototype work** when used together with this companion ADR.

This means the project may now proceed with:
- corner-module prototype design
- first chassis layout work
- first tube table and plate set development

## 6. Follow-Up Requirement

After fabrication of at least one representative prototype assembly, the project should either:
- fold this content back into ADR-003 and retire ADR-003A, or
- revise both documents into a cleaner production-ready node standard.
