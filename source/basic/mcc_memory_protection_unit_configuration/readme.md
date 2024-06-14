---
title: MCC Memory Protection Unit Configuration
parent: Harmony Basics
has_toc: false
nav_order: 7
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)


# MCC Memory protection Unit (MPU) Configuration
MCC plug-in consists of following plug-ins/managers based on the device selection while creating the project.

- Clock Configuration: Enables to configure Master, Generic, Peripheral and System Clocks
- Pin Configuration: Enables to configure pins in the Pin Configuration area depending upon the application requirements
- NVIC Configuration: Enables to configure enable/disable of interrupts, interrupt priority and name
- DMA Configuration: Enables to configure DMA Channels
- MPU Configuration: Enables to configure different zones of Memory Protection Unit

To open **MPU Configuration** MCC plug-in, perform the action, MCC → Tools then click **MPU Configuration** .

 <img src = "images/figure_5.11.png" width="650" height="500" align="middle">

**Note**: MCC plugins availability will vary depending on the device selection while creating the project.

## MPU Configuration
Users can configure MPU regions for memory spaces, such as ITCM, DTCM, Flash, SRAM, Peripherals, EBI, QSPI, USBHS and System. Users can also set the different attributes for these memory spaces. See image below:

 <img src = "images/figure_5.18.png" width="850" height="430" align="middle">

**Note**: In the screenshot above, the MCC MPU configuration for SAME70 MCU is shown as an example. The MCC MPU configuration for other PIC or SAM MCUs may differ from the one shown above.

## Note
<span style="color:blue"> *This page has been verified with the following versions of software tools:*</span>
- [MPLAB X IDE v6.20](https://www.microchip.com/mplab/mplab-x-ide)
- [MPLAB XC32 Compiler v4.40](https://www.microchip.com/mplab/compilers)
- [MPLAB Code Configurator Plugin v5.5.1](https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator)
- [MPLAB Harmony v3 "csp" repo v3.18.5](https://github.com/Microchip-MPLAB-Harmony/csp/releases/tag/v3.18.5)

<span style="color:blue"> Because Microchip regularly update tools, occasionally there could be minor differences with the newer versions of the tools. </span>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
