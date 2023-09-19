---
title: Migrating ASF SAM C21 Application to MPLAB Harmony v3 PIC32CM MC
parent: Migration Guides
has_toc: false
nav_order: 12
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Migrating ASF SAM C21 Application to MPLAB Harmony v3 PIC32CM MC

This tutorial shows you how to migrate an application from Advanced Software Framework (ASF) to MPLAB® Harmony v3 software framework using 32-bit Arm® Cortex®-based M0+ PIC32CM MC microcontroller.

MPLAB® Harmony v3 is a flexible, fully integrated embedded software development framework for 32-bit microcontrollers (MCUs) and microprocessors (MPUs). MPLAB Harmony v3 includes the MPLAB Harmony Configurator (MHC) tool, a set of modular Peripheral Libraries (PLIBs), drivers, system services, middleware, and numerous example applications, all of which are designed to help you quickly and easily develop powerful and efficient embedded software for Microchip’s 32-bit PIC® and SAM devices.

The application makes use of the [PIC32CM MC Curiosity Development Board](https://www.microchip.com/developmenttools/ProductDetails/EV15N46A) and the [I/O1 Xplained Pro Extension Kit](https://microchipdeveloper.com/boards:sam-l10-xpro#io1-xpro-extension) (sold separately).

This tutorial will migrate a pre-developed ASF SAMC21 [IO1 xplained demo](https://start.atmel.com/#examples/SAMC21XplainedPro/io/IO1/xplained/demo) application available in Atmel START.

The application reads current room temperature from the temperature sensor and light level from light sensor on the I/O1 Xplained Pro Extension and sends it to the console.

This training module will implement the same application and will also demonstrate the callback feature.

The application you create will utilize:

- SERCOM (as I²C) PLIB to read the temperature from a temperature sensor.
- SERCOM (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) PLIBs and STDIO library to print the temperature values on a COM (serial) port terminal application running on a PC.
- The ADC peripheral library is used to read data from the light sensor.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:migrate-asf-samc21-application-to-harmony3" target="_blank">Migrating ASF SAM C21 Application to MPLAB Harmony v3 PIC32CM MC</a>


## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()  
