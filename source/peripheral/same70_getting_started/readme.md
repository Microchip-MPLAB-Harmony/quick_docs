---
title: Getting Started with PLIBs on SAM E70/S70/V70/V71 MCUs
parent: Peripheral Libraries
has_toc: false
nav_order: 3
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started with Harmony v3 Peripheral Libraries on SAM E70/S70/V70/V71 MCUs

This tutorial shows you how to use MPLAB Code Configurator MCC to create an application that gets you started in developing applications on SAM E70/S70/V70/V71 MCUs using MPLAB Harmony v3 software framework.

The application makes use of <a href="https://www.microchip.com/en-us/development-tool/DM320113" target="_blank">SAM E70 Xplained Ultra board</a> and <a href="https://www.microchip.com/en-us/development-tool/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a> (sold separately).

The application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension. The temperature read is displayed on a serial console periodically every 500 milliseconds. The periodicity of the temperature values displayed on the serial console is changed to 1 second, 2 seconds, 4 seconds, and back to 500 milliseconds every time you press the switch SW0 on the SAM E70 Xplained Ultra Evaluation Kit. Also, an LED, LED3, is toggled every time the temperature is displayed on the serial console.

The application you create will utilize:

- Two-Wire Interfaces (TWIHS) (I²C) Peripheral Library to read the temperature from a temperature sensor
- Timer Counter (TC) Peripheral Library to periodically sample temperature sensor data
- Universal Synchronous Asynchronous Receiver Transmitter (USART) and Direct Memory Access (DMA) Peripheral Libraries to print the temperature values on a COM (serial) port terminal application running on a PC
- PORTS Peripheral Library to change the periodicity of temperature sensor data read using SWITCH event and toggle the LED

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://developerhelp.microchip.com/xwiki/bin/view/software-tools/harmony/same70-getting-started-training-module/" target="_blank">Getting Started with Harmony v3 Peripheral Libraries on SAM E70/S70/V70/V71 MCUs</a>



## Reference Links
[<a href="https://www.microchip.com/en-us/products/microcontrollers-and-microprocessors/32-bit-mcus" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/en-us/products/microcontrollers-and-microprocessors/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/en-us/tools-resources/develop/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/develop/mplab-xc-compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
