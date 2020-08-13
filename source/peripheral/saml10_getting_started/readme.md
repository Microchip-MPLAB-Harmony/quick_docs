---
title: Getting Started with PLIBs on SAM L10 MCUs
parent: Peripheral Libraries
has_toc: false
nav_order: 4
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started with Harmony v3 Peripheral Libraries on SAM L10 MCUs

This tutorial shows you how to use the MHC to create an application that gets you started in developing applications on SAM L10 MCUs using MPLAB Harmony v3 software framework.

The application makes use of <a href="https://www.microchip.com/Developmenttools/ProductDetails/DM320204" target="_blank">SAM L10 Xplained Pro Evaluation Kit</a> and <a href="https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a> (sold separately).

The application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension. The temperature read is displayed on a serial console periodically every 500 milliseconds. The periodicity of the temperature values displayed on the serial console is changed to one second, two seconds, four seconds, and back to 500 milliseconds every time you press the switch SW0 on the SAM L10 Xplained Pro Evaluation Kit. Also, an LED0 is toggled every time the temperature is displayed on the serial console.

The application you create will utilize:

- SERCOM (as I²C) PLIB to read the temperature from a temperature sensor
- Real-Time Clock (RTC) PLIB to periodically sample temperature sensor data
- SERCOM (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) and Direct Memory Access (DMA) PLIBs to print the temperature values on a COM (serial) port terminal application running on a PC
- PORT PLIB to toggle the LED
- External Interrupt Controller (EIC) PLIB to change the periodicity of temperature sensor data read using SWITCH press event


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:saml10-getting-started-training-module" target="_blank">Getting Started with Harmony v3 Peripheral Libraries on SAM L10 MCUs</a>




## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() 
