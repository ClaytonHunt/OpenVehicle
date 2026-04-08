# Component Envelopes v0.1

- **Status:** Draft baseline for platform packaging
- **Date:** 2026-04-08
- **Applies to:** Roadster Platform v0

## Purpose

This document defines the **component envelope method** used to keep the Open Vehicle Platform modular while still grounded in real-world packaging constraints.

The platform is not initially designed around one specific donor. Instead, the chassis is designed around:

1. **Fixed chassis architecture**
2. **Standardized interface zones**
3. **Component bounding envelopes and keep-out zones**
4. **Future donor compatibility validation**

This approach allows the platform to remain system-oriented while still supporting real donor-based implementation later.

## Design Principles

- The main chassis should not be dimensioned directly from one donor unless a later ADR explicitly chooses that path.
- Major structural geometry should be based on platform assumptions, occupant packaging, and module boundaries.
- Variable donor-specific components should fit within defined **envelopes** and connect through defined **interface zones**.
- A component is not considered compatible simply because its outer size fits. Service access, movement, clearance, and adjacent-system routing must also be considered.

## Terms

### Component Envelope
A three-dimensional bounding volume representing the space a component occupies in static installed condition.

### Keep-Out Zone
Additional space around a component that must remain clear for function, movement, heat, service access, or assembly.

### Interface Zone
A chassis-defined region intended to receive donor-specific mounts, brackets, cradles, or adapters.

### Compatibility Class
A grouping of components with similar packaging and installation requirements.

## Packaging Strategy

The platform uses the following workflow:

1. Define a target vehicle class.
2. Define target compatibility classes for major subsystems.
3. Define chassis module boundaries and interface zones.
4. Define component envelopes and keep-out zones.
5. Design chassis structure around those envelopes.
6. Evaluate actual donors against the envelope specification.

## Initial Target Compatibility Classes (Roadster v0)

These are working assumptions for the first chassis generation.

### Powertrain Class
- Compact longitudinal internal-combustion engine
- Rear-wheel-drive manual-transmission compatible
- Small to medium bellhousing and transmission case
- Small independent rear differential

### Suspension Class
- Independent front suspension
- Independent rear suspension
- Upright/knuckle and coilover-compatible packaging

### Vehicle Class
- Lightweight two-seat roadster
- Front-engine, rear-wheel drive (per ADR-004)

## Standard Envelope Categories

The following subsystem envelopes must be defined and checked during layout.

### 1. Engine Envelope
The engine envelope must include:
- Overall length
- Overall width
- Overall height
- Oil pan depth below crank centerline
- Front accessory depth
- Intake-side keep-out zone
- Exhaust-side keep-out zone
- Rear bellhousing interface plane
- Engine mount zone width band
- Hood and firewall service clearance assumptions

### 2. Transmission Envelope
The transmission envelope must include:
- Bellhousing maximum width/diameter region
- Main case width and height
- Tailshaft location and height band
- Shifter zone
- Transmission mount zone
- Tunnel assembly clearance
- Service keep-out for install/removal

### 3. Front Suspension Envelope
The front suspension envelope must include:
- Wheel/tire diameter range
- Wheel/tire width range
- Steering sweep zone
- Bump and droop travel zone
- Upright/knuckle volume
- Coilover/spring-damper volume
- Upper and lower arm sweep zones
- Brake package envelope

### 4. Rear Suspension / Differential Envelope
The rear envelope must include:
- Differential housing volume
- Half-shaft articulation zone
- Rear upright/knuckle volume
- Wheel/tire travel zone
- Shock/spring volume
- Rear suspension link sweep zones
- Differential mounting interface region

### 5. Steering Envelope
The steering envelope must include:
- Steering rack body volume
- Rack travel zone
- Inner tie-rod sweep
- Steering shaft routing envelope
- Pedal box and footwell interference zone

### 6. Cooling Envelope
The cooling envelope must include:
- Radiator core bounding box
- Fan and shroud depth
- Inlet/outlet hose routing space
- Front support structure zone
- Airflow clearance assumptions

### 7. Pedal Box / Driver Interface Envelope
The driver interface envelope must include:
- Pedal box volume
- Pedal swing zone
- Steering column routing space
- Master cylinder or control-system protrusion zone
- Footwell clearance assumptions

### 8. Wheel / Tire Envelope
The wheel and tire envelope must include:
- Nominal tire outer diameter range
- Nominal section width range
- Full steering and suspension travel envelope
- Fender/body clearance assumption

## Interface Zone Strategy

The chassis should provide stable interface zones rather than donor-specific mount geometries.

### Engine Interface Zones
The chassis should define:
- Left engine rail mount zone
- Right engine rail mount zone
- Bellhousing/firewall clearance plane
- Front accessory/cooling clearance zone

### Transmission Interface Zones
The chassis should define:
- Transmission tunnel envelope
- Crossmember mounting band
- Shifter access region

### Front Suspension Interface Zones
The chassis should define:
- Left and right front pickup node regions
- Steering rack mounting band
- Damper tower / upper support region, if used

### Rear Interface Zones
The chassis should define:
- Rear differential mounting region
- Rear suspension pickup node regions
- Rear shock/spring support regions

### Driver Interface Zones
The chassis should define:
- Seat reference region
- Pedal box mounting region
- Steering column routing band

## Envelope Definition Rules

For each envelope, document:
- Reference datum origin or reference plane
- Overall bounding dimensions
- Keep-out zones
- Interface points or mounting bands
- Service/removal direction assumptions
- Adjacent subsystem dependencies

Where possible, dimensions should be expressed relative to the platform datum system defined by ADR-002.

## Compatibility Outcomes

When a real donor component is later evaluated, it must be classified as one of the following:

### Compatible
- Fits inside defined envelope
- Aligns with interface zones
- Requires no major chassis modification

### Compatible with Adapter
- Fits inside defined envelope
- Requires donor-specific brackets, cradles, or mounts
- Does not require changing primary chassis geometry

### Incompatible
- Exceeds envelope or keep-out limits
- Conflicts with major structural zones
- Requires modifying primary chassis geometry or architecture

## Roadster v0 Initial Envelope Direction

Roadster v0 should be laid out to support a **compact longitudinal FR sports-car component class**, not an unrestricted universal donor space.

This means the first platform should intentionally prefer:
- Compact four-cylinder longitudinal engines
- Small manual transmissions
- Small independent rear differentials
- Compact independent suspension corner packages

The platform should not attempt to accommodate all possible powertrains in the first iteration.

## Non-Goals

This document does not:
- Select a final donor vehicle
- Lock final engine, transmission, or suspension part numbers
- Guarantee compatibility with all components in a class
- Replace physical prototype validation

## Next Recommended Deliverables

1. Create envelope tables for:
   - Engine
   - Transmission
   - Front corner
   - Rear corner
2. Define interface-zone diagrams for the v0 roadster chassis.
3. Create a donor compatibility validation checklist.
4. Compare at least one likely donor set against the envelope model.
