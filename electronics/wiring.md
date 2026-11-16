# TruckDeck Lite V0.1   -   Wiring Guide

## Wire colours

- Black = common ground bus.
- Red = individual signal wire from a switch/encoder to the Pro Micro GPIO
- Label every red wire near the Pro Micro with tape or a number. Do not rely on colour alone after installation.

## Basic switch wiring

Every switch is active-low:

```text
Pro Micro GPIO pin ---------- red signal wire ---------- switch button ---------- black wire ---------- Pro Micro GND / another switch GND
```

- When the switch is open, the internal pull-up keeps the pin HIGH.
- When pressed/closed, the pin reads LOW.
- No external resistor is needed.

### ***Do not wire a switch between VCC/RAW and GND. That creates a short when pressed!!!***

## Ground bus

- Connect every switch/button/encoder commmon terminal to the each others ground bus.
- Use any Pro Micro GND pin as the final bus connection.
- Keep the ground bus away from moving parts and screw posts.
- Heat-shrink every solder joint.

## Encode wiring

EC11 bare encoder, ignoring the push-switch contacts:

```text
EC11 A ---------- red signal wire ---------- Pro Micro D7 or D9
EC11 B ---------- red signal wire ---------- Pro Micro D8 or D10
EC11 COM ---------- black wire ---------- Pro Micro GND / Other GND
```
- Use the A/B/C encoder contacts, ignore the two switch contacts.
- If unsure which pin is C (COM), use a multimeter.

## Wiring diagram

```text
Ignition MTS-102 ---------- D2
Hazard PBS-33B ---------- D3
Left indicator ---------- D4
Right indicator ---------- D5
Horn big red ---------- D6
Wiper encoder A ---------- D7
Wiper encoder B ---------- D8
Retarder encoder A ---------- D9
Retarder encoder B ---------- D10
High beam MTS-102 ---------- A0
Beacon MTS-102 ---------- A1
Engine brake MTS-102 ---------- A2

Every switch/button other terminal ---------- common black GND bus
Every encoder C/common ---------- common black GND bus
Every encoder A/B ---------- red signal wire to its GPIO

All switches/buttons are between GPIO and GND only.
No switch is connected to VCC or RAW!
```

## USB and strain relief

- Use a known data-capable USB-C cable.
- The Pro Micro is powered only by USB 5V.

## Pre-power inspection

Before plugging in the finished project:

1. Check there is no connection between common GND bus and GPIO pin.
2. Check each switch/button shorts its GPIO pin to GND only when activated.
3. Check no red signal wires touches another red signal wire.
4. Check no wire strand is loose or bridging the Pro Micro pins.
5. Check the Pro Micro USB connector is not being mechanically pulled by the cable.