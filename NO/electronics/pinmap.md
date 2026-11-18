# TruckDeck Lite V0.1   -   Pin Map and Button order

Board: Pro Micro 5V 16MHz, USB-C
USB mode: HID gamepad
All switches/buttons are wired between GPIO pins and GND.
All pins use the Pro Micro internal pull-ups.

## HID gamepad buttons

| HID button | Physical control | Pro Micro pin | Behaviour |
| ---: | --- | --- | --- |
| 1 | Ignition toggle | D2 | Pulse: 100ms on state change |
| 2 | Hazard button | D3 | Pulse: 80-100ms on press |
| 3 | Left indicator | D4 | Pulse: 80-100ms on press |
| 4 | Right indicator | D5 | Pulse: 80-100ms on press |
| 5 | Horn | D6 | Held: while pressed |
| 6 | High beam toggle | A0 | Pulse: 100ms on state change |
| 7 | Beacon toggle | A1 | Pulse: 100ms on state change |
| 8 | Engine brake toggle | A2 | Pulse: 100ms on state change |
| 9 | Wipers up | D7 / D8 encoder | One pulse: per detent |
| 10 | Wipers down | D7 / D8 encoder | One pulse: per detent |
| 11 | Retarder up | D9 / D10 encoder | One pulse: per detent |
| 12 | Retarder down | D9 / D10 encoder | One pulse: per detent |

## Physical pin map

| function | Part | Pro Micro connection |
| ---: | --- | --- |
| Ignition toggle | MTS-102, ON-ON | COM to GND, NO to D2 |
| Hazard button | PBS-33B red, momentary | Terminal 1 to GND, terminal 2 to D3 |
| Left indicator | PBS-33B black, momentary | Terminal 1 to GND, terminal 2 to D4 |
| Right indicator | PBS-33B black, momentary | Terminal 1 to GND, terminal 2 to D5 |
| Horn | Big red, momentary | Terminal 1 to GND, terminal 2 to D6 |
| Wiper encoder A | EC11 | A to D7 |
| Wiper encoder B | EC11 | B to D8 |
| Wiper encoder common | EC11 | COM to GND |
| Retarder encoder A | EC11 | A to D9 |
| Retarder encoder B | EC11 | B to D10 |
| Retarder encoder common | EC11 | COM to GND |
| High beam toggle | MTS-102, ON-ON | COM to GND, NO to A0 |
| Beacon toggle | MTS-102, ON-ON | COM to GND, NO to A1 |
| Engine brake toggle | MTS-102, ON-ON | COM to GND, NO to A2 |

## RULES

- Do not connect any switch or encoder to VCC or RAW
- Do not use a button matrix
- Do not change HID button numbers after users map them in-game
- If an encoder turns backwards, swap its A/B wires or just swap the two HID numbers for that encoder. (Do not change the whole panel layout.)
- If an encoder detent sends too many pulses, adjust `ENCODER_STEPS_PER_DETENT` in the firmware.