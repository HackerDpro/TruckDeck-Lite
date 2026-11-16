# TruckDeck Lite V0.1

An affordable HID control panel for truck simulator such as **Euro Truck Simulator 2** and **American Truck Simulator**.

**Status:** ***Design*** - preparing for Fabricate design review. No parts have been ordered yet, and no physical build or hardware test has been done.

**Fabricate tier:** ***Tier 4***

**Repository:** ***[TruckDeck-Lite](https://github.com/HackerDpro/TruckDeck-Lite)*** Obviously

**Progress journal:** ***[Journal](JOURNAL.md)***

![TruckDeck Lite top plate](cad/screenshots/Schermafbeelding%202026-11-16%20193200.png)

## What is it?

TruckDeck Lite is a 3D printed, USB-powered control panel for truck simulators. It has controls for common truck simulation functions instead of forcing players to use keyboard shortcuts. It is shown to the PC as a standard HID gamepad, so no special drivers or config is required! The user just needs to map the buttons in the game.

The panel has a removable faceplate, a simple bottom box, a desk stand (print it 2 times!), and a USB hole for connection between the inside-the-box components and the outer world.

## Goals

- Make a useful, affordable truck-sim panel for ETS2/ATS (or other games)
- Learn to work with CAD, electronics, soldering, wiring, HID
- Keep the design repairable and simple enough (for me) to understand.

## Controls and Electronics

View [Pin-Map](electronics/pinmap.md) and [Wiring](electronics/wiring.md)

## Firmware behaviour

View [README-firmware](firmware/README.md)

# CAD (3D printing)

OnShape was used as CAD for this project.

The project has:

- a bottom box with USB-C port cutout
- a top plate with all control cutouts
- a simple desk stand (2x)
- a printed encoder know (2x)

The top plate attaches with M3*10mm screws. The Pro Micro is mounted next to the USB-C opening.

## Dimensions

All cutout dimensions are based on supplier drawings and product-page dimensions. They have not been physically verified because the parts haven't been ordered yet.

## BOM

The BOM can be found at [BOM]()

Current summary:

- Estimated total: Around **€29.75**
- Shipping: Around: **€8.75**, paid separately
- Owned materials as usb-c data cable, M3 screws, ... Are not counted in the Estimated total.

## Build and test plan

1. Test-fit the microcontroller and buttons/switches/encoders
2. Adjust the measures in the CAD if needed
3. Print the final 3D models (With exact measures)
4. Install controls in the top plate
5. Solder the COM's to GND bus
6. Solder the red signal wires and heat shrink the joints
7. Test the Pro Micro as HID before installing it too
8. Test a button and encoder
9. Assamble the panel, and close the top plate
10. Test with `joy.cpl` on Windows and play ETS/ATS for some time
11. Check for problems (stuck inputs, ...)

## SAFETY

- USB *5V* Only. No battery/wireless
- Not connect any switch to VCC/RAW. Only GPIO and GND.

## AI disclosure

I did us AI (deepseek and google AI-mode search) as assistant for learning and planning purposes:

- component researches
- project planning
- draft pin-map, wiring and README document (later edited and reviewed by myself)

I created all the OnShape CAD models myself and I any AI outputs as unverified drafts, I did not do or have written anything I am not aware of. I am responsible for reviewing, editing, and physically testing the design. No hardware has been built or tested yet, but that will be me too.

## Credits

- Arduino Joystick library by Matthew Heironimusa
- OnShape for CAD
- ***Hack Club Fabricate*** for the hardware program and review process
- The truck-sim communities whose feedback will be used for the final layout