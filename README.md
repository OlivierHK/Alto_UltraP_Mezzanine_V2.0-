# Alto_UltraP_Mezzanine_V2.0
Updated Mezzanine card V2.0 for Alto_UltraP Board.
Fitting Xilinx Ultrascale+ VU9p/VU13p, FLGA2104 Package. 

## Log
- Full compatible with V1.0 Mezzanine, and V1.0 Backplane.
- x2 64-Pins Connan connectors added for better current distribution, and increase signals pins.
- Mini-DIP Switch added to change TPS's PM bus address.
- PCIE extended to x8. Aurora extended x4.
- SPI interface added for direct backboard Arduino controller FPGA bitstream writing.
- Sysmon read ADC VauxP/N added for MGTAVCC, MGTVCCAUX, MGTAVTT. 
- Mechanical holes added for watercooling block on FPGA and VRM.
- C-cap for CSD updated to X7R for better thermal resistance and void space increased to install wider cooler plate. 
- Soldermask's color changed to Blue. Logo and information added on Silkscreen.


## Functionnal Diagram

The schematic's comment should cover all the specifications of the Board. With the functionnal Diagram:
![Functionnal diagram](https://github.com/user-attachments/assets/de3472aa-66f2-4ac5-90fc-c60a2c354b5f)

For the detailed Specification document, please contact the Author at  [olivier.faurie.hk@gmail.com](olivier.faurie.hk@gmail.com).

## Connectors Pinout

### Top connectors (power):
![Power_Connectors_pinout](https://github.com/user-attachments/assets/4e53e351-56f5-4b88-be38-f49f8134b5ce)


### Bottom connectors (Signals & Hi-SPeed interface):
![Signals_Connectors_pinout](https://github.com/user-attachments/assets/aba93dd3-d2cf-459c-aa6f-54e08342bde9)

### Debug port (not populated):
Directly connected to FPGA, on +1.8V bank:
```
J1

  Pin1  - Q0
  Pin2  - Q1
  Pin3  - Q2
  Pin4  - Q3
  Pin5  - Q4
  Pin6  - Q5
  Pin7  - Q6
  Pin8  - Q7
  Pin9  - +1.8V
  Pin10 - GND
```

## LEDs Block
+3.3V LEDs driven directly by FPGA's IOs on +1.8V Bank, via a Mosfet. Active-Low.
```
  D44 - Debug_LED0 (TP56).
  D54 - Debug_LED1 (TP57).
  D46 - Debug_LED2 (TP58).
  D47 - Debug_LED3 (TP59).
  D48 - Debug_LED4 (TP67).
  D49 - Debug_LED5 (TP68).
  D50 - Debug_LED6 (TP69).
  D51 - Debug_LED7 (TP70).
```
## Firmwares

Firmwares installation/update can only be done if mezzanine plugged on an Alto system BackPlane. Procedure can be find on the AltoP platform Firmwares' [Folder](https://github.com/OlivierHK/Alto_UltraP_Board_V1.0/tree/main/Firmwares). There is two:

- Power Controller TPS53681 6+2 Phases for the VCCINT, VCCIO_BRAM of the FPGA:
  - Via PMBUS and TI PMBUS dongle plugged to the backplane.
  - Via PMBUS and Arduino, using [AltoP_SysCtrlMon](https://github.com/OlivierHK/AltoP_SysCtrlMon) tool. 
- FPGA Bitstream:
  - Via AMD JTAG Programing Dongle plugged on the JTAG port of the BackPlane for flashing FPGA or writing QSPI FLash memory
  - Via USB cable and embedded JTAG programming cable for flashing FPGA or writing QSPI FLash memory.
  - New interface (to be implemented on the backplane V2.0) to write the QSPI Flash memory via the Arduino.

## Delivery

The board has been valided already and working full time since Early 2025:
![Mezzanine_V2 0](https://github.com/user-attachments/assets/6f760b17-e291-44ea-aef2-f8fb70d67586)

## Design Files

Gerber Files and BOM available in the [PCB](https://github.com/OlivierHK/Alto_UltraP_Mezzanine_V2.0/tree/main/PCB) folder.

For Kicad Project files, Please contact [olivier.faurie.hk@gmail.com](olivier.faurie.hk@gmail.com).
