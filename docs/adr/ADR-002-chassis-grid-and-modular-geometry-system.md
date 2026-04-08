# ADR-002: Chassis Grid and Modular Geometry System

- **Status:** Accepted
- **Date:** 2026-04-08

## Context

A repeatable geometry system is needed so multiple builders can reproduce a chassis with consistent dimensions and so future variants can be developed with controlled dimensional changes.

## Decision

1. **Base design grid**
   - 2-inch base grid for chassis node planning and primary layout.

2. **Tube length modularity**
   - Structural tube lengths should be integer multiples of 2 inches wherever practical.

3. **Global datum system**
   - All major geometry must reference a global datum framework:
     - Longitudinal center plane (X-Z)
     - Vertical center plane (X-Y)
     - Primary table datum plane (X-Y at jig surface)
     - Defined origin node for dimensioning

4. **Jigging strategy**
   - Prefer flat-table jigging for first-build accessibility and repeatability.

5. **Geometry complexity**
   - Avoid compound angles unless a measurable performance, packaging, or load-path need justifies them.

6. **Future parametric capability**
   - Chassis architecture should support future controlled variation in:
     - Wheelbase
     - Track width
     - Ride height

## Consequences

- Improves community reproducibility and quality control.
- Reduces setup complexity and rework risk.
- May constrain some packaging solutions compared with highly sculpted frames.
- Enables later parameterized development without redesigning every bracket/jig from scratch.
