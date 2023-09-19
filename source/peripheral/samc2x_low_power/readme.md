---
title: Low Power with PLIBs on SAMC2x MCUs
parent: Peripheral Libraries
has_toc: false
nav_order: 9
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Low Power Application on SAMC2x (Cortex M0+) MCUs Using MPLAB Harmony v3 Peripheral Libraries

SAMC2x is part of Microchip's 32-bit Arm® Cortex® M0+ microcontroller (MCU) family that can be used to meet the needs of power-constrained applications. SAMC2x MCUs provide various sleep modes to meet the power consumption requirements of the application. The Power Manager (PM) module is responsible for controlling the low power modes.

SAMC2x supports two low power modes; IDLE and STANDBY.

Idle sleep mode: In Idle mode, CPU and Synchronous clocks are stopped except when requested. Idle mode allows power optimization with fast wakeup time.
Standby sleep mode: In standby mode, the CPU is stopped as well as the peripherals, except those that are running using the RUN IN STANDBY option. Standby mode allows the device to consume the lowest power with little overhead on wakeup time.

The application makes use of the <a href="https://www.microchip.com/developmenttools/ProductDetails/atsamc21-xpro" target="_blank">SAM C21 Xplained Pro evaluation kit</a>
 and the <a href="https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a> (sold separately).

On power-up, the application is in sleep (standby) mode. The application wakes up from the sleep mode and enters active mode when you cover the light sensor (by placing a hand over it) on the I/O1 Xplained Pro extension kit. The application periodically prints room temperature on a serial terminal while the light sensor is covered. The application goes back to sleep (standby) mode when you uncover the light sensor. LED0 in the SAM C21 evaluation kit is toggled every time the temperature is displayed on the serial console.

When you press the switch SW0, the application switches sleep mode from standby mode to idle mode.

The application you create will utilize:

- SERCOM (as I²C) Peripheral Library to read the temperature from the temperature sensor.
- RTC Peripheral Library to periodically generate an event for the ADC to sample the light sensor.
- SERCOM (as USART) and DMA Peripheral Libraries to print the temperature values on a COM (serial) port terminal application running on a PC.
- PORT Peripheral Library to toggle the LED.
- ADC Peripheral Library to sample the light sensor analog input and detect whether the light sensor is covered or not.
- PM (Power Manager) and Supply Controller (SUPC) Peripheral Libraries to configure low power modes.
- EIC (External Interrupt controller) Peripheral Library to control switch SW0.
Event System Peripheral Library to trigger the start of the ADC conversion on every RTC compare match event. The event system allows for peripheral-to-peripheral communication without CPU intervention. This reduces the burden on the CPU and other resources when compared to the conventional interrupt-based systems.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:low-power-application-on-samc21" target="_blank">Low Power Application on SAMC2x (Cortex M0+) MCUs Using MPLAB Harmony v3 Peripheral Libraries</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]() 
