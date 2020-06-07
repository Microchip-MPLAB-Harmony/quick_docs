---
title: Low Power with PLIBs on SAM L21 MCUs
parent: Peripheral
has_toc: false
nav_order: 10
---

# Low Power Application on SAM L21 (Cortex M0+) MCUs Using MPLAB Harmony v3 Peripheral Libraries

This tutorial shows you how to create a low power application on a SAM L21 using MPLAB® Harmony v3 software framework.

The SAM L21 is a 32-bit Arm® Cortex® M0+ based microcontroller (MCU) that provides features to reduce power consumption through different Sleep modes such as Idle, Standby, Backup, and Off.

- In Idle mode, the CPU and the synchronous clocks are stopped, except when requested. This mode allows power optimization with a fast wake-up time.
- In Standby mode, the CPU and the peripherals are stopped, except those that are running using the Run in Standby mode feature. This mode allows the device to consume the lowest power with little overhead on wake-up time.
- In Backup mode, the device is entirely powered off, except for the peripherals in the backup domain. This mode allows you to achieve the lowest power consumption aside from Off mode but increases the wake-up time compared to Standby mode.
- In Off mode, the device is entirely powered off. It allows you to achieve the lowest power consumption. Since the device must be reset to recover from this mode, the wake-up time is the highest.  

The Power Manager (PM) module is responsible for controlling the Low Power modes. Additionally, the SAM L21 provides SleepWalking, an advanced low power operation mode, which is based on event propagation managed by the Event System (EVSYS).

This application makes use of the <a href="https://www.microchip.com/developmenttools/ProductDetails/atsaml21-xpro-b" target="_blank">SAM L21 Xplained Pro B evaluation kit</a>
 and the <a href="https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a> (sold separately).

On power-up, the device is set to Standby Sleep mode. The device wakes up from Standby mode and enters Active mode when you cover the light sensor (by placing a hand over it, for example) on the I/O1 Xplained Pro extension kit. The application periodically prints room temperature on a serial terminal while the light sensor is covered. The device goes back to Standby mode when you uncover the light sensor. LED0 in the SAM L21 evaluation kit is toggled every time the temperature is displayed on the serial console. When you press the switch button SW0, the application switches Sleep mode from Standby mode to Idle mode.

The application you create will utilize the following peripherals:

- SERCOM2 (as I²C) peripheral library to read the temperature from the temperature sensor.
- Real-Time Clock (RTC) peripheral library to periodically generate an event for the ADC to sample the light sensor.
- SERCOM3 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) peripheral library to print messages on a serial console running on a computer.
- Direct Memory Access Controller (DMAC) peripheral library to send the converted temperature value to the SERCOM3.
- PORT peripheral library to toggle the LED0.
- Analog-to-Digital Converter (ADC) peripheral library to sample the light sensor analog input and detect whether the light sensor is covered or not.
- PM and Supply Controller (SUPC) peripheral libraries to configure Low Power modes.
- External Interrupt Controller (EIC) peripheral library to control the user button SW0.
- EVSYS peripheral library to trigger the start of the ADC conversion on every RTC compare match event. The EVSYS allows for peripheral-to-peripheral communication without CPU intervention. This reduces the burden on the CPU and other resources when compared to the conventional interrupt-based systems.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:low-power-application-on-saml21" target="_blank">Low Power Application on SAM L21 (Cortex M0+) MCUs Using MPLAB Harmony v3 Peripheral Libraries</a>



## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() 
