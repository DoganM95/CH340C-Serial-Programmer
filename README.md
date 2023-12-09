# CH340C-Module

This CH340C-Module is a specialized ESP32 programmer PCB that simplifies the programming process by incorporating auto-programming functionality. This means there's no need for manual interaction with the ESP32 during programming, such as pressing buttons on the board. Additionally, it supports Power Delivery (PD), allowing the attached ESP32 to be powered from a PD source at 5V.

## Visual Overview

<table>
  <tr>
    <td>
      <img src="https://github.com/DoganM95/CH340C-Pcb/assets/38842553/930e5172-5bf8-4496-964e-156199e865cc" alt="PCB Top View"/>
    </td>
    <td>
      <img src="https://github.com/DoganM95/CH340C-Pcb/assets/38842553/0f2f7af0-e23c-419c-b916-a81f3ad52a0a" alt="PCB Bottom View"/>
    </td>
    <td>
      <img src="https://github.com/DoganM95/CH340C-Pcb/assets/38842553/9860365b-ce62-4cc8-a7cd-dd0f03e665b5" alt="PCBWay order raw"/>
    </td>
    <td>
      <img src="https://github.com/DoganM95/CH340C-Pcb/assets/38842553/d23bb2a4-6924-4b47-8242-443eb76528bd" alt="PCBWay order assembled"/>
    </td>
  </tr>
</table>

## Key Features

- **Compact Design**: The module is designed to occupy minimal space, making it ideal for streamlined setups.
- **Power Delivery Support**: Compatible with Power Delivery, enabling the ESP32 to run directly from a 5V PD source.
- **USB-C Connectivity**: Utilizes a USB-C connection for modern, reversible, and reliable connectivity.
- **Auto-Programming**: Simplifies the programming process by eliminating the need for manual button presses on the ESP32 during programming.

## Part List

The following table contains all the parts required for the CH340C-Module, along with their corresponding printed names. The parts are listed in the recommended order of soldering.

| Reference | Part Name               | Description                           |
|-----------|-------------------------|---------------------------------------|
| J1        | CQ-USB-C16PSMT01        | 16 Pin female USB C connector         |
| U2        | CH340C                  | Programming IC                        |
| R1        | 0603-5.1k               | Resistor, 0603 sized, 5.1 kilo Ohm    |
| R2        | 0603-5.1k               | Resistor, 0603 sized, 5.1 kilo Ohm    |
| C1        | 0603-100nF              | Capacitor, 0603 sized, 100 nano Farad |
| C2        | 0603-4.7uF              | Capacitor, 0603 sized, 4.7 micro Farad |
| JP1       | Jumper                  | short: mid (VCC) with left/inner (3V3) or right/outer (5V)|
| U4        | AO3400                  | N-Channel Mosfet                      |
| U3        | AO3400                  | N-Channel Mosfet                      |
| U1        | AMS1117 3.3V            | 5V to 3.3V Voltage regulator          |

## Driver
https://www.wch.cn/download/CH341SER_ZIP.html

## Key Takeaways
- The CH340C can be powered with `3.3V` or `5V`. The input Voltage translates to its TX voltage and 5V is too high for e.g. an esp32, so it gets powered with `3.3V` 
- The `3V` pin of the CH340C needs to be connected to `GND` with a `100nF` capacitor, else it will not work and not show up in device manager
- Connecting it with wrong polarity (`5V` and `GND`) gets the chip hot quickly, but doesn't break it when cutting the power off soon (like 20 seconds)
- The minimum circuit, only to check if a CH340C ic is functional, consists of a usb port with (`5V`, `D-`, `D+`, `GND`) connected to the CH340C as well as the said `100nF` capacitor from its `3V` pin to `GND`
- The capacitor (`C2`) between `EN` and `GND` needs to be high enough, else the auto reset will not work. `100nF` was too little, so the IDE was stuck at `Hard resetting via RTS pin...` and the module had to be plugged out and in again manually. Increasing the capacitance to `4.7nF` solved this and the auto reset works fine with that.

## Sponsorship - [PCBWay](https://pcbway.com/g/8bcMJY)
The physical PCB's and stencil are sponsored by [PCBWay](https://pcbway.com/g/8bcMJY).  
Overall i am very satisfied with the quality of the pcb's, especially with
- the matte surface finish
- the cover of the vias, which almost feel like plugged, so there is no way to accidentally put solder in there to cause a short circuit
- the traces, which are covered better than other manufacturers do and cannot be brushed/scraped away easily. Big plus for that

One thing i missed was clearer texts (white) on the pcb's, but printing those in good quality, especially sized at 0.6mm, can be challenging.  
I am very pleased to get these sponsored by [PCBWay](https://pcbway.com/g/8bcMJY) and can recommend their service, especially for the high quality you get and the huge amount of configurable settings.  

## Video preview
https://github.com/DoganM95/CH340C-Pcb/assets/38842553/810827a4-b2fa-454a-bed7-59ae43e08667
