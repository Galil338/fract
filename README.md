# Fract Keyboard

Fract is a 40 key (4x10) ortholinear keyboard, powered by a bluetooth-enabled Pro Micro compatible dev board.

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
303450 LiPo Battery | Powers the wireless keyboard | Get one with JST PH 2.0 connector
[S2B-PH-K-S](https://www.digikey.com/en/products/detail/jst-sales-america-inc/S2B-PH-K-S/926626) | JST PH 2.0 battery connector | 1 |
SS12D00 5mm handle length | On/Off switch | 1 |
6mm x 6mm push button, 8mm total height | Reset button | 1 |
1N4148 SOD-123 | Diodes for keyboard row-column matrix | 52 |
Choc v1 Keyswitches |  | 34 |
Choc v1 Keycaps |  | 34 | Use keycaps which fit 18mm x 17mm spacing
M2 12mm screws | Screw all five PCBs together | 5 |
M2 nuts | Hold the screws in place | 8 |
2mm tall rubber bumpons | Raise board above desk surface and provide skid resitance | 6 |
[Peel-a-way Sockets and Pins](https://ringerkeys.com/collections/modders-tools/products/peel-a-way-sockets) | socket dev board to PCB | 2 strips of 12 pins/sockets | May use other low profile sockets which give less than ~4.8 mm height.

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
* **Mark on PCD**: Remove Mark

## Build tips

**TODO**

## Revision history

**TODO**