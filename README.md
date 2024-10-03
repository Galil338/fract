# Fract Keyboard

Fract is a 40 key (4x10) ortholinear keyboard, powered by a bluetooth-enabled Pro Micro compatible dev board.

It uses Choc v1 keyswitches with 18mm x 17mm spacing.

The goal of this design was to use the manufacturer minimum order of five PCBs to build a single sturdy and pocketable keyboard.

## Project structure

* [`gerbers`](gerbers): Gerber files for PCB manufacturing
* [`graphics`](graphics): Source assets for PCB silkscreen
* [`kicad`](kicad): KiCad project files (schematics and PCB designs)
* [`kicad-libraries`](kicad-libraries): KiCad components and footprints
* [`images`](images): Images for project documentation

## PCB

Five copies of the same PCB are used to encase the dev board, battery, and components.

A dremel or other cutting tool is used to cut away sections of the inner layer of the PCB, in order to encase the dev board, battery connector, and battery between layers of PCB.

## Keyboard firmware

* ZMK
    * Fract shield definition is in [skarrmann's zmk-config](https://github.com/skarrmann/zmk-config)

## Bill of materials

For PCBs, keyswitches, and keycaps, get parts depending on your desired keyswitch type.

Part | Purpose | Quantity | Notes
---- | ------- | -------- | ---------
Main PCB  | circuit board | 5 | Send Gerber zip files to [JLCPCB](https://jlcpcb.com/).
Bluetooth Pro Micro | Microcontroller board | 1 | nice!nano or SuperMini nRF52840
303450 LiPo Battery | Powers the wireless keyboard | Get one with JST PH 2.0 connector
[S2B-PH-K-S](https://www.digikey.com/en/products/detail/jst-sales-america-inc/S2B-PH-K-S/926626) | JST PH 2.0 battery connector | 1 |
[EG1218 slide switch](https://www.digikey.com/en/products/detail/e-switch/eg1218/101726) | On/Off switch | 1 |
[PTS636 SL50 tactile button](https://www.digikey.com/en/products/detail/c-k/PTS636-SL50-LFS/10071718) | Reset button | 1 |
1N4148 SOD-123 | Diodes for keyboard row-column matrix | 52 |
Choc v1 Keyswitches |  | 52 |
Choc v1 Keycaps |  | 52 | Use keycaps which fit 18mm x 17mm spacing
M2 12mm screws | Screw all five PCBs together | 5 |
M2 nuts | Hold the screws in place | 8 |
2mm tall rubber bumpons | Raise board above desk surface and provide skid resitance | 6 |
[Peel-a-way Sockets and Pins](https://ringerkeys.com/collections/modders-tools/products/peel-a-way-sockets) | socket dev board to PCB | 2 strips of 12 pins/sockets | May use other solution which sockets in under 4.8mm clearance.

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
* **Remove Order Number**: Specify a location

**IMPORTANT:** PCB has ["JLCJLCJLCJLC" silkscreen text](https://support.jlcpcb.com/article/28-how-to-remove-order-number-from-your-pcb) underneath the Pro Micro footprint. If you want to remove the order number from the boards or you want to print the PCBs with another manufacturer, then I recommend removing this silkscreen text from the `.kicad_pcb` file, and then re-run the Fract Board Producer plugin to create the updated Gerber files.

## Build tips

**TODO**

## Revision history

**TODO**