---
title: Low Power with PLIBs on SAMD21 MCUs
parent: Peripheral Libraries
has_toc: false
nav_order: 14
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Low Power Application on SAM D21 (Arm® Cortex® M0+) MCUs Using MPLAB® Harmony v3 Peripheral Libraries

The SAM D21 is a 32-bit Arm® Cortex® - M0+ based microcontroller that provides features to reduce power consumption through different Sleep modes, such as Idle and Standby.

- In Idle mode, the CPU is stopped and optionally, some synchronous clock domains are stopped, depending on the IDLE argument. The regulator operates in Normal mode. This mode allows power optimization with a fast wake-up time.
- In Standby mode, all clock sources are stopped, except those which are kept running if requested by a running module or have the ONDEMAND bit set to zero. The regulator operates in Low Power mode. Before entering Standby mode the user must make sure that a significant amount of clocks and peripherals are disabled so that the voltage regulator is not overloaded. This mode allows the device to consume the lowest power with little overhead on wake-up time.

The Power Manager (PM) module is responsible for controlling the Low Power modes. Additionally, the SAM D21 provides SleepWalking. SleepWalking is the capability for a device to temporarily wake up clocks for the peripheral to perform a task without waking up the CPU in STANDBY sleep mode.


The application makes use of the <a href="https://microchipdeveloper.com/boards:sam-d21-xpro" target="_blank">SAM D21 Xplained Pro evaluation kit</a>, <a href="https://microchipdeveloper.com/hwtools:pwrdebug-start" target="_blank"> Power Debugger </a> and the <a href="https://www.microchip.com/Developmenttools/ProductDetails/ATIO1-XPRO" target="_blank">I/O1 Xplained Pro Extension Kit</a> (sold separately).

The application is developed on the MPLAB Harmony v3 software framework. MPLAB Harmony v3 is a modular framework that provides interoperable firmware libraries for application development on 32-bit MCUs and MPUs. It includes an easy-to-use Graphical User Interface (GUI) (MPLAB Harmony Configurator (MHC)) for selecting, configuring, and generating starter codes, peripheral libraries, and middleware (USB, TCP/IP, Graphics and so on).

On power-up, the application prints a menu on a PC serial terminal. The menu provides options to measure the device power consumption in Sleep modes or to measure wake-up time when the device is wake-up from one of the Sleep modes. Once the option is selected, the application sets up EIC peripheral clock source and goes to Standby Sleep mode to enable measurement modes.


In this training module,

- The power consumption of the SAM D21 Xplained Pro board is measured using two tools
  - External Power Debugger - A hardware tool
  - Data Visualizer - A software tool
  The steps to connect and measure the power consumption using these tools are provided in the following sections.

- Device wake-up time is measured using the Logic Analyzer. The steps to connect and measure the wake-up time are provided in the following sections.

**Power Measurement Mode:**
By default, the application is running with the device in Standby Sleep mode. While the device is in Standby Sleep mode, the user can measure the device's power consumption by following the instructions provided in the following sections.

The device wakes up from Standby mode and enters Active mode when you cover the light sensor (by placing a hand over it, for example) on the I/O1 Xplained Pro Extension kit. Here, you can observe the transition of the device's power consumption from Standby Sleep mode to Active mode on the Data Visualizer tool.

The application prints the room temperature on a serial terminal, and the device goes back to Standby Sleep mode. The LED0 on the SAM D21 Xplained Pro Evaluation Kit is toggled every time the serial console displays the temperature.

When you press the switch button SW0, the application switches from Standby Sleep mode to Idle Sleep mode. Here, you can observe the transition of the device's power consumption from Standby Sleep mode to Active mode and from Active mode to Idle Sleep mode. At this point, you can measure the device's power consumption in Idle Sleep mode by following the instructions provided in the following sections.

The device wakes up from Idle mode and enters Active mode when you cover the light sensor (by placing a hand over it, for example) on the I/O1 Xplained Pro extension kit. Here, you can observe the transition of the device's power consumption from Idle Sleep mode to Active mode on the Data Visualizer tool.

The application prints the room temperature on a serial terminal, and the device goes back to Standby Sleep mode. The LED0 on the SAM D21 Xplained Pro Evaluation Kit is toggled every time the serial console displays the temperature.

**Wake-up Time Measurement Mode:**
By default, the application is running with the device in Standby Sleep mode, and the device wakes up from Standby Sleep mode when you press a switch on the development board.

The application toggles the Wake-up GPIO pin on the device wake-up and then goes to the Idle Sleep mode. You can measure the wake-up time by monitoring the switch SW0 pin and Wake-up GPIO pin on the Logic Analyzer tool.

In the next switch press, you can measure the wake-up time from Idle Sleep mode by monitoring the same switch SW0 pin and Wake-up GPIO pin on the Logic Analyzer tool.

The application switches the device Sleep mode between Standby Sleep mode and Idle Sleep mode whenever you press the SW0 switch. Therefore, you can measure the wake-up time from these Sleep modes by monitoring the switch SW0 on the Logic Analyzer tool.

Also, the device wakes up from Standby mode or Idle mode when you cover the light sensor by placing your hand over it, prints the wake-up reason message, and goes back to Sleep mode.

The application you create will utilize the following peripherals:

- SERCOM2 (as I²C) peripheral library to read the temperature from the temperature sensor.
- Real-Time Clock (RTC) peripheral library to periodically generate an event for the AC to sample the light sensor.
- SERCOM3 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) peripheral library to print messages on a serial console running on a computer.
- PORT peripheral library to toggle the LED0.
- Analog Comparator (AC) peripheral library to sample the light sensor analog input and detect whether the light sensor is covered or not.
- PM peripheral library to configure Low Power modes.
- External Interrupt Controller (EIC) peripheral library to control the user button SW0.
- EVSYS peripheral library to trigger the start of the AC conversion on every RTC compare match event. The EVSYS allows for peripheral-to-peripheral communication without CPU intervention. This reduces the burden on the CPU and other resources when compared to conventional interrupt-based systems.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:low-power-application-on-samd21" target="_blank">Low Power Application on SAM D21 (Arm® Cortex® M0+) MCUs Using MPLAB® Harmony v3 Peripheral Libraries</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()
