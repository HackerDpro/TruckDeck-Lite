# TruckDeck Lite V0.1   -   Firmware Plan

## Board

Pro Micro 5V 16MHz, USB-C.
Arduino IDE:
- Board: SparkFun Pro Micro
- Processor: ATmega32u4 5V, 16MHz
- Library: Joystick by Matthew Heironimus
- Board package: SparkFun AVR Boards

If SparkFun Pro Micro is unavailable in the IDE, Arduino Leonardo can be used as a fallback, but select the correct 5V/16MHz processor.

## USB behaviour

- The panel appears as a standard HID gamepad with 12 buttons and no axes.
- It does not appear as a keyboard.
- It does not type letters into windows.
- No drivers are needed.

Windows test:
- Press Win+R
- Type `joy.cpl`
- Press Enter
- Open the game controller properties
- Verify 12 buttons

## Button behaviour

| Control type | Firmware behaviour |
|---|---|
| Horn | Button held: while physical button is held |
| Hazard | Short pulse: on press |
| Left indicator | Short pulse: on press |
| Right indicator | Short pulse: on press |
| Ignition toggle | Short pulse: whenever the physical toggle changes state |
| High beam toggle | Short pulse: whenever the physical toggle changes state |
| Beacon toggle | Short pulse: whenever the physical toggle changes state |
| Engine brake toggle | Short pulse: whenever the physical toggle changes state |
| Rotary encoders | One short pulse: on the corresponding up/down HID button per detent |

## Fixed HID order

1 = ignition
2 = hazard
3 = left indicator
4 = right indicator
5 = horn
6 = high beam
7 = beacon
8 = engine brake
9 = wipers up
10 = wipers down
11 = retarder up
12 = retarder down