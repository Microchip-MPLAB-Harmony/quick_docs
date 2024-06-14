---
title: Create a first application on PIC32CZ CAx Microcontrollers using MPLAB Harmony v3 with using MCC

parent:  Harmony Basics
has_toc: false
nav_order: 15
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create a first application on PIC32CZ CAx Microcontrollers using MPLAB Harmony v3 with MCC

This tutorial explains how to create a simple application on an Arm® Cortex®-M7 based PIC32CZ CAx Microcontroller using the [MPLAB Code Configurator (MCC)](https://developerhelp.microchip.com/xwiki/bin/view/software-tools/mcc/) with MPLAB Harmony v3 modules. This technical brief used PIC32CZ CAx MCUs to create an application that gets you started in developing applications using MCC on the MPLAB Harmony v3 software framework.

The application makes use of [PIC32CZ CA90 Curiosity Ultra Development Board](https://www.microchip.com/en-us/development-tool/ev16w43a).

**Note:** Though this application uses the PIC32CZ CAx microcontroller as an example, the general description and steps to install, configure, and generate code using MCC applies to all 32-bit PIC and SAM microcontrollers.


The objective of this application is to toggle an LED on a timeout basis and print the LED toggling rate on the serial console. For this demonstration, the following MPLAB Harmony v3 modules are used and configured using the MCC.

The applications you create will utilize:

- PORT Pin to toggle LED0.
- Real-Time Clock (RTC) PLIB to periodically sample the LED0 toggling rate.
- External Interrupt Controller (EIC) PLIB to change the toggling rate when there is a switch press event.
- Serial Communication Interfaces ((SERCOM) configured as USART) and Direct Memory Access (DMA) PLIBs to print the LED0 toggling rate on a COM (serial) port terminal application running on a PC.
- Port Pins (USART pins as they are responsible for printing the data on the terminal after obtaining the values) to communicate with the serial terminal.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://ww1.microchip.com/downloads/aemDocuments/documents/MCU32/ProductDocuments/SupportingCollateral/Creating-the-First-Application-on-PIC32CZ-CAx-Microcontrollers-Using-MPLAB-Harmony-v3-with-MPLAB-Code-Configurator-DS90003348.pdf" target="_blank">Creating the First Application on PIC32CZ CAx Microcontrollers Using MPLAB Harmony v3 with MPLAB Code Configurator (MCC)</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
