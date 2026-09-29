# Bill of Materials

Airframe and flight electronics only. There are no payload provisions.

Links point to AliExpress where a listing exists (Amazon otherwise). Listings change often: if a link is dead, use the search link or the part name. Prices are not listed because they move daily.

Model column: **CAD** = vendor STEP used in the assembly (not redistributed, see the README) · **ENV** = envelope modelled from the datasheet · **OWN** = designed in this project

## Flight electronics

| # | Qty | Part | Role | Key spec / fit | Model | Buy |
|---|-----|------|------|----------------|-------|-----|
| 1 | 1 | Holybro **Kakute H7** (v1.3 or newer) + **Tekko32 F4 4-in-1 50A** stack | Flight controller + 4-in-1 ESC | 30.5 × 30.5 mm, 3–6S, 8-pin JST-SH FC↔ESC cable included | CAD | [AliExpress](https://www.aliexpress.com/i/1005003501904106.html) (choose the H7 + Tekko32 50A option) · [Holybro](https://holybro.com/products/kakute-h7-v1-stacks) |
| 2 | 4 | **Hobbywing XRotor 2807 1300 KV** | Lift / thrust | Ø34 × 20.5 mm, **4 × M3 on a Ø19 mm circle** (the nacelle is drilled for this), M5 shaft. Many other 2807s use a 19 × 19 mm *square*, so check before you buy. | ENV | [AliExpress](https://www.aliexpress.com/item/1005008187282453.html) |
| 3 | 2 + 2 | 7″ tri-blade props, CW + CCW (Gemfan Flash 7040) | Thrust | M5 hub | — | [AliExpress](https://www.aliexpress.us/item/3256802880798263.html) |
| 4 | 1 | HDZero **Freestyle V2** VTX | Digital video TX | 20 × 20 mm, U.FL, MIPI, 6-pin to the FC. Buy the VTX-only option if the listing offers one. | CAD | [AliExpress](https://www.aliexpress.com/item/1005008893507720.html) |
| 5 | 1 | 5.8 GHz U.FL antenna, RHCP (Foxeer Lollipop 4 Plus, U.FL) | Video antenna | Exits the tail on the body axis | CAD | [AliExpress](https://www.aliexpress.com/item/32879131529.html) |
| 6 | 1 | HDZero **Micro V2** camera | FPV camera | 19 mm micro. MIPI cable not included. | CAD | [AliExpress](https://www.aliexpress.com/item/1005002498873004.html) |
| 7 | 1 | HDZero MIPI cable, **250 mm** | Camera → VTX | Modelled route is about 152 mm | OWN (route) | [AliExpress](https://www.aliexpress.com/item/1005004686755457.html) |
| 8 | 1 | U.FL / IPEX 1.13 mm extension, **300 mm** | VTX → tail antenna | Modelled route is about 250 mm | OWN (route) | [AliExpress search](https://www.aliexpress.com/w/wholesale-ufl-extension-cable.html) |
| 9 | 1 | Holybro **Micro M10 GPS** | Position / RTL | 25 × 25 mm, JST-GH 6-pin (UART + I²C compass), mounted in the nose | CAD | [AliExpress](https://www.aliexpress.com/i/1005005742008810.html) |
| 10 | 1 | ExpressLRS 2.4 GHz receiver: **RadioMaster RP1 V2** | RC link | about 11 × 18 × 3 mm, CRSF on UART6 | ENV | [AliExpress](https://www.aliexpress.com/item/1005008159265729.html) |
| 11 | 1 | 6S 2200 mAh LiPo, XT60: **CNHL G+Plus 70C** | Power | 109 × 35 × 51 mm, about 349 g. The tray pocket is 108 mm long today, so trim the front rib 1 mm (a CAD fix is planned). | ENV | [Amazon](https://www.amazon.com/CNHL-2200mAh-Battery-22-2V-Airplane/dp/B0C7ZQ4VMR) · [AliExpress](https://www.aliexpress.com/item/1005005418076286.html) |

## Wiring consumables

| # | Qty | Part | Used for | Buy |
|---|-----|------|----------|-----|
| 12 | 1 | XT60 female pigtail, 12 AWG, about 100 mm | Battery → ESC pads | [AliExpress](https://www.aliexpress.com/item/4001320190567.html) |
| 13 | 1 | Low-ESR capacitor 35 V 470–1000 µF | Across the ESC battery pads | Supplied with the stack |
| 14 | 1 m | 18 AWG silicone wire (3 colours) | Motor lead extensions, about 180 mm × 3 per motor | [AliExpress](https://www.aliexpress.com/item/1005002530970656.html) (choose 18 AWG) |
| 15 | 1 | Heat-shrink assortment (+ 3 mm braided sleeve) | Motor bundles in the wing grooves | [AliExpress](https://www.aliexpress.com/item/4000342725090.html) |
| 16 | — | JST-SH / JST-GH leads | FC ↔ ESC, FC ↔ VTX, FC ↔ GPS | Supplied with the stack, VTX and GPS |
| 17 | 30 cm | 28 AWG silicone wire (4 colours) | FC ↔ receiver | [AliExpress](https://www.aliexpress.com/item/1005002530970656.html) (choose 28 AWG) |

## Printed parts

Print in PETG or ASA; LW-PLA works for the wing panels. STEP files are in [`cad/step`](cad/step).

| # | Qty | File | Notes |
|---|-----|------|-------|
| 18 | 1 | `Body` | Ø100 mm tube, 4 aerofoil root fairings with tab slots, 2 swept canards, tray rails |
| 19 | 1 | `Nose Cone` | Ogive nose with the camera cradle and the GPS mount (screws through the bulkhead) |
| 20 | 4 | `Wing - Top Part` | Leading-edge beam + motor nacelle |
| 21 | 4 | `Wing - Bottom Part` | Wing panel. The 6 × 6 mm motor-lead groove is on the split face. |
| 22 | 4 | `Spike` | Landing leg / nacelle tail cone (TPU is fine) |
| 23 | 1 | `Avionics Tray` | Stack and VTX standoffs, battery pocket, receiver bay |
| — | — | `Arm` | Unsplit master of the wing, for editing only (not printed) |

## Hardware

| # | Qty | Part | Used for | Buy |
|---|-----|------|----------|-----|
| 24 | 16 | M3 × 8 socket screws | Motors → nacelles | [AliExpress screw kit](https://www.aliexpress.com/item/32908695258.html) |
| 25 | 4 | M3 × 20 screws + nylon nuts (or the stack's own bolts) | Stack → tray | same kit |
| 26 | 4 | M2 × 5 screws | VTX → tray | same kit |
| 27 | 4 | M2 × 5 screws | GPS → nose bulkhead | same kit |
| 28 | 2 | M2 × 6 screws | Camera tilt pivot | same kit |
| 29 | 16 | 1.75 mm filament pins, 12 mm long | Wing top ↔ bottom alignment (plus CA or epoxy) | Offcuts of your filament |
| 30 | 1 | Battery strap, 20 mm | Battery retention | [AliExpress](https://www.aliexpress.us/item/3256809035872583.html) |

## Ground equipment (not on the aircraft)

| Item | Recommendation | Why | Buy |
|------|----------------|-----|-----|
| Radio | **RadioMaster Pocket (ELRS)** | Cheap, compact, EdgeTX, internal ELRS that binds to the RP1 | [AliExpress](https://www.aliexpress.com/item/1005009266944405.html) |
| Goggles (best value) | **HDZero BoxPro / BoxPro+** | Native HDZero with built-in DVR, about half the price of Goggle 2 | [AliExpress](https://www.aliexpress.com/item/1005009639730273.html) |
| Goggles (premium) | HDZero Goggle 2 | OLED, lowest latency | [AliExpress](https://www.aliexpress.com/item/1005008069113840.html) |
| Charger | Any 6S-capable balance charger | — | — |
| Ground station | Mission Planner or QGroundControl on a PC | Setup, tuning, logs | free |

**Do you need FPV?** The hover modes (`QSTABILIZE`, `QHOVER`, `QLOITER`) can be flown line-of-sight with just the radio. Forward (wing-borne) flight covers ground fast and is flown through the camera, so plan on goggles plus a spotter where your local rules require one.
