---
title: Rapid Prototyping with Curiosity Nano Using MPLAB Harmony v3
parent: Middleware Examples
has_toc: false
nav_order: 3
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Rapid prototyping with Curiosity Nano Evaluation Kit using MPLAB Harmony v3

This tutorial shows you how to develop an application prototype from a concept without designing a PCB using 32-bit MCU-based Curiosity Nano Evaluation Kits and Nano baseboard.

The problem statement you would address is implementing a smart appliance control application on the PIC32CM MC00 Curiosity Nano Evaluation Kit using MPLAB® Harmony v3 software framework.

The application makes use of the [PIC32CM MC00 Curiosity Nano Evaluation Kit](https://www.microchip.com/en-us/development-tool/EV10N93A), the [BM71-XPRO Bluetooth Low energy board](https://www.microchip.com/en-us/development-tool/DM164146), and the following MikroElektronika Click boards: [WEATHER CLICK](https://www.mikroe.com/weather-click), [Fan Click](https://www.mikroe.com/fan-click), [EINK CLICK BUNDLE](https://www.mikroe.com/eink-click).

The application is developed on the MPLAB Harmony v3 software framework. MPLAB Harmony v3 is a modular framework that provides interoperable firmware libraries for application development on 32-bit MCUs and MPUs. It includes an easy-to-use Graphical User Interface (GUI) (MPLAB Harmony Configurator (MHC)) for selecting, configuring, and generating starter codes, peripheral libraries, and middleware (USB, TCP/IP, Graphics, and so on).

This application demonstrates smart control of an appliance (fan) through an Android-based smartphone over a Bluetooth Low Energy (BLE) connection.

The application enables BLE transfers by connecting the BM71 XPRO to the Microchip Bluetooth Data (MBD) Android smartphone application. The BM71 XPRO uses a transparent service for data exchange with the Android MBD mobile application. The BM71 XPRO interfaces to the MCU over SERCOM - USART interface.

The fan connected to Fan Click via the I²C interface is controlled based on the mobile application's commands. The application supports two types of commands received over BLE.

### Environment temperature-based Fan Control mode command
- When the application receives a command TEMP_CTRL from the Android smartphone, the fan is run based on the environmental temperature. The application reads the temperature values from a weather sensor and displays them on the eINK display and controls a DC fan as mentioned below.
  - The fan rotates at LOW speed at a temperature between 18 (64°F) to 25 (77°F) degrees Celsius.
  - The fan rotates at MEDIUM speed at a temperature between 26 (78°F) to 30 (86°F) degrees Celsius.
  - Temperature is greater than 30 degrees Celsius (86°F), the fan rotates at HIGH speed.
  - Temperature is less than 18 (64°F), the fan is switched OFF.  

### Fan operation control based on the commands received from the Android smartphone.
- You can control the fan by sending specific commands to the MBD app running on the connected smartphone.
  - BLE_CTRL: FAN_ON - Turns the fan "On" and runs at LOW speed.
  - BLE_CTRL: FAN_OFF - Turns "Off" the fan.
  - BLE_CTRL: FAN_LOW - Runs the fan at LOW speed.
  - BLE_CTRL: FAN_MID - Runs the fan at MEDIUM speed.
  - BLE_CTRL: FAN_HIGH - Runs the fan at HIGH speed.


The application you create will utilize the following peripherals:

- SERCOM0 (as I²C) peripheral library to read the temperature from the Weather Click sensor and control the speed of the 5 V DC fan using the Fan Click.
- SERCOM1 (as SPI) peripheral library to display the temperature and fan speed status on the eINK display
- SERCOM3 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) peripheral library to communicate with the BM71-XPRO using the BM71 Driver
- SysTick and Timer (TC0) peripheral libraries are used for MikroElektronika board and BM71 driver timing requirements

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:rapid-prototyping-with-32-bit-mcu-based-cnano" target="_blank">Rapid prototyping with 32-bit MCU-based Curiosity Nano Evaluation Kit using MPLAB Harmony v3 Software Framework</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()  
