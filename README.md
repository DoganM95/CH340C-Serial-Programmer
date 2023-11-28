# CH340C-Module

This CH340C-Module is a specialized ESP32 programmer PCB that simplifies the programming process by incorporating auto-programming functionality. This means there's no need for manual interaction with the ESP32 during programming, such as pressing buttons on the board. Additionally, it supports Power Delivery (PD), allowing the attached ESP32 to be powered from a PD source at 5V.

## Visual Overview

<table>
  <tr>
    <td>
      <img src="https://github.com/DoganM95/CH340C-Pcb/assets/38842553/90784a38-3567-4cee-b42a-d1d5a5c72e44" alt="PCB Top View" width="100%" />
    </td>
    <td>
      <img src="https://github.com/DoganM95/CH340C-Pcb/assets/38842553/83c0b718-0b2c-4d56-bbd6-e11d8ced7d17" alt="PCB Bottom View" width="100%" />
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
| C2        | 0603-1uF                | Capacitor, 0603 sized, 1 micro Farad  |
| U4        | AO3400                  | N-Channel Mosfet                      |
| U3        | AO3400                  | N-Channel Mosfet                      |
| U1        | AMS1117 3.3V            | 5V to 3.3V Voltage regulator          |

## Key Takeaways
- The CH340C can be powered with 3.3V as well as 5V, but its TX voltage perhaps is too high for e.g. an esp32, so powering it with 3.3V seems fine
- The 3V pin of the CH340C needs to be connected (exclusively) to GND with a 100nF capacitor in between, else it will not work and not show up in windows device manager
- Connecting it with wrong polarity (5V and GND) gets the chip hot quickly, but doesn't break it when cutting the power off soon (like 20 seconds)
