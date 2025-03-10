# Getting to Blinky
![Rendering of the pcb](graphics\pcb_render.png)
This project is designed to introduce you to KiCad and electronics design. The gadget is battery powered and will blink a high luminosity LED as well as output a tone to a speaker. The frequency can be switched between 1 Hz and 440Hz with a solder jumper. The two integrated circuits are classics and are considered [jellybean](https://forum.digikey.com/t/what-are-jellybean-electronic-components/46180) parts.

## General design requirements
* Power supplied by [3 x AA batteries](https://www.digikey.no/en/products/detail/keystone-electronics/2464/303813)
* Generate the pulsed signal with a [555 timer](.\datasheets\ne555.pdf) chip
* Boost the battery voltage with the [MC34063](.\datasheets\MC34063A-D.pdf) DC-DC regulator
* Let the 555 timer drive 0.25 Watt into an 8Ω speaker without an additional amplifier
* Use only through hole parts in the design with two small exceptions
* Familiarize the designer with SMD parts of imperial size 0603 and 0805.
* Introduce some of the tools and techniques that are useful in KiCad
* Cut a slot in the PCB to use as strain relief for the speaker cable
* Use a two layer pcb design

## Teaching points in Schematic Editor
* Getting started with a new project i KiCad
* Placing parts and connecting them on the schematic
    * Place
    * Rotate
    * Mirror
    * Move
    * Grab
    * Wire
* Implementing the typical application found in the MC34063 and 555 datasheets
* Choosing component values from [E series of preferred numbers](https://en.wikipedia.org/wiki/E_series_of_preferred_numbers)
* Searching for parts on [DigiKey](https://digikey.com), [JLCPCB](https://jlcpcb.com/parts) and [LCSC](https://www.lcsc.com/)
* Choosing footprints
* Adding symbol data by using *fields* and the *Symbol Fields Table*
* Using the *Do not populate* and *Exclude from Bill Of Materials* (BOM) option
* The purpose of the 0.1µF decoupling capacitor
* Dividing a schematic into functional blocks
* Annotating the schematic
* Running Design Rules Check

## Teaching points in PCB Editor
* Switching from schematic to pcb
* Update PCB from schematic
* Move components into functional blocks
* Untangle the ratsnest
* Draw board outline
* Pre-define sizes for tracks and vias.
    * 0.3mm (0.012") track
    * 0.7mm (0.028") track
    * 1.0mm / 0.4mm via
* Route Tracks
    * Track size
    * Use of vias and multiple layers
* Create filled zones for ground and power
* Use the 3D-viewer
* Use the Design Rules Check


## Suggested Parts list

|Reference|Value|Manufacturer|Part#|DigiKey#|Qty|
|----------|----------|----------|----------|----------|----------|
|BT1|Battery|Keystone Electronics|2464|36-2464-ND|1|
|C1,C2|100u|Chinsan (Elite)|ED1E101MP26311U|4191-ED1E101MP26311UCT-ND|2|
|C3|22u|Murata Electronics|GRM188C61E226ME01J|490-GRM188C61E226ME01JCT-ND|1|
|C4,C7|470u|Chinsan (Elite)|EK1C471MP30812|4191-EK1C471MP30812CT-ND|2|
|C5|1u|TDK Corporation|FG24X7R1H105KRT06|445-173374-1-ND|1|
|C6|0.1u|KEMET|C320C104M5R5TA|399-9776-ND|1|
|Ct1|240p|KEMET|C318C241K3G5TA|C318C241K3G5TA-ND|1|
|D1|1N5819|STMicroelectronics|1N5819|497-6610-1-ND|1|
|D2|Green|Inolux|INL-5AG30|1830-1011-ND|1|
|L1|15u|Bourns Inc.|RLB0913-150K|RLB0913-150K-ND|1|
|R1,R4|180|Stackpole Electronics Inc|CF14JT180R|CF14JT180RCT-ND|2|
|R2|64k9|YAGEO|MFR-25FRF52-64K9|13-MFR-25FRF52-64K9CT-ND|1|
|R3|16k2|YAGEO|MFR-25FTE52-16K2|13-MFR-25FTE52-16K2CT-ND|1|
|R5|1k5|YAGEO|MFR-25FTF52-1K5|13-MFR-25FTF52-1K5CT-ND|1|
|R6|75|Stackpole Electronics Inc|CF14JT75R0|CF14JT75R0CT-ND|1|
|R7|8.06|KOA Speer Electronics, Inc.|RK73H2ATTD8R06F|2019-RK73H2ATTD8R06FCT-ND|1|
|Rsc1|240m|YAGEO|MFR-25JR-52-0R24|13-MFR-25JR-52-0R24CT-ND|1|
|U1|MC34063AP|onsemi|MC34063AP1G|MC34063AP1GOS-ND|1|
|U2|NE555P|Texas Instruments|NE555P|296-NE555P-ND|1|


## Suggested Footprints
|Reference|Footprint|
|--------|-------|
|BT1|Battery:BatteryHolder_TruPower_BH-331P_3xAA|
|C1,C2|Capacitor_THT:CP_Radial_D6.3mm_P2.50mm|
|C3|Capacitor_SMD:C_0603_1608Metric_Pad1.08x0.95mm_HandSolder|
|C4,C7|Capacitor_THT:CP_Radial_D8.0mm_P3.50mm|
|C5|Capacitor_THT:C_Disc_D5.1mm_W3.2mm_P5.00mm|
|C6|Capacitor_THT:C_Disc_D5.0mm_W2.5mm_P2.50mm|
|Ct1|Capacitor_THT:C_Rect_L7.0mm_W3.5mm_P5.00mm|
|D1|Diode_THT:D_DO-41_SOD81_P10.16mm_Horizontal|
|D2|LED_THT:LED_D5.0mm|
|L1|Inductor_THT:L_Radial_D8.7mm_P5.00mm_Fastron_07HCP|
|R1,R2,R3,R4,R5,R6,Rsc1|Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal|
|R7|Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder|
|U1,U2|Package_DIP:DIP-8_W7.62mm|

## Useful tools
* [KiCad](https://www.kicad.org/)
* [LTspice circuit simulator](https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html)
* [Saturn PCB Design Toolkit](https://saturnpcb.com/saturn-pcb-toolkit/)

## Useful webservices
* [jlcpcb.com](https://jlcpcb.com/)
* [digikey.com](https://www.digikey.com)
* [lcsc.com](https://www.lcsc.com/)
* [Falstad circuit simulator](https://www.falstad.com/circuit/circuitjs.html)


## My favorite podcasts
* [The Amp Hour](https://theamphour.com/)
* [Embedded FM](https://embedded.fm/)
* [Hackaday](https://hackaday.com/tag/hackaday-podcast/)
* [The Unnamed Reverse Engineering Podcast](https://unnamedre.com/)