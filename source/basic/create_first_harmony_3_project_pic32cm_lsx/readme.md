---
title: Create a first application on PIC32CM LSx Microcontrollers using MPLAB Harmony v3 with using MCC

parent:  Harmony Basics
has_toc: false
nav_order: 13
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create a first application on PIC32CM LSx Microcontrollers using MPLAB Harmony v3 with MCC

This document describes how to create a simple application on an Arm® Cortex®-M23 based PIC32CM LSx Microcontroller using the [MPLAB Code Configurator (MCC)](https://developerhelp.microchip.com/xwiki/bin/view/software-tools/mcc/) with MPLAB Harmony v3 modules. This application demonstrates the TrustZone®-based security feature on PIC32CM LSx Microcontrollers. 

The application consists of two projects which details about Secure and Non-Secure modes on PIC32CM LSx Microcontrollers. These two projects offer security isolation between the trusted and non-trusted resources in the device. The objective of this application is to toggle an LED on a timeout basis and print the LED toggling rate on the Serial Console. For this
demonstration, the following MPLAB Harmony v3 modules are used and configured using the MCC as Secure and Non-Secure.

The application makes use of [PIC32CM LS60 Curiosity Pro Evaluation Kit](https://www.microchip.com/en-us/development-tool/EV76R77A).

The applications you create will utilize:

- Secure PORT Pin to toggle LED (by default, all the PORT pins are configured as Secure).
- Secure Real-Time Clock (RTC) PLIB to periodically sample LED toggling rate.
- Secure External Interrupt Controller (EIC) PLIB to change the toggling rate when a switch press event occurs. The Non-Secure modules include:
- Non-Secure SERCOM (configured as USART) and Non-Secure Direct Memory Access (DMA) PLIBs to print the LED toggling rate on a COM (serial) port terminal application running on a PC.
- Non-Secure Port Pins (USART pins are responsible for printing the data on the Terminal after obtaining the values from Secure Application) to communicate with the Serial Terminal.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://ww1.microchip.com/downloads/aemDocuments/documents/MCU32/ProductDocuments/SupportingCollateral/Creating-the-First-Application-on-PIC32CM-LSx-Microcontrollers-Using-MPLAB-Harmony-v3-with-MPLAB-Code-Configurator-DS90003342.pdf" target="_blank">Creating the First Application on PIC32CM LSx Microcontrollers Using MPLAB Harmony v3 with MPLAB Code Configurator (MCC)</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
