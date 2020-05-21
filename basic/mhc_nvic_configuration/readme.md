---
title: MHC NVIC Configuration
parent: Basic
has_toc: false
nav_order: 5
---

# MHC NVIC Configuration

MHC plug-in consists of following plug-ins/managers based on the device selection while creating the project.

- Clock Configuration: Enables to configure Master, Generic, Peripheral and System Clocks
- Pin Configuration: Enables to configure pins in the Pin Configuration area depending upon the application requirements
- NVIC Configuration: Enables to configure enable/disable of interrupts, interrupt priority and name
- DMA Configuration: Enables to configure DMA Channels
- MPU Configuration: Enables to configure different zones of Memory Protection Unit

To open **NVIC Configuration** MHC plug-in, perform this action MHC → Tools then click **NVIC Configuration** .

<img src = "images/figure_5.11.png" width="288" height="377" align="middle">  

**Note**: MHC plugins availability will vary depending on the device selection while creating the project.

## NVIC Configuration

NVIC Manager allows users to enable or disable interrupts, change priority, and change names of interrupt handlers, see image below.

<img src = "images/figure_5.16.png" width="700" height="440" align="middle">

**Note**: In the screenshot above, the MHC NVIC configuration for SAME70 MCU is shown as an example. The MHC NVIC configuration for other PIC or SAM MCUs may differ from the one shown above. 

## Reference Links
- <a href="https://www.microchip.com/design-centers/32-bit" target="_blank">Microchip 32-bit MCUs</a>
- <a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank">Microchip MPLAB X IDE</a>
- <a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank">Microchip MPLAB Harmony</a>
- <a href="https://www.microchip.com/mplab/compilers" target="_blank">MPLAB XC32/32++ C Compiler</a>
