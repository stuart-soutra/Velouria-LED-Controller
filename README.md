# Velouria LED Controller
## Details
The Velouria LED Controller is a 30x20mm programmable, LED controller with battery charging and protection capabilities. 
Please feel free to build and use this board for your own projects.
## Driving NeoPixels
Ideal for driving small strings of NeoPixels, testing has shown that the DC/DC convertor on the board can power up to 12 individual NeoPixels at the same time (5V, 1A max. out of DC/DC Convertor); up to 16 may be achievable.
## MCU
The controller utilises an ATTiny412 MCU that can be programmed via. the UPDI programming header on the back of the board.
One output and one input are accesible via. solder pads on the bottom of the PCB (ideal for having one single input control a string of NeoPixels via. a data output from the MCU).
## Battery Charging/Protection
The battery charging/protection circuit accepts any 3.7V Li-Ion battery.
The controller allows charging from USB Micro B connector only.
The charging circuit outputs a safe charging current of 370mA - after initial testing, it was realised that this is a slow charging rate and will be changed for Rev B.
The battery protection circuit will automatically disconnect the battery from the circuit quickly in the event of over-charging or under-charging.
## New Battery Connection Procedure
If the protection circuit trips when a new battery is connected, please follow the steps below to ensure circuit reset after connection:
 - Connect Battery
 - Short GND to Bat Negative
 - Power cycle charger
## Current Rev (Uploaded)
Rev A
## Mods Required After Rev A Testing
After initial testing, the following mods will need to be implemented in Rev B - PLEASE ADD THESE YOURSELF IF YOU PLAN ON USING THE REV A VERSION:
- Use Diodes Inc. AP9101CK6-BJTRG1 instead of current protection IC - required footprint change
- Remove filter on Vcc at input to battery charger (remove R16 and C5) - short '+5V_FUSED' to 'CHARGE_VCC'
- Change R20 for higher charge current
