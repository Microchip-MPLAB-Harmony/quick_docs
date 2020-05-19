---
title: Getting Started with Drivers on SAM E70/S70/V70/V71 MCUs
parent: Peripheral
has_toc: false
nav_order: 11
---

# Getting Started with Harmony v3 Drivers and System Services on SAM E70/S70/V70/V71 MCUs

This tutorial shows you how to use MHC to create an application that gets you started in developing applications on SAM E70/S70/V70/V71 MCUs using MPLAB Harmony v3 software framework.

The application makes use of [SAM E70 Xplained Ultra Evaluation Kit](https://www.microchip.com/Developmenttools/ProductDetails/DM320113) and [I/O1 Xplained Pro Extension Kit](https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO) (sold separately).

The application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension Kit. The temperature reading is displayed on a serial console periodically every second. Further, the application writes the temperature readings to EEPROM. When a character is entered on the console, the last five written temperature values are read from the EEPROM and displayed on the console. Also, an LED (LED3) is toggled every time the temperature is displayed on the serial console.

The application you create will utilize:

- Two-Wire Interfaces (TWIHS) (I²C) Driver to read the temperature from a temperature sensor and store/retrieve to/from EEPROM.
- Timer System Service to periodically sample temperature sensor data.
- Universal Synchronous Asynchronous Receiver Transmitter (USART) Driver (in Direct Memory Access (DMA) mode) to print the temperature values on a COM (serial) port terminal application running on a PC.
- PORTS Peripheral Library to toggle an LED.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a> 
## Web Links

- [Getting Started with Harmony v3 Drivers and System Services on SAM E70/S70/V70/V71 MCUs](https://microchipdeveloper.com/harmony3:same70-getting-started-training-module-drivers)