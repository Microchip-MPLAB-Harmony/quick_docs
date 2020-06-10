---
title: Getting Started with Middleware on PIC32MZ EF MCUs
parent: Middleware Examples
has_toc: false
nav_order: 1
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started with Harmony v3 Drivers and Middleware on PIC32MZ EF MCUs using FreeRTOS


This tutorial shows you how to use the MHC to create an application that gets you started in developing applications on PIC32MZ EF MCUs using MPLAB Harmony v3 software framework with FreeRTOS™.

Harmony v3 drivers support Asynchronous and Synchronous modes of operation.

- Asynchronous Mode
    - Non-blocking Application Program Interfaces (APIs)
    - Works seamlessly in bare-metal and RTOS environment
    - Interrupt and thread-safe
- Synchronous Mode
    - Blocking APIs
    - Suitable for use in RTOS environment
    - Interrupt and thread-safe

In this tutorial, you will use Harmony drivers in Synchronous mode of operation and Harmony middleware libraries with FreeRTOS.

The application makes use of <a href="https://www.microchip.com/DevelopmentTools/ProductDetails/DM320209" target="_blank">Curiosity PIC32MZ EF 2.0 Development Board</a> and <a href="https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a>.

The application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension Kit. The temperature reading is displayed on a serial console periodically every second. Further, the application writes the temperature readings to EEPROM and to a file in a USB thumb drive whenever the USB thumb drive is connected. Also, an LED (LED1) is toggled every time the temperature is displayed on the serial console and an LED (LED2) is in ON state when a USB thumb drive is connected.

The application you create will utilize:

- I²C Synchronous Driver to read the temperature from a temperature sensor and store/retrieve to/from EEPROM.
- Universal Synchronous Asynchronous Receiver Transmitter (USART) Synchronous Driver to print the temperature values on a COM (serial) port terminal application running on a PC.
- USB High-Speed Driver, USB Host Middleware, and File System Service libraries to write the temperature readings to a file in a USB thumb drive whenever a USB thumb drive is connected.
- GPIO Peripheral Library to toggle an LED.
- FreeRTOS library to create middleware, application threads, and intercommunicate between these threads.



For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:pic32mz-get-start-tm-drvr-middlware-freertos" target="_blank">Getting Started with Harmony v3 Drivers and Middleware on PIC32MZ EF MCUs using FreeRTOS</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()  
