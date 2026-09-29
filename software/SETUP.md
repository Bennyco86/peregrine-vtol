# Software setup

Every piece of software here is open source or free, and none of it is written for this airframe. The only project-specific file is the ArduPilot parameter file.

| Layer | Software | Licence | What it does here |
|-------|----------|---------|-------------------|
| Flight controller firmware | [ArduPilot **ArduPlane**](https://ardupilot.org/plane/), target `KakuteH7` | GPLv3 | Motor-only tail-sitter: hovers like a quad, transitions nose-forward like a plane |
| Ground control | [Mission Planner](https://ardupilot.org/planner/) or [QGroundControl](https://qgroundcontrol.com/) | GPLv3 / Apache-2.0 | Flashing, parameters, calibration, motor test, logs |
| ESC firmware | BLHeli_32 or AM32 (factory on the Tekko32) | AM32 is GPLv3 | DShot600 + telemetry, no changes needed |
| Radio link | [ExpressLRS](https://www.expresslrs.org/) + [EdgeTX](https://edgetx.org/) on the transmitter | GPLv3 | CRSF RC link and telemetry |
| Video | HDZero firmware (VTX + goggles) | vendor | Digital video, MSP DisplayPort OSD |

## 1. Flash the flight controller

1. Hold the Kakute H7 boot button, plug in USB-C, and flash **ArduPlane stable** for board `KakuteH7`. Use Mission Planner (*Install Firmware*) or the ArduPilot firmware server.
2. Connect, set `Q_ENABLE = 1`, write, then **reboot**.
3. Load `ardupilot/karearea-kakuteh7.param` (*Config → Full Parameter List → Load from file*), write, then reboot again.

## 2. Orientation and calibration: do these in the FIXED-WING attitude

ArduPilot treats forward flight as the "normal" attitude for a tail-sitter. Lay the aircraft nose-forward with the canards level for all of these:

- `AHRS_ORIENTATION`: the stack lies in the body's XY plane with the component side facing the canopy (+Z). If the FC arrow points at the nose, leave it at `0`. Otherwise pick the matching yaw rotation.
- Accelerometer calibration (6-position), then *Level*.
- Compass calibration, with the battery fitted and the GPS screwed into the nose.

## 3. Motors (props OFF)

- Motor order and spin direction follow ArduPilot's **Quad X** diagram for `Q_FRAME_TYPE = 1`, drawn in the hover attitude. Check each motor with *Motor Test* and swap the motor leads or `SERVOx_FUNCTION` until they match.
- Reverse a motor with the ESC tool (BLHeli_32 Suite / AM32 configurator via passthrough), not by rewiring the stack.

## 4. Radio (ExpressLRS)

- Flash the RX and TX with the same ELRS major version and binding phrase (ExpressLRS Configurator).
- RX wiring: RX-TX → **R6**, RX-RX → **T6**, 5 V, GND. `SERIAL6_PROTOCOL = 23` is already in the param file.
- Map modes to a 6-position switch: `QSTABILIZE`, `QHOVER`, `QLOITER`, `FBWA`, `QRTL`, plus a separate arm switch.

## 5. Video and OSD (HDZero)

- The VTX plugs into the FC's HD/VTX port (9 V + GND + UART). The param file assumes **UART1**. Check your board's silkscreen and move the `SERIAL1_*` lines if your connector is on another UART.
- `OSD_TYPE = 5`, `SERIALx_PROTOCOL = 42`, `OSD1_TXT_RES = 1` (HD). HDZero garbles text at resolution `2`.

## 6. First flights

1. Bench: props off, arm in `QSTABILIZE`, check every control input moves the right motors.
2. Tethered or low hover in `QSTABILIZE`, then run QuadPlane autotune (`QAUTOTUNE`) in hover.
3. `QLOITER` once GPS and the compass are healthy.
4. Only after a stable hover: transition at 30 m+ in `FBWA`, with a quick switch back to `QHOVER`.

5. **Going fast (target 200 km/h / 56 m/s):** fit the airspeed sensor and calibrate it before trusting it (`ARSPD_USE = 1` only after the HUD reads sensibly). Recompute `Q_TAILSIT_DSKLD` from your real all-up weight. Raise speed in steps (25 → 35 → 45 → 56 m/s). If it oscillates at speed, lower `Q_TAILSIT_GSCMIN`. Swap 7×5 props for 7×6 only once hover and transitions are solid.

Always follow your local aviation rules (registration, line-of-sight/FPV spotter rules, no-fly zones).
