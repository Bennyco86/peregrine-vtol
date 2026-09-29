# Kārearea: open-source VTOL FPV tail-sitter

![Kārearea, exterior](images/01-exterior-trimetric.png)

**Kārearea** (the New Zealand falcon) is a hobby **VTOL tail-sitter**. It stands on its four wing-tip spikes, takes off and hovers like a quadcopter, then pitches nose-forward and flies on its wings. It uses four motors and no control surfaces.

The shape is inspired by the new Ukrainian interceptor drone, but this is an original design built as an **open-source FPV project**. Every part was modelled from scratch with **Claude Code (Opus 5.5)** driving the CAD (AI-to-CAD).

> **Scope:** airframe and flight electronics only. There are **no payload provisions**, and none should be added. Fly it within your local aviation rules.

## What's in the repo

| Folder / file | Contents |
|---|---|
| [`cad/step/`](cad/step) | STEP files of every part designed here, plus the full assembly without vendor parts |
| [`BOM.md`](BOM.md) | Full bill of materials with purchase links, radio and goggle recommendations |
| [`docs/WIRING.md`](docs/WIRING.md) | Every cable, connector, pad and route |
| [`software/SETUP.md`](software/SETUP.md) | Flashing ArduPilot, calibration, radio, OSD, first flights |
| [`software/ardupilot/`](software/ardupilot) | ArduPlane parameter file for the Kakute H7 (QuadPlane tail-sitter) |
| [`images/`](images) | Renders and CFD (airflow simulation) results |

## Key numbers

| | |
|---|---|
| Layout | Quad tail-sitter, motors at 45° / 135° / 225° / 315°, 190 mm from the axis |
| Length | about 460 mm (tail to nose) |
| Body | Ø100 mm tube, ogive nose, 2 swept canards, 4 aerofoil wings (NACA 00xx) |
| Power | 4 × 2807 1300 KV, 7″ tri-blade props, 6S 2200 mAh |
| Flight controller | Holybro Kakute H7 + Tekko32 F4 50A 4-in-1 |
| Firmware | ArduPilot **ArduPlane** (`Q_TAILSIT_ENABLE = 2`, copter-motor tail-sitter) |
| Video | HDZero Freestyle V2 + Micro V2 camera (digital, MSP OSD) |
| RC | ExpressLRS 2.4 GHz |
| GPS | Holybro Micro M10 in the nose |

## Build notes

- **Split wings.** Each wing is a top part (leading-edge beam + motor nacelle) and a bottom part (panel), split along the seam line. The motor leads lie in a groove on the split face before the halves are pinned and glued, so nothing has to be threaded through a closed wing.
- **Tabbed root.** The wings slide into slots in the body's aerofoil root fairings.
- **Wiring.** All wiring is modelled and colour-coded in the CAD: orange = motors, red = battery, yellow = VTX power/UART, black = video coax, blue = MIPI, cyan = GPS, green = receiver.

![x-ray](images/04-xray-60-trimetric.png)
![wiring, 85% transparent](images/05-xray-85-wiring-front.png)

| Front | Top (hover attitude) |
|---|---|
| ![front](images/02-exterior-front.png) | ![top](images/03-exterior-top-hover.png) |

## CFD (airflow simulation)

External-flow CFD on the outer shape only (internal parts removed), air, 1.35 M cells.

> ⚠️ **300 m/s (Mach 0.87) is a hypothetical shape study.** A 7″ quad cannot fly anywhere near this speed; realistic top speed is roughly 40–60 m/s. The plot shows where the shape builds shocks and wake, not a performance claim. Colours *inside* the body tube are not meaningful, because air enters through the camera opening in the model.

| Mach number | Velocity | Pressure |
|---|---|---|
| ![mach](images/cfd-300ms-mach-midplane.png) | ![velocity](images/cfd-300ms-velocity-midplane.png) | ![pressure](images/cfd-300ms-pressure-midplane.png) |

## Vendor CAD (not included)

The assembly uses vendor models that are **not redistributed** here: HDZero CAD is CC BY-NC, and Holybro's terms are unknown. Download them yourself if you want the complete assembly:

- Holybro Kakute H7 / Tekko32 stack and Micro M10 GPS: [holybro.com](https://holybro.com) (product pages → downloads)
- HDZero Freestyle V2 VTX, antenna and Micro V2 camera: [docs.hd-zero.com](https://docs.hd-zero.com/freestyle-v2)

The assembly STEP in `cad/step/` already leaves them out.

## Status

- ✅ CAD complete, interference-checked, all wiring connected
- ✅ ArduPilot parameters written (names checked against the ArduPilot docs, **not yet flight-tested**)
- ⏳ First build and hover test
- ⏳ Flow trajectories at realistic speed (25–50 m/s)

## Licence

- Hardware (CAD, drawings, images, docs): **CC BY-SA 4.0**
- Software / configuration (parameter files): **GPL-3.0**, matching ArduPilot

See [`LICENSE`](LICENSE).
