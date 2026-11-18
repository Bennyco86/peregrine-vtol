# Bill of Materials

Airframe and flight electronics only. There are no payload provisions.

Where available, links point to manufacturer or retailer references checked on 30 Sep 2026. These references are for the prototype and do not establish manufacturing origin or supplier approval.

**Prices** are estimates in **NZD**, taken from typical AliExpress and retailer listings in September 2026 at 1 USD ≈ 1.75 NZD. They exclude shipping; overseas orders to NZ also add 15 % GST at checkout. Treat them as a budget, not a quote.

## Cost summary

| Group | NZD (est.) |
|---|---|
| Flight electronics (#1–11a) | $957 |
| Wiring consumables (#12–17) | $39 |
| Filament (ASA, 1 kg spool) | $44 |
| Hardware (#24–30) | $19 |
| **Aircraft total** | **≈ $1,059** |
| Spare battery (strongly recommended) | $53 |
| Ground: radio + HDZero BoxPro goggles + charger | $840 |
| **Total to fly, with nothing already owned** | **≈ $1,952** |

If you already own a radio, goggles and a charger, the aircraft alone is about **NZ$1,060**.

Model column: **CAD** = vendor STEP used in the assembly (not redistributed, see the README) · **ENV** = envelope modelled from the datasheet · **OWN** = designed in this project

## Flight electronics

| # | Qty | Part | Role | Key spec / fit | Model | NZD (est.) | Buy |
|---|-----|------|------|----------------|-------|-----|-----|
| 1 | 1 | Holybro **Kakute H7** (v1.3 or newer) + **Tekko32 F4 4-in-1 50A** stack | Flight controller + 4-in-1 ESC | 30.5 × 30.5 mm, 3–6S, 8-pin JST-SH FC↔ESC cable included | CAD | $236 | [Holybro (official)](https://holybro.com/products/kakute-h7-v1-stacks) |
| 2 | 4 | **Hobbywing XRotor 2807 1300 KV** | Lift / thrust | Ø34 × 20.5 mm, **4 × M3 on a Ø19 mm circle** (the nacelle is drilled for this), M5 shaft. Many other 2807s use a 19 × 19 mm *square*, so check before you buy. | ENV | $140 (4 × $35) | [Hobbywing (official)](https://www.hobbywingdirect.com/products/xrotor-fpv-2807-motors) |
| 3 | 2 + 2 (+ spares) | 7″ tri-blade **high-pitch** props, CW + CCW: **Gemfan Hurricane 7050** (7×5) | Thrust. Pitch sets top speed: 7×4 tops out around 120–130 km/h, 7×5 gives about 183 km/h of pitch speed and 7×6 about 220 km/h | M5 hub. Start with 7050s for hover tuning, then try 7×6 for the 200 km/h runs | — | $21 (2 packs) | [RaceDayQuads](https://www.racedayquads.com/products/gemfan-hurricane-7050-durable-tri-blade-7-prop-4-pack-choose-your-color) |
| 4 | 1 | HDZero **Freestyle V2** VTX | Digital video TX | 20 × 20 mm, U.FL, MIPI, 6-pin to the FC. Buy the VTX-only option if the listing offers one. | CAD | $201 | [HDZero (official)](https://hdzero.us/products/hdzero-freestyle-v2-vtx) · [Pyrodrone](https://pyrodrone.com/products/hdzero-freestyle-v2-20x20-25-1000mw-hd-vtx-u-fl) |
| 5 | 1 | 5.8 GHz U.FL antenna, RHCP (Foxeer Lollipop 4 Plus, U.FL) | Video antenna | Exits the tail on the body axis | CAD | $18 (2-pack) | [Foxeer (official)](https://www.foxeer.com/foxeer-lollipop-4-plus-high-quality-5-8g-2-6dbi-fpv-omni-lds-antenna-g-374) |
| 6 | 1 | HDZero **Micro V3** camera (replaces the discontinued Micro V2) | FPV camera | Same 19 × 19 mm micro mount as the V2 in the CAD; the V3 body is 24 mm deep, so check the fit in the nose cradle. MIPI cable not included. | CAD | $100 | [HDZero (official)](https://hdzero.us/products/hdzero-micro-v3-camera) |
| 7 | 1 | HDZero MIPI cable, **250 mm** | Camera → VTX | Modelled route is about 152 mm | OWN (route) | $30 | [HDZero (official)](https://hdzero.us/products/hdzero-mipi-cable-250mm) · [Pyrodrone](https://pyrodrone.com/products/hdzero-mipi-cable-250mm) |
| 8 | 1 | U.FL / IPEX 1.13 mm extension, **300 mm** | VTX → tail antenna | Modelled route is about 250 mm | OWN (route) | $5 | — |
| 9 | 1 | Holybro **Micro M10 GPS** | Position / RTL | 25 × 25 mm, JST-GH 6-pin (UART + I²C compass), mounted in the nose | CAD | $49 | [Holybro (official)](https://holybro.com/products/micro-m10-gps) |
| 10 | 1 | ExpressLRS 2.4 GHz receiver: **RadioMaster RP1 V2** | RC link | about 11 × 18 × 3 mm, CRSF on UART6 | ENV | $30 | [RadioMaster (official)](https://radiomasterrc.com/products/rp1-expresslrs-2-4ghz-nano-receiver) |
| 11 | 1 | 6S 2200 mAh LiPo, XT60: **CNHL G+Plus 70C** | Power. Expect only 2–3 min at full speed | 109 × 35 × 51 mm, about 349 g. The tray pocket is 111 mm long. | ENV | $53 | [CNHL (official)](https://chinahobbyline.com/products/cnhl-gplus-series-2200mah-22-2v-6s-70c-lipo-battery-with-xt60-plug) |
| 11a | 1 | **Matek ASPD-4525** digital airspeed sensor (MS4525DO, I²C, comes with pitot + tubing) | Real airspeed for gain scaling, speed limits and the OSD. Strongly recommended for high-speed flight | Pitot must sit in clean air ahead of the canards (see WIRING.md) | — | $74 | [Matek (official)](https://www.mateksys.com/?portfolio=aspd-4525) |
| | | | | | | **$957** | |

## Wiring consumables

| # | Qty | Part | Used for | NZD (est.) | Buy |
|---|-----|------|----------|-----|-----|
| 12 | 1 | XT60 female pigtail, 12 AWG, about 100 mm | Battery → ESC pads | $5 | — |
| 13 | 1 | Low-ESR capacitor 35 V 470–1000 µF | Across the ESC battery pads | incl. | Supplied with the stack |
| 14 | 1 m | 18 AWG silicone wire (3 colours) | Motor lead extensions, about 180 mm × 3 per motor | $18 | — |
| 15 | 1 | Heat-shrink assortment (+ 3 mm braided sleeve) | Motor bundles in the wing grooves | $9 | — |
| 16 | — | JST-SH / JST-GH leads | FC ↔ ESC, FC ↔ VTX, FC ↔ GPS | incl. | Supplied with the stack, VTX and GPS |
| 17 | 30 cm | 28 AWG silicone wire (4 colours) | FC ↔ receiver | $7 | — |
| | | | | **$39** | |

## Printed parts

For 200 km/h, print the wings and canards in **ASA or carbon-fibre nylon (PA-CF)** with 4+ walls. PETG flexes and LW-PLA is too soft at this speed. STEP files are in [`cad/step`](cad/step).

| # | Qty | File | Notes |
|---|-----|------|-------|
| 18 | 1 | `Body Rev 2` | Ø100 mm tube, 4 aerofoil root fairings with tab slots, 2 swept canards, tray rails. **245 mm tall, so it fits 250 mm printers.** Bayonet sockets at both ends. |
| 19 | 1 | `Nose Cone Rev 2` | Ogive nose with the bulkhead, camera cradle and GPS mount, extended down to take the forward tube. **Twist-lock bayonet with a snap onto the body: do not glue**, it is the service hatch. A wide key lug means it fits only one way. It has a threaded collar (2.5 mm pitch) around the camera. |
| 19b | 1 | `Nose Tip Rev 2` | The front of the nose around the camera, with the lens window. **Screws onto the threaded collar** (about 2.5 turns). Unscrew it to fit the camera and reach the pivot and GPS screws. |
| 19a | 1 | `Tail Cap Rev 2` | Tapered tail end with the antenna hole (42 mm tall). Twist-lock bayonet with a snap, **glued** once the wiring is in (glue groove on the ring). |
| 20 | 4 | `Wing - Top Part` | Leading-edge beam + motor nacelle |
| 21 | 4 | `Wing - Bottom Part` | Wing panel. The 6 × 6 mm motor-lead groove is on the split face |
| 22 | 4 | `Spike` | Landing leg / nacelle tail cone (TPU is fine) |
| 23 | 1 | `Avionics Tray` | Stack and VTX standoffs, battery pocket between two ribs, slots for the lower motor-lead bundles |
| — | — | `Arm` | Unsplit master of the wing, for editing only (not printed) |

**Filament:** about 450 g in total. Budget one 1 kg spool of ASA (about NZ$44), or about NZ$80 if you print the wings and canards in PA-CF.

## Hardware

| # | Qty | Part | Used for | NZD (est.) | Buy |
|---|-----|------|----------|-----|-----|
| 24 | 16 | M3 × 8 socket screws | Motors → nacelles | $12 (kit) | — |
| 25 | 4 | M3 × 20 screws + nylon nuts (or the stack's own bolts) | Stack → tray | in kit | same kit |
| 26 | 4 | M2 × 5 screws | VTX → tray | in kit | same kit |
| 27 | 4 | M2 × 5 screws | GPS → nose bulkhead | in kit | same kit |
| 28 | 2 | M2 × 6 screws | Camera tilt pivot | in kit | same kit |
| 29 | 16 | 1.75 mm filament pins, 12 mm long | Wing top ↔ bottom alignment (plus CA or epoxy) | incl. | Offcuts of your filament |
| 30 | 1 | Battery strap, 20 mm | Battery retention | $7 | — |
| | | | | **$19** | |

## Ground equipment (not on the aircraft)

| Item | Recommendation | Why | NZD (est.) | Buy |
|------|----------------|-----|-----|-----|
| Radio | **RadioMaster Pocket (ELRS)** | Cheap, compact, EdgeTX, internal ELRS that binds to the RP1 | $123 | [RadioMaster (official)](https://radiomasterrc.com/products/pocket-radio-controller-m2) |
| Goggles (**best value**) | **HDZero BoxPro** (US$349.99) | The cheapest goggles that receive HDZero natively. 100 Hz 1800-nit LCD, built-in DVR, analog receiver and HDMI in. Less than half the price of Goggle 2. BoxPro+ (US$399.99) only upgrades the optics. | $612 | [HDZero (official)](https://hdzero.us/products/hdzero-boxpro-boxpro) |
| Goggles (premium, not needed) | HDZero Goggle 2 (US$749.99) | OLED and slightly lower latency; about double the BoxPro price for a small gain | $1,312 | [HDZero (official)](https://hdzero.us/products/hdzero-goggle-2) |
| Charger | Any 6S-capable AC/DC balance charger (e.g. ToolkitRC / ISDT class) | Charges the 6S packs | about $105 | — |
| Ground station | Mission Planner or QGroundControl on a PC | Setup, tuning, logs | free | — |

**Do you need FPV?** The hover modes (`QSTABILIZE`, `QHOVER`, `QLOITER`) can be flown line-of-sight with just the radio. Forward (wing-borne) flight covers ground fast and is flown through the camera, so plan on goggles plus a spotter where your local rules require one.
