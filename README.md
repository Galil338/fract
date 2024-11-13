# Fract Keyboard

Fract is a 34 key ortholinear keyboard, powered by a bluetooth-enabled Pro Micro compatible dev board.

It uses Choc v1 keyswitches with 18mm x 17mm spacing.

The goal of this design was to build a simple pocketable keyboard out of PCBs.

## Project structure

* [`gerbers`](gerbers): Gerber files for PCB manufacturing
* [`graphics`](graphics): Source assets for PCB silkscreen
* [`kicad`](kicad): KiCad project files (schematics and PCB designs)
* [`kicad-libraries`](kicad-libraries): KiCad components and footprints
* [`images`](images): Images for project documentation

## PCB

Two copies of the main PCB are used to as the logical PCB and a bottom plate. The PCBs are screwed directly together.

Two top plate PCBs cover the dev board and battery.

## Keyboard firmware

* ZMK
    * Fract shield definition is in [skarrmann's zmk-config](https://github.com/skarrmann/zmk-config)

## Bill of materials

Part | Purpose | Quantity | Notes
---- | ------- | -------- | ---------
Main PCB  | logical PCB, bottom plate | 2 | Send Gerber zip files to [JLCPCB](https://jlcpcb.com/)
Top plate PCB  | cover dev board and battery  | 2 | 
Bluetooth Pro Micro | Microcontroller board | 1 | nice!nano or SuperMini nRF52840
502040 LiPo Battery | Powers the wireless keyboard | Get one with JST PH 2.0 connector
S2B-PH-K-S connector | JST PH 2.0 battery connector | 1 |
SS12D00, 5mm handle length | On/Off switch | 1 |
6mm x 6mm push button, 8mm total height | Reset button | 1 |
1N4148 SOD-123 | Diodes for keyboard row-column matrix | 34 |
Choc v1 Keyswitches |  | 34 |
Choc v1 Keycaps |  | 34 | Use keycaps which fit 18mm x 17mm spacing
M2 5mm screws | Screws PCBs together | 19 |
M2 6mm spacers | Spacers between logical PCB and top plates | 8 |
M2 nuts | Holds the top screws between the bottom plate and logical PCB | 3 |
[Peel-a-way Sockets and Pins](https://ringerkeys.com/collections/modders-tools/products/peel-a-way-sockets) | socket dev board to PCB | 2 strips of 12 pins/sockets | May use other low profile sockets which give less than 6 mm total height.

## PCB manufacturing settings

These are the manufacturing settings I used when ordering from JLCPCB:

* **Base Material**: FR4
* **Layers**: 2
* **Dimensions**: (whatever the gerber file specifies)
* **PCB Qty**: 5
* **Different Design**: 1
* **Delivery Format**: Single PCB
* **PCB Thickness**: 1.6
* **PCB Color**: Black
* **Silkscreen**: White
* **Surface Finish**: LeadFree HASL-RoHS
* **Outer Copper Weight**: 1 oz
* **Gold Fingers**: No
* **Confirm Production File**: No
* **Flying Probe Test**: Fully Test
* **Castellated Holes**: No
* **Mark on PCB**: Remove Mark

## Build tips

* Before starting, check if the PCBs are warped, and bend them to be perfectly flat before soldering.
* Solder the diodes first. Make sure they are oriented correctly! Once the keyswitches are soldered in, you won't be able to get to them anymore.
* Make sure the dev board is placed **components side up**. The pinout labels printed on the PCB should align with those printed on the dev board.
* Use tape to hold the battery connector, reset button, and power switch in place. Solder just one leg of each of these components, make sure they are aligned correctly, and then solder the other legs.
* Don't plug in the battery until you're done soldering everything! Use tape to secure the battery and its wires.

## Revision history

* Fract 1.0 (2024-10-16)
    * Initial Choc switch PCB design