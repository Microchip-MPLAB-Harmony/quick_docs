---
title: Getting Started with PLIBs on SAM D5x/E5x MCUs
parent: Peripheral
has_toc: false
nav_order: 2
---

# Getting Started with Harmony v3 Peripheral Libraries on SAM D5x/E5x MCUs

This tutorial shows you how to use the MPLAB Harmony Configurator (MHC) to create an application that gets you started in developing applications on SAM D5x/E5x MCUs using MPLAB Harmony v3 software framework.

The application makes use of [SAM E54 Xplained Pro Evaluation Kit](https://www.microchip.com/DevelopmentTools/ProductDetails/ATSAME54-XPRO) and [I/O1 Xplained Pro Extension Kit](https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO) (sold separately).

The application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension. The temperature read is displayed on a serial console periodically every 500 milliseconds. The periodicity of the temperature values displayed on the serial console is changed to 1 second, 2 seconds, 4 seconds and back to 500 milliseconds every time you press the switch SW0 on the SAM E54 Xplained Pro Evaluation Kit. Also, LED0 is toggled every time temperature is displayed on the serial console.

The application you create will utilize:

- SERCOM (as I²C) Peripheral Library (PLIB) to read the temperature from a temperature sensor.
- Real-Time Clock (RTC) PLIB to periodically sample temperature sensor data.
- SERCOM (as USART), Direct Memory Access (DMA) PLIBS to print the temperature values on a COM (serial) port terminal application running on a PC.
PORTS PLIB to toggle the LED.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a> 
## Web Links

- [Getting Started with Harmony v3 Peripheral Libraries on SAM D5x/E5x MCUs](hhttps://microchipdeveloper.com/harmony3:same54-getting-started-training-module)