---
title: Create a new MPLAB Harmony v3 project using MCC
parent:  Harmony Basics
has_toc: false
nav_order: 20
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create a new MPLAB Harmony v3 project using MCC

This tutorial shows you how to create a new MPLAB Harmony v3 project using [MPLAB Code Configurator (MCC)](https://microchipdeveloper.com/mplabx:mcc). This training module used SAM D5x/E5x MCUs to create an application that gets you started in developing applications using MCC on the MPLAB Harmony v3 software framework.

The application makes use of [SAM E51 Curiosity Nano Evaluation Kit](https://microchipdeveloper.com/boards:sam-e51-cnano).


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

- <a href="https://microchipdeveloper.com/harmony3:getting-started-training-module-using-mcc" target="_blank">Create a new MPLAB Harmony v3 project using MCC</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
