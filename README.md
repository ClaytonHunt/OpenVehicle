# Open Vehicle Platform (OVP)

Open Vehicle Platform is an open-source, modular approach to building a **full-size road-going vehicle** with fabrication methods accessible to motivated hobbyists and small shops.

## Vision

Build a practical first platform—a lightweight roadster/sports car—using:

- Straight steel tubing (no required tube bending for primary chassis)
- CNC/plasma-cut brackets, gussets, and plates
- Flat-table jigging and repeatable geometry
- 3D-printed, non-structural body panels

## Current Scope (Phase 1)

This repository is currently scoped to:

1. Core chassis architecture and fabrication standards
2. Node and plate connection strategy for straight-tube construction
3. Initial roadster platform assumptions and packaging targets
4. Documentation that supports implementation by community builders

## Safety, Legality, and Responsibility

This project is experimental and educational.

- **Crashworthiness:** No claim is made that designs in this repository are crashworthy, road-safe, or equivalent to certified production vehicles.
- **Legal registration/compliance:** Registration, inspection, emissions, lighting, and safety-equipment requirements vary by country/state/province. Meeting legal requirements does **not** prove crash safety.
- **Builder responsibility:** Any person fabricating or operating a vehicle from this project is responsible for engineering review, weld quality, material verification, testing, and legal compliance.

See `reference/safety/README.md` for additional notes.

## Repository Structure

```text
.
├── docs/
│   ├── adr/                    # Architecture Decision Records
│   └── platforms/              # Platform assumptions and packaging
├── cad/
│   ├── chassis/                # Chassis CAD, node maps, tube tables
│   └── brackets/               # Plate/gusset DXF and related CAD
├── manufacturing/
│   ├── cut-sheets/             # Tube cut lists and plate BOM exports
│   ├── jigs/                   # Table jig references and setup docs
│   └── 3d-printing/            # Body panel print settings/process docs
└── reference/
    └── safety/                 # Safety and regulatory reference docs
```

## Decisions and Proposals

Accepted:

- [ADR-001: Chassis Material and Structural Tubing Specification](docs/adr/ADR-001-chassis-material-and-structural-tubing-specification.md)
- [ADR-002: Chassis Grid and Modular Geometry System](docs/adr/ADR-002-chassis-grid-and-modular-geometry-system.md)

Proposed:

- [ADR-003 (Proposed): Node and Plate System](docs/adr/ADR-003-node-and-plate-system.md)

Platform assumptions:

- [Roadster Platform v0.1 Assumptions](docs/platforms/roadster-v0.1-assumptions.md)

## Contribution Guidelines (Early Stage)

When proposing geometry/material changes:

- Keep fabrication steps practical for hobbyist tooling.
- Prefer straight cuts and repeatable fixtures.
- Clearly separate structural members from non-structural bodywork.
- Include manufacturing implications (cost, lead-time, tolerance stack-up).

## License

See [LICENSE](LICENSE).
