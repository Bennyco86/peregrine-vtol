# Bill of Materials

Airframe and flight electronics only. There are no payload provisions.

Links point to AliExpress where a listing exists (Amazon otherwise). Listings change often: if a link is dead, use the search link or the part name.

**Prices** are estimates in **NZD**, taken from typical AliExpress and retailer listings in September 2026 at 1 USD ≈ 1.75 NZD. They exclude shipping; overseas orders to NZ also add 15 % GST at checkout. Treat them as a budget, not a quote.

## Cost summary

| Group | NZD (est.) |
|---|---|
| Flight electronics (#1–11a) | $918 |
| Wiring consumables (#12–17) | $39 |
| Filament (ASA, 1 kg spool) | $44 |
| Hardware and carbon reinforcement (#24–30) | $35 |
| **Aircraft total** | **≈ $1,036** |
| Spare battery (strongly recommended) | $53 |
| Ground: radio + HDZero BoxPro+ goggles + charger | $841 |
| **Total to fly, with nothing already owned** | **≈ $1,930** |

If you already own a radio, goggles and a charger, the aircraft alone is about **NZ$1,040**.

Model column: **CAD** = vendor STEP used in the assembly (not redistributed, see the README) · **ENV** = envelope modelled from the datasheet · **OWN** = designed in this project

## Flight electronics

| # | Qty | Part | Role | Key spec / fit | Model | NZD (est.) | Buy |
|---|-----|------|------|----------------|-------|-----|-----|
| 1 | 1 | Holybro **Kakute H7** (v1.3 or newer) + **Tekko32 F4 4-in-1 50A** stack | Flight controller + 4-in-1 ESC | 30.5 × 30.5 mm, 3–6S, 8-pin JST-SH FC↔ESC cable included | CAD | $236 | [AliExpress](https://www.aliexpress.com/i/1005003501904106.html) (choose the H7 + Tekko32 50A option) · [Holybro](https://holybro.com/products/kakute-h7-v1-stacks) |
| 2 | 4 | **Hobbywing XRotor 2807 1300 KV** | Lift / thrust | Ø34 × 20.5 mm, **4 × M3 on a Ø19 mm circle** (the nacelle is drilled for this), M5 shaft. Many other 2807s use a 19 × 19 mm *square*, so check before you buy. | ENV | $140 (4 × $35) | [AliExpress](https://www.aliexpress.com/item/1005008187282453.html) |
| 3 | 2 + 2 (+ spares) | 7″ tri-blade **high-pitch** props, CW + CCW: **Gemfan Hurricane 7050** (7×5) | Thrust. Pitch sets top speed: 7×4 tops out around 120–130 km/h, 7×5 gives about 183 km/h of pitch speed and 7×6 about 220 km/h | M5 hub. Start with 7050s for hover tuning, then try 7×6 for the 200 km/h runs | — | $21 (2 packs) | [AliExpress search](https://www.aliexpress.com/w/wholesale-gemfan-7050-hurricane.html) · [RaceDayQuads](https://www.racedayquads.com/products/gemfan-hurricane-7050-durable-tri-blade-7-prop-4-pack-choose-your-color) |
| 4 | 1 | HDZero **Freestyle V2** VTX | Digital video TX | 20 × 20 mm, U.FL, MIPI, 6-pin to the FC. Buy the VTX-only option if the listing offers one. | CAD | $193 | [AliExpress](https://www.aliexpress.com/item/1005008893507720.html) |
| 5 | 1 | 5.8 GHz U.FL antenna, RHCP (Foxeer Lollipop 4 Plus, U.FL) | Video antenna | Exits the tail on the body axis | CAD | $18 (2-pack) | [AliExpress](https://www.aliexpress.com/item/32879131529.html) |
| 6 | 1 | HDZero **Micro V2** camera | FPV camera | 19 mm micro. MIPI cable not included. | CAD | $88 | [AliExpress](https://www.aliexpress.com/item/1005002498873004.html) |
| 7 | 1 | HDZero MIPI cable, **250 mm** | Camera → VTX | Modelled route is about 152 mm | OWN (route) | $11 | [AliExpress](https://www.aliexpress.com/item/1005004686755457.html) |
| 8 | 1 | U.FL / IPEX 1.13 mm extension, **300 mm** | VTX → tail antenna | Modelled route is about 250 mm | OWN (route) | $5 | [AliExpress search](https://www.aliexpress.com/w/wholesale-ufl-extension-cable.html) |
| 9 | 1 | Holybro **Micro M10 GPS** | Position / RTL | 25 × 25 mm, JST-GH 6-pin (UART + I²C compass), mounted in the nose | CAD | $49 | [AliExpress](https://www.aliexpress.com/i/1005005742008810.html) |
| 10 | 1 | ExpressLRS 2.4 GHz receiver: **RadioMaster RP1 V2** | RC link | about 11 × 18 × 3 mm, CRSF on UART6 | ENV | $30 | [AliExpress](https://www.aliexpress.com/item/1005008159265729.html) |
| 11 | 1 | 6S 2200 mAh LiPo, XT60: **CNHL G+Plus 70C** | Power. Expect only 2–3 min at full speed | 109 × 35 × 51 mm, about 349 g. The tray pocket is 111 mm long. | ENV | $53 | [Amazon](https://www.amazon.com/CNHL-2200mAh-Battery-22-2V-Airplane/dp/B0C7ZQ4VMR) · [AliExpress](https://www.aliexpress.com/item/1005005418076286.html) |
| 11a | 1 | **Matek ASPD-4525** digital airspeed sensor (MS4525DO, I²C, comes with pitot + tubing) | Real airspeed for gain scaling, speed limits and the OSD. Strongly recommended for high-speed flight | Pitot must sit in clean air ahead of the canards (see WIRING.md) | — | $74 | [AliExpress](https://www.aliexpress.com/item/4000183343004.html) |
| | | | | | | **$918** | |

## Wiring consumables

| # | Qty | Part | Used for | NZD (est.) | Buy |
|---|-----|------|----------|-----|-----|
| 12 | 1 | XT60 female pigtail, 12 AWG, about 100 mm | Battery → ESC pads | $5 | [AliExpress](https://www.aliexpress.com/item/4001320190567.html) |
| 13 | 1 | Low-ESR capacitor 35 V 470–1000 µF | Across the ESC battery pads | incl. | Supplied with the stack |
| 14 | 1 m | 18 AWG silicone wire (3 colours) | Motor lead extensions, about 180 mm × 3 per motor | $18 | [AliExpress](https://www.aliexpress.com/item/1005002530970656.html) (choose 18 AWG) |
| 15 | 1 | Heat-shrink assortment (+ 3 mm braided sleeve) | Motor bundles in the wing grooves | $9 | [AliExpress](https://www.aliexpress.com/item/4000342725090.html) |
| 16 | — | JST-SH / JST-GH leads | FC ↔ ESC, FC ↔ VTX, FC ↔ GPS | incl. | Supplied with the stack, VTX and GPS |
| 17 | 30 cm | 28 AWG silicone wire (4 colours) | FC ↔ receiver | $7 | [AliExpress](https://www.aliexpress.com/item/1005002530970656.html) (choose 28 AWG) |
| | | | | **$39** | |

## Printed parts

For 200 km/h, print the wings and canards in **ASA or carbon-fibre nylon (PA-CF)** with 4+ walls. PETG flexes and LW-PLA is too soft at this speed. STEP files are in [`cad/step`](cad/step).

| # | Qty | File | Notes |
|---|-----|------|-------|
| 18 | 1 | `Body` | Ø100 mm tube, 4 aerofoil root fairings with tab slots, 2 swept canards (each with a Ø2.1 mm rod channel), tray rails |
| 19 | 1 | `Nose Cone` | Ogive nose with the camera cradle and the GPS mount (screws through the bulkhead) |
| 20 | 4 | `Wing - Top Part` | Leading-edge beam + motor nacelle |
| 21 | 4 | `Wing - Bottom Part` | Wing panel. The 6 × 6 mm motor-lead groove is on the split face; a Ø6.2 mm spar channel runs 101 mm from the root at 45 % chord. |
| 22 | 4 | `Spike` | Landing leg / nacelle tail cone (TPU is fine) |
| 23 | 1 | `Avionics Tray` | Stack and VTX standoffs, battery pocket, receiver bay |
| — | — | `Arm` | Unsplit master of the wing, for editing only (not printed) |

**Filament:** about 450 g in total. Budget one 1 kg spool of ASA (about NZ$44), or about NZ$80 if you print the wings and canards in PA-CF.

## Hardware

| # | Qty | Part | Used for | NZD (est.) | Buy |
|---|-----|------|----------|-----|-----|
| 24 | 16 | M3 × 8 socket screws | Motors → nacelles | $12 (kit) | [AliExpress screw kit](https://www.aliexpress.com/item/32908695258.html) |
| 25 | 4 | M3 × 20 screws + nylon nuts (or the stack's own bolts) | Stack → tray | in kit | same kit |
| 26 | 4 | M2 × 5 screws | VTX → tray | in kit | same kit |
| 27 | 4 | M2 × 5 screws | GPS → nose bulkhead | in kit | same kit |
| 28 | 2 | M2 × 6 screws | Camera tilt pivot | in kit | same kit |
| 29a | 4 | **Carbon tube 6 mm OD × 100 mm** (pultruded, e.g. 6 × 4 mm) | Wing spar, one per wing, glued into the channel | $11 | [AliExpress search](https://www.aliexpress.com/w/wholesale-carbon-fiber-tube-6mm.html) |
| 29b | 2 | **Carbon rod 2 mm × 40 mm** | Canard stiffener, pushed in from inside the body and glued | $5 | [AliExpress search](https://www.aliexpress.com/w/wholesale-carbon-fiber-rod-2mm.html) |
| 29 | 16 | 1.75 mm filament pins, 12 mm long | Wing top ↔ bottom alignment (plus CA or epoxy) | incl. | Offcuts of your filament |
| 30 | 1 | Battery strap, 20 mm | Battery retention | $7 | [AliExpress](https://www.aliexpress.us/item/3256809035872583.html) |
| | | | | **$35** | |

## Ground equipment (not on the aircraft)

| Item | Recommendation | Why | NZD (est.) | Buy |
|------|----------------|-----|-----|-----|
| Radio | **RadioMaster Pocket (ELRS)** | Cheap, compact, EdgeTX, internal ELRS that binds to the RP1 | $123 | [AliExpress](https://www.aliexpress.com/item/1005009266944405.html) |
| Goggles (best value) | **HDZero BoxPro / BoxPro+** | Native HDZero with built-in DVR, about half the price of Goggle 2 | $613 | [AliExpress](https://www.aliexpress.com/item/1005009639730273.html) |
| Goggles (premium) | HDZero Goggle 2 | OLED, lowest latency | $1,136 | [AliExpress](https://www.aliexpress.com/item/1005008069113840.html) |
| Charger | Any 6S-capable AC/DC balance charger (e.g. ToolkitRC / ISDT class) | Charges the 6S packs | about $105 | — |
| Ground station | Mission Planner or QGroundControl on a PC | Setup, tuning, logs | free | — |

**Do you need FPV?** The hover modes (`QSTABILIZE`, `QHOVER`, `QLOITER`) can be flown line-of-sight with just the radio. Forward (wing-borne) flight covers ground fast and is flown through the camera, so plan on goggles plus a spotter where your local rules require one.
