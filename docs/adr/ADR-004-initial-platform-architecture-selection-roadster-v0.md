# ADR-004: Initial Platform Architecture Selection (Roadster v0)

- **Status:** Accepted
- **Date:** 2026-04-08

## Context

The initial platform must define a clear drivetrain and packaging architecture to enable:

- Chassis layout development
- Suspension hardpoint definition
- Node and plate system application
- Prototype fabrication

The architecture must balance:
- Simplicity for first implementation
- Compatibility with common donor components
- Accessibility for community builders

The current platform assumptions document defers the decision between front-engine and mid-engine configurations.

## Decision

The **initial platform (Roadster v0)** will use a:

> **Front-engine, rear-wheel drive (FR) layout**

## 1. Core Architecture Definition

- Engine located forward of the passenger compartment
- Transmission located along the longitudinal centerline
- Driveshaft connecting transmission to rear differential
- Rear-wheel drive as baseline configuration

## 2. Packaging Implications

### Defined Zones

The chassis must include clearly defined structural zones:

1. **Front module**
   - Engine bay
   - Front suspension mounting structure
   - Radiator/cooling support

2. **Cockpit module**
   - Seating structure
   - Side-impact structure
   - Pedal box and steering column support

3. **Transmission tunnel**
   - Central structural spine
   - Driveshaft clearance
   - Potential structural contribution

4. **Rear module**
   - Differential mounting structure
   - Rear suspension pickup points

## 3. Donor Compatibility Strategy

The FR layout supports:
- Widely available donor vehicles (e.g., Mazda Miata class)
- Readily available aftermarket suspension components
- Conventional drivetrain alignment and mounting

Specific donor selection will be defined in a separate document.

## 4. Fabrication Benefits

- Simplifies chassis geometry for first iteration
- Reduces need for complex cooling routing
- Minimizes early-stage packaging conflicts
- Enables faster progression to a rolling chassis

## 5. Non-Goals

This ADR does NOT:

- Prevent future mid-engine or alternate layouts
- Define exact engine dimensions or mounts
- Define suspension geometry or hardpoints

## 6. Future Expansion

Future platform variants may include:

- Mid-engine configurations
- Electric drivetrain layouts
- Off-road or truck platforms

These will be implemented as separate platform variants built on the same underlying principles.

## Rationale

Selecting a front-engine, rear-wheel-drive layout:

- Maximizes accessibility and reproducibility
- Aligns with common DIY and kit car practices
- Reduces early-stage engineering complexity
- Enables faster validation of chassis and node systems

This decision prioritizes **progress and validation** over optimal performance or novelty.

## Consequences

### Positive
- Faster path to first rolling chassis
- Easier community adoption
- Broad donor compatibility

### Negative
- Less optimal weight distribution vs mid-engine
- May require redesign for future high-performance variants

## Notes

This ADR establishes the **baseline architecture** for Platform v0.

All subsequent:
- Chassis layouts
- Node definitions
- CAD models

Must assume FR packaging unless superseded by a future ADR.
