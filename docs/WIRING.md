# Wiring

Every cable in the CAD assembly is modelled end to end, from a real pad or connector to a real pad or connector. The harness parts are colour-coded in the model and in the renders:

| # | Link | Colour in CAD | From → To | Connector / pads | Route |
|---|------|---------------|-----------|------------------|-------|
| 1 | FC ↔ ESC | (inside the stack) | Kakute H7 ↔ Tekko32 4-in-1 | 8-pin JST-SH, supplied with the stack | Straight down between the stacked boards (30.5 mm pattern). It carries motor signals, current sense and ESC telemetry (UART7 → `SERIAL7_PROTOCOL = 16`). |
| 2 | Motor leads ×4 | Orange | ESC motor pads → motors | 3 × 18 AWG per motor, soldered | The front and rear pad rows each feed two motors. The leads bundle beside the stack, rise into the root fairing, run through the **6 × 6 mm groove on the split face of `Wing - Bottom Part`**, then up the nacelle slot to the motor base. |
| 3 | Battery lead | Red | ESC battery pads → XT60 | 12 AWG pigtail + XT60 pair | Short riser from the pads to an XT60 lying across the tray. The battery's own XT60 plugs in from the rear. Solder the low-ESR capacitor across the battery pads. |
| 4 | VTX power + UART | Yellow | FC HD/VTX port → HDZero VTX | 6-pin JST-SH both ends (9 V, GND, UART1 TX/RX) | Runs along the tray to the VTX at the front of the bay. `SERIAL1_PROTOCOL = 42` (MSP DisplayPort OSD). |
| 5 | Video antenna coax | Black | VTX U.FL → tail antenna | U.FL, 1.13 mm coax (300 mm extension) | Runs aft under the tray to the tail and leaves on the body axis through the Ø3.6 mm hole (Ø5.8 × 2 mm counterbore for the ferrule). |
| 6 | Camera MIPI | Blue | VTX MIPI port → HDZero Micro V2 | HDZero MIPI ribbon, 250 mm | About 152 mm of route plus slack, forward into the nose cradle. Keep it away from the motor leads. |
| 7 | GPS | Cyan | Micro M10 (nose) → FC pads | JST-GH 6-pin at the GPS, soldered at the FC: 5 V, GND, TX3, RX3, SCL, SDA | The GPS sits in the nose cone above the camera, screwed through the bulkhead. The cable runs aft along the canopy side. `SERIAL3_PROTOCOL = 5`, `GPS_TYPE = 2`. |
| 8 | ELRS receiver | Green | RX (beside the battery, −X side) → FC UART6 pads | 4 × 28 AWG: 5 V, GND, RX-TX → **R6**, RX-RX → **T6** | Short run forward to the stack. The 2.4 GHz T-antenna lies along the body axis on the bottom skin, away from the video antenna. `SERIAL6_PROTOCOL = 23`, `RSSI_TYPE = 3`. |
| 9 | Airspeed sensor | (not in CAD yet) | Matek ASPD-4525 → FC I²C pads | JST-GH 4-pin: 5 V, GND, SCL, SDA (shared with the GPS compass bus) | Mount the board inside the nose bay. Run the silicone tubes to a pitot tube that pokes forward through a canard leading edge or the nose-to-body joint, **out of the prop wash and at least 20 mm ahead of the local surface**. `ARSPD_TYPE = 1`. |

## Notes

- **Wing split.** Each wing is printed as a top part (leading-edge beam + motor mount) and a bottom part (panel). Lay the motor leads in the bottom part's groove, then close the wing on 4 filament pins (Ø1.75 mm) with CA or epoxy. The leads never have to be pulled through a closed tube.
- **Motor direction.** Swap any two motor wires, or better, reverse the motor in BLHeli_32 / AM32. The motor order follows ArduPilot Quad X in the hover attitude (see [`software/SETUP.md`](../software/SETUP.md)).
- **RF separation.** The 5.8 GHz video antenna exits the tail and the 2.4 GHz RX antenna lies on the bottom skin, so neither antenna shadows the other in hover (nose up) or in forward flight.
- **Checks before the first power-up.** Beep out the battery pads for shorts, check the XT60 polarity, and power the stack from a smoke stopper the first time.
