---
title: Update and Configure an Existing MHC-based MPLAB Harmony v3 Project to MCC-based Project
parent:  Harmony Basics
has_toc: false
nav_order: 21
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Update and Configure an Existing MHC-based MPLAB Harmony v3 Project to MCC-based Project

This tutorial shows you how to update and configure an existing MPLAB Harmony Configurator (MHC)-based MPLAB Harmony v3 project to [MPLAB Code Configurator (MCC)](https://developerhelp.microchip.com/xwiki/bin/view/software-tools/mcc/)-based project. This training module uses the [Getting Started Extended Application on Curiosity PIC32MZ EF 2.0 Development Board](https://github.com/Microchip-MPLAB-Harmony/reference_apps/releases/download/v1.3.0/getting_started_ext.zip) to update and configure an existing project.

The application makes use of [Curiosity PIC32MZEF v2 Development Board](https://www.microchip.com/en-us/development-tool/DM320209) and [I/O1 Xplained Pro Kit](https://www.microchip.com/en-us/development-tool/ATIO1-XPRO) (optional if you intend to exercise the extended functionality described below).

**Note:** Though this application uses the PIC32MZEF microcontroller as an example, the general description and steps to install, configure, and generate code using MCC applies to all 32-bit PIC and SAM microcontrollers.


This application demonstrates an LED toggle (LED1 toggles when the switch SW1 is pressed and LED3 toggles when switch SW3 is pressed) on a timeout basis and prints the LED toggling rate on the serial terminal. The periodicity of the timeout will change from 500 milliseconds to one second, two seconds, four seconds, and back to 500 milliseconds every time you press the switch SW1 or SW3 on the Curiosity PIC32MZ EF 2.0 Development Board. The periodicity will not change while switching between SW1 to SW3 or vice versa.

The demo application has extended functionality to print the current room temperature periodically when switch SW2 is pressed (the Xplained pro extension connector on the Curiosity PIC32MZ EF 2.0 Development Board must be plugged with I/O1 Xplained Pro Extension Kit).

This application will utilize:

- Timer Peripheral Library to periodically sample temperature sensor data and to toggle LED.
- I2C Peripheral Library to read the temperature from a temperature sensor.
- Universal Asynchronous Receiver Transmitter (UART), Direct Memory Access (DMA) Peripheral Libraries to print the temperature values on a COM (serial) port terminal application running on a PC.
- GPIO Peripheral Library to toggle the LED.
- Help develop your first MPLAB Harmony v3 application using MCC.
In the process, the lab will also demonstrate the use of callback functions.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://developerhelp.microchip.com/xwiki/bin/view/software-tools/harmony/update-and-configure-existing-mhc-proj-to-mcc-proj/" target="_blank">Update and Configure an Existing MHC-based MPLAB Harmony v3 Project to MCC-based Project</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
