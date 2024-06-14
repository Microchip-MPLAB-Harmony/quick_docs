---
title: Create a new MPLAB Harmony v3 project using MCC
parent:  Harmony Basics
has_toc: false
nav_order: 20
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create a new MPLAB Harmony v3 project using MCC

This tutorial shows you how to create a new MPLAB Harmony v3 project using [MPLAB Code Configurator (MCC)](https://developerhelp.microchip.com/xwiki/bin/view/software-tools/mcc/). This training module used SAM D5x/E5x MCUs to create an application that gets you started in developing applications using MCC on the MPLAB Harmony v3 software framework.

The application makes use of [SAM E51 Curiosity Nano Evaluation Kit](https://www.microchip.com/en-us/development-tool/EV76S68A).


**Note:** Though this application uses the SAM E51 microcontroller as an example, the general description and steps to install, configure, and generate code using MCC applies to all 32-bit PIC and SAM microcontrollers.


This application demonstrates an LED (LED0) toggle on a timeout basis and prints the LED toggling rate on the serial terminal. The periodicity of the timeout will change from 500 milliseconds to 1 second, 2 seconds, 4 seconds, and back to 500 milliseconds every time you press the switch SW0 on the SAM E51 Curiosity Nano Evaluation Kit.

The applications you create will utilize:

- Real-Time Clock (RTC) PLIB to periodically sample temperature sensor data.
- SERCOM (as USART), Direct Memory Access (DMA) PLIBS to print the temperature values on a COM (serial) port terminal application running on a PC.
- PORT PLIB to toggle the LED.
- Help develop your first MPLAB Harmony v3 application using MCC.
In the process, the lab will also demonstrate the use of callback functions.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://developerhelp.microchip.com/xwiki/bin/view/software-tools/harmony/getting-started-training-module-using-mcc/" target="_blank">Create a new MPLAB Harmony v3 project using MCC</a>
- <a href="https://www.microchip.com/content/dam/mchp/documents/MCU32/ProductDocuments/SupportingCollateral/Creating-the-First-Application-on-PIC32CM-LSx-Microcontrollers-Using-MPLAB-Harmony-v3-with-MPLAB-Code-Configurator-DS90003342.pdf" target="_blank">Creating the First Application on PIC32CM LSx Microcontrollers Using MPLAB Harmony v3 with MPLAB Code Configurator (MCC)</a>
- <a href="https://ww1.microchip.com/downloads/aemDocuments/documents/MCU32/ProductDocuments/SupportingCollateral/Dual-Developer-Application-Development-Use-Case-with-TrustZone-on-SAM-L11-Using-MPLAB-Harmony-DS90003306.pdf" target="_blank"> Dual Developer Application Development Use Case with TrustZone on SAM L11 Using MPLAB Harmony v3</a>
- <a href="https://youtu.be/0rNFSlsVwVw?si=njPYitpENsH-qBBx" target="_blank">How to Set up the Tools Required to Get Started with MPLAB® Harmony v3 and MCC</a>
- <a href="https://youtu.be/0rNFSlsVwVw?si=tTK6mX9aV6slOcjA&t=145" target="_blank">MPLAB Harmony 3 Content Manager</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
