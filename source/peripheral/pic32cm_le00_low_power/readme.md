---
title: Low Power with PLIBs on PIC32CM LE00 MCU
parent: Peripheral Libraries
has_toc: false
nav_order: 2
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Low Power Application on PIC32CM LE00 (Cortex M23) MCU Using MPLAB® Harmony v3 Peripheral Libraries

The PIC32CM LE00 is a 32-bit Arm® Cortex®-M23-based microcontroller that provides features to reduce power consumption through different Sleep modes, such as Idle and Standby.

- In Idle mode, the CPU is stopped and optionally, some synchronous clock domains are stopped, depending on the IDLE argument. The regulator operates in Normal mode. This mode allows power optimization with a fast wake-up time.
- In Standby mode, all clock sources are stopped, except those that are kept running if requested by a running module or have the ONDEMAND bit set to zero. The regulator operates in Low Power mode. Before entering Standby mode the user must make sure that a significant amount of clocks and peripherals are disabled so that the voltage regulator is not overloaded. This mode allows the device to consume the lowest power with little overhead on wake-up time.

The Power Manager (PM) module is responsible for controlling the Low Power modes. Additionally, the PIC32CM LE00 MCU provides SleepWalking. SleepWalking is the capability for a device to temporarily wake up clocks for the peripheral to perform a task without waking up the CPU in STANDBY sleep mode.

The application makes use of the [PIC32CM LE00 Curiosity Pro Evaluation Kit](https://www.microchip.com/en-us/development-tool/ev80p12a), and the [I/O1 Xplained Pro Extension Kit](https://www.microchip.com/en-us/development-tool/ATIO1-XPRO) (sold separately).

The application is developed on the MPLAB Harmony v3 software framework. MPLAB Harmony v3 is a modular framework that provides interoperable firmware libraries for application development on 32-bit MCUs and MPUs. It includes an easy-to-use Graphical User Interface (GUI) (MHC) for selecting, configuring, and generating starter codes, peripheral libraries, and middleware (USB, TCP/IP, Graphics, and so on).

On power-up, the application prints a menu on a PC serial terminal. The menu provides options to measure the device's power consumption in Sleep modes. Once the option is selected, the application sets up the EIC peripheral clock source and goes to Standby Sleep mode to enable measurement modes.

In this training module,
The power consumption of the PIC32CM LE00 Curiosity Pro Evaluation Kit is measured using the tool:

- Data Visualizer - A software tool

The steps to connect and measure the power consumption using these tools are provided in the following sections.

**Power Measurement Mode**
By default, the application is running with the device in Standby Sleep mode. While the device is in Standby Sleep mode, the user can measure the device's power consumption by following the instructions provided in the following sections.

The device wakes up from Standby mode and enters Active mode when you cover the light sensor (by placing a hand over it, for example) on the I/O1 Xplained Pro Extension Kit. Here, you can observe the transition of the device's power consumption from Standby Sleep mode to Active mode on the Data Visualizer tool.

The application prints the room temperature on a serial terminal, and the device goes back to Standby Sleep mode. The LED0 on the PIC32CM LE00 Curiosity Pro Evaluation Kit is toggled every time the serial console displays the temperature.

When you press the switch button SW1, the application switches from Standby Sleep mode to Idle Sleep mode. Here, you can observe the transition of the device's power consumption from Standby Sleep mode to Active mode and from Active mode to Idle Sleep mode. At this point, you can measure the device's power consumption in Idle Sleep mode by following the instructions provided in the following sections.

The device wakes up from Idle mode and enters Active mode when you cover the light sensor (by placing a hand over it, for example) on the I/O1 Xplained Pro extension Kit. Here, you can observe the transition of the device's power consumption from Idle Sleep mode to Active mode on the Data Visualizer tool.

The application prints the room temperature on a serial terminal, and the device goes back to Standby Sleep mode. The LED0 on the PIC32CM LE00 Curiosity Pro Evaluation Kit is toggled every time the serial console displays the temperature.

By default, the application is running with the device in Standby Sleep mode, and the device wakes up from Standby Sleep mode when you press a switch on the Evaluation board. The application switches the device's Sleep mode between Standby Sleep mode and Idle Sleep mode whenever you press the SW1 switch.

Also, the device wakes up from Standby mode or Idle mode when you cover the light sensor by placing your hand over it, prints the wake-up reason message, and goes back to Sleep mode.

The application you create will utilize the following peripherals:

- SERCOM5 (as I²C) peripheral library to read the temperature from the temperature sensor.
- Real-Time Clock (RTC) peripheral library to periodically generate an event for the ADC to sample the light sensor.
- SERCOM3 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) peripheral library to print messages on a serial console running on a computer.
- PORT peripheral library to toggle the LED0.
- Analog to Digital Converter (ADC) peripheral library to sample the light sensor analog input and detect whether the light sensor is covered or not.
- PM peripheral library to configure Low Power modes.
- External Interrupt Controller (EIC) peripheral library to control the user button SW1.
- EVSYS peripheral library to trigger the start of the ADC conversion on every RTC compare match event. The EVSYS allows for peripheral-to-peripheral communication without CPU intervention. This reduces the burden on the CPU and other resources when compared to conventional interrupt-based systems.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://developerhelp.microchip.com/xwiki/bin/view/software-tools/harmony/low-power-application-on-pic32cm-le00/" target="_blank">Low Power Application on PIC32CM LE00 (Cortex M23) MCUs Using MPLAB® Harmony v3 Peripheral Libraries</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
