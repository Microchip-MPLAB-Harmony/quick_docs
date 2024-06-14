---
title: Create a first application on PIC32CX SG Microcontrollers using MPLAB Harmony v3 with using MCC

parent:  Harmony Basics
has_toc: false
nav_order: 14
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create a first application on PIC32CX SG Microcontrollers using MPLAB Harmony v3 with MCC

This tutorial explains how to create a simple application on a Arm® Cortex-M4F based PIC32CX SG Microcontroller using the [MPLAB Code Configurator (MCC)](https://developerhelp.microchip.com/xwiki/bin/view/software-tools/mcc/) with MPLAB Harmony v3 modules. The objective of this Application is to toggle
an LED on a timeout basis and print the LED toggling rate and temperature reading periodically on a serial console. For this demonstration, the following MPLAB Harmony v3 modules are used and configured using the
MCC:

The application makes use of [PIC32CX SG61 Curiosity Ultra Evaluation Board](https://www.microchip.com/en-us/development-tool/EV09H35A).

The objective of this application is to toggle an LED on a timeout basis and print the LED toggling rate on the serial console. For this demonstration, the following MPLAB Harmony v3 modules are used and configured using the MCC.

The applications you create will utilize:

- The PORT pin to toggle the LED.
- Real-Time Clock (RTC) PLIB to periodically sample the LED toggling rate and temperature reading.
- Two instances of the External Interrupt Controller (EIC) PLIB: one to change the toggling rate when there is a switch press event and another one to decide what needs to be printed on the Serial Console; temperature reading or LED toggling rate.
- SERCOM (configured as I2C) PLIB to read the temperature from an on-board temperature sensor.
- SERCOM (configured as USART) and DMA PLIBs to print the LED toggling rate and temperature reading on a COM (serial console) port terminal application running on a PC.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://ww1.microchip.com/downloads/aemDocuments/documents/MCU32/ProductDocuments/SupportingCollateral/Creating-the-First-Application-on-PIC32CX-SG-Microcontrollers-Using-MPLAB-Harmony-v3-with-MPLAB-Code-Configurator-DS90003345.pdf" target="_blank">Creating the First Application on PIC32CX SG Microcontrollers Using MPLAB Harmony v3 with MPLAB Code Configurator (MCC) </a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
