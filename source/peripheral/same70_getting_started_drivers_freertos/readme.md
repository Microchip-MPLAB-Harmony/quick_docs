---
title: Getting Started with Drivers on SAM E70/S70/V70/V71 MCUs using FreeRTOS
parent: Peripheral Libraries
has_toc: false
nav_order: 15
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started with Harmony v3 Drivers on SAM E70/S70/V70/V71 MCUs Using FreeRTOS

This tutorial shows you how to use MHC to create an application that gets you started in developing applications on SAM E70/S70/V70/V71 MCUs using MPLAB Harmony v3 software framework.

Harmony v3 drivers support Asynchronous and Synchronous modes of operation.

- Asynchronous Mode
    - Non-blocking Application Program Interfaces (APIs)
    - Works seamlessly in bare-metal and RTOS environment
    - Interrupt and thread-safe
- Synchronous Mode
    - Blocking APIs
    - Suitable for use in RTOS environment
    - Interrupt and thread-safe

In this tutorial, you will use Harmony drivers in Synchronous mode of operation.

The application makes use of <a href="https://www.microchip.com/Developmenttools/ProductDetails/DM320113" target="_blank">SAM E70 Xplained Ultra board</a> and <a href="https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a> (sold separately).

The application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension Kit. The temperature reading is displayed on a serial console periodically every second. Further, the application writes the temperature readings to EEPROM. When a character is entered on the console, the last five written temperature values are read from the EEPROM and displayed on the console. Also, an LED (LED3) is toggled every time the temperature is displayed on the serial console.

The application you create will utilize:

- Two-Wire Interface High Speed (TWIHS) (I²C) Synchronous Driver to read the temperature from a temperature sensor and store/retrieve to/from EEPROM.
- USART Synchronous Driver to print the temperature values on a COM (serial) port terminal application running on a PC.
- PORTS Peripheral Library to toggle an LED.
- FreeRTOS library to create application threads and intercommunicate between application threads.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:same70-getting-started-tm-drivers-freertos" target="_blank">Getting Started with Harmony v3 Drivers on SAM E70/S70/V70/V71 MCUs Using FreeRTOS</a>



## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
