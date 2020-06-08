---
title: Getting Started with PLIBs on PIC32MX 470 MCUs
parent: Peripheral
has_toc: false
nav_order: 7
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started With Harmony v3 Peripheral Libraries on PIC32MX 470 MCUs

This tutorial shows you how to use the MPLAB Harmony Configurator (MHC) to create an application that gets you started in developing applications on PIC32MX470 MCUs using MPLAB Harmony v3 software framework.

The application makes use of <a href="http://www.microchip.com/DevelopmentTools/ProductDetails.aspx?PartNO=DM320103" target="_blank">PIC32MX470 Curiosity Development Board</a>
, <a href="https://www.mikroe.com/weather-click" target="_blank">MikroElectronika Weather click board</a>, and <a href="https://www.mikroe.com/usb-uart-click" target="_blank">MikroElectronika USB UART click board</a>
 (sold separately).

The application reads the current room temperature from the temperature sensor on the MikroElectronika Weather click board. The temperature read is displayed on a serial console periodically every 500 milliseconds. The periodicity of the temperature values displayed on the serial console is changed to one second, two seconds, four seconds, and back to 500 milliseconds every time you press the switch S1 on the PIC32MX470 Curiosity Development Board. Also, LED1 is toggled every time the temperature is displayed on the serial console.

The application you create utilizes:

- I²C Peripheral Library (PLIB) to read the temperature from a temperature sensor.
- TMR2 PLIB to periodically sample temperature sensor data.
- CORETIMER PLIB to use blocking timer delay for initializing temperature sensor.
- UART and Direct Memory Access (DMA) PLIBs to print the temperature values on a COM (serial) port terminal application running on a PC.
- GPIO Peripheral Library to change the periodicity of temperature sensor data read using SWITCH press event and toggle the LED.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links
- <a href="https://microchipdeveloper.com/harmony3:pic32mx470-getting-started-training-module" target="_blank">Getting Started With Harmony v3 Peripheral Libraries on PIC32MX 470 MCUs</a>



## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() 
