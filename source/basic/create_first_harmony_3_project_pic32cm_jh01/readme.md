---
title: Create a first application on PIC32CM JH01 Microcontrollers using MPLAB Harmony v3 with using MCC

parent:  Harmony Basics
has_toc: false
nav_order: 12
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create a first application on PIC32CM JH01 Microcontrollers using MPLAB Harmony v3 with MCC

The PIC32CM JH family of microcontrollers (MCUs) is the next generation of the popular SAM C21 family of Arm® Cortex®-M0+ based MCUs. The PIC32CM JH family of MCUs delivers a variety of popular features plus extended memory options up to 512 KB of Flash and 64 KB to help create designs that need functional safety, enhanced touch, or security. This family pin is compatible with the SAM C21 family in the 32-pin, 48-pin and 64-pin packages.

The application makes use of [PIC32CM JH01 Curiosity Pro Evaluation Kit](https://www.microchip.com/en-us/development-tool/ev81x90a).

This tutorial explains how to create a simple application on a Cortex-M0+ based PIC32CM JH01 Microcontroller using the [MPLAB Code Configurator (MCC)](https://developerhelp.microchip.com/xwiki/bin/view/software-tools/mcc/) with MPLAB Harmony v3 modules. The objective of this application is to toggle an LED on a timeout basis and print the LED toggling rate. For this demonstration, the following MPLAB Harmony v3 modules are used and configured using the MCC.

The applications you create will utilize:

- The PORT pin to toggle LED.
- Real-Time Clock (RTC) PLIB to periodically sample LED toggling rate.
- External Interrupt Controller (EIC) PLIB to change the toggling rate when there is a switch press event.
- Serial Communication Interfaces (SERCOM (SERCOM configured as USART)) and DMA PLIBs to print LED toggling rate on COM port terminal application (Serial Console) running on a computer.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://ww1.microchip.com/downloads/aemDocuments/documents/MCU32/ProductDocuments/SupportingCollateral/Creating-the-First-Application-on-PIC32CM-JH01-Microcontrollers-Using-MPLAB-Harmony-v3-with-MCC-DS90003353.pdf" target="_blank">Creating the First Application on PIC32CM JH01 Microcontrollers Using MPLAB Harmony v3 with MPLAB Code Configurator (MCC)</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
