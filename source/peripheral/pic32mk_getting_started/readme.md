---
title: Getting Started with PLIBs on PIC32MK GP MCUs
parent: Peripheral Libraries
has_toc: false
nav_order: 8
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started with Harmony v3 Peripheral Libraries on PIC32MK GP MCUs

This tutorial shows you how to use the MPLAB Code Configurator (MCC) to create an application that will help you get started in developing applications on PIC32MK GP MCUs using MPLAB Harmony v3 Software Framework.

The application makes use of a <a href="https://www.microchip.com/en-us/development-tool/DM320106" target="_blank">PIC32MK General Purpose (GP) Development board</a> and a <a href="https://www.mikroe.com/weather-click#/263-clickid-yes" target="_blank">MikroElectronika Weather click board</a>
 (sold separately).

The application reads the current room temperature from the temperature sensor on the MikroElectronika Weather click board. The temperature reading is displayed on a serial console periodically every 500 milliseconds. The periodicity of the temperature values displayed on the serial console is changed to one second, two seconds, four seconds, and back to 500 milliseconds every time you press the switch S1 on the PIC32MK GP Development Board. Also, an LED (LED1) is toggled every time the temperature is displayed on the serial console.

The application you create will utilize:

- The Serial Peripheral Interface (SPI) Peripheral Library (PLIB) to read the temperature from a temperature sensor.
- The TMR2 PLIB to periodically sample temperature sensor data.
- The CORE TIMER PLIB to use a blocking timer delay for initializing the temperature sensor.
- The Universal Asynchronous Receiver Transmitter (UART) and Direct Memory Access (DMA) PLIBs to print the temperature values on a COM (serial) port terminal application running on a PC.
- The General Purpose Input/Output (GPIO) PLIB to change the periodicity of temperature sensor data readings using the SWITCH press event and to toggle the LED.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://developerhelp.microchip.com/xwiki/bin/view/software-tools/harmony/pic32mk-gp-db-getting-started-training-module/" target="_blank">Getting Started with Harmony v3 Peripheral Libraries on PIC32MK GP MCUs</a>



## Reference Links
[<a href="https://www.microchip.com/en-us/products/microcontrollers-and-microprocessors/32-bit-mcus" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/en-us/products/microcontrollers-and-microprocessors/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/en-us/tools-resources/develop/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/develop/mplab-xc-compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]() 
