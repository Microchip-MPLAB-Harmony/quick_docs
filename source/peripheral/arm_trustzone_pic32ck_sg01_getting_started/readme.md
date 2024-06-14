---
title: Arm TrustZone Getting Started Application on PIC32CK SG01 MCU
parent: Peripheral Libraries
has_toc: false
nav_order: 1
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Arm TrustZone Getting Started Application on  PIC32CK SG01 MCU

This tutorial shows you how to create an Arm TrustZone feature application on PIC32CK SG01 microcontroller (MCU) using the MPLAB Harmony v3 software framework.

The PIC32CK SG01 MCU is the implementation of the Arm TrustZone for Armv8-M devices. TrustZone technology for an Armv8-M device is based on specific hardware that is implemented in the Arm Cortex®-M33 core, which is combined with a dedicated Secure instructions set. It allows the creation of multiple software security domains that restrict access to selected memory, peripherals, and I/O to trusted software without compromising the system's performance. The TrustZone technology enables secure and non-secure code to run on a single MCU.

MPLAB Harmony v3 is a flexible, fully integrated embedded software development framework for 32-bit microcontrollers (MCUs) and microprocessors (MPUs). MPLAB Harmony v3 includes the MPLAB Code Configurator (MCC) tool, a set of modular Peripheral Libraries (PLIBs), drivers, system services, middleware, and numerous example applications, all of which are designed to help you quickly and easily develop powerful and efficient embedded software for Microchip’s 32-bit PIC and SAM devices. Also, MPLAB Harmony v3 provides a TrustZone environment to develop security applications on different secured MCUs and MPUs like SAM L11, SAM A5D2 and SAM A5D4.

The application makes use of the [PIC32CK SG01 Curiosity Ultra Development Board](https://www.microchip.com/en-us/development-tool/ev33a17a) and the [I/O1 Xplained Pro Extension Kit](https://www.microchip.com/en-us/development-tool/ATIO1-XPRO) (sold separately).

The application includes Basic and Extended functionalities.

**Basic application:**

- The Secure mode application toggles an LED (LED0 toggles when the switch SW0 is pressed) on a timeout basis and the periodicity of the timeout will change from 500 milliseconds to one second, two seconds, four seconds, and back to 500 milliseconds every time you press the switch SW0 on the PIC32CK SG01 Curiosity Ultra Development Board.
- The Non-secure application requests the Secure mode application, reads the LED toggling rate, and prints on the serial terminal. The LED toggling rate data is transferred to the Non-secure mode application when it requests to Secure application through Non-Secure Callables (NSC).

**Extended application:**

- The Secure mode application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension Kit every 500 milliseconds. Further, the application writes the temperature readings to EEPROM and reads when a request is received from the Non-secure mode application. Also, a green LED (LED0) is toggled every time the temperature display request is received from the Non-secure mode application. The periodicity of the temperature values reading can be changed to 1 second, 2 seconds, 4 seconds, and back to 500 milliseconds whenever the user presses the switch SW0 on the PIC32CK SG01 Curiosity Ultra Development Board. The temperature readings are transferred to the Non-secure mode application when it requests to Secure the application through Non-Secure Callables (NSC).
- The Non-secure mode application requests the Secure mode application the temperature values and prints them on a serial console once it receives from the Secure mode application. Further, when it gets a request from the user (in the form of a key press on the serial console), it will request the Secure mode application to retrieve the last five stored temperature values in the EEPROM. The Non-secure application prints the last five stored temperature values on the console. Also, a red LED (LED1) is toggled every time the temperature values are read from EEPROM.

The application has two projects on Secure and Non-secure modes of PIC32CK SG01, that work together on the same MCU and offer security isolation between the trusted and the non-trusted resources of the device.

The Secure mode application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension Kit every 500 milliseconds. Additionally, the secure application writes the temperature readings to EEPROM and reads when a request is received from the Non-secure mode application. Also, an LED (LED0) is toggled every time the temperature is displayed on the serial console. The periodicity of the temperature values reading can be changed to 1 second, 2 seconds, 4 seconds, and back to 500 milliseconds every time the user presses the switch SW0 on the PIC32CK SG01 Curiosity Ultra Development Board. The temperature readings are transferred to a Non-secure mode application when it requests to secure application through Non-Secure Callables (NSC). By default LED toggling rate is displayed on the terminal, by pressing the switch SW1, the temperature sampling rate is displayed. Switch SW1 press interrupt to toggle from Basic Functionality to Extended Functionality and vice-versa.

The Non-secure mode application requests the Secure mode application to get the current temperature values and the Non-secure mode application prints them on a serial console. Further, when it receives a request from the user (in the form of a key press on the serial console), it requests a Secure mode application to retrieve the last five stored temperature values in the EEPROM. The Non-secure application prints the last five stored temperature values on the console.

The application you create will utilize:

- Secure PORT Pin to toggle the LED (By default, all PORT pins are secure)
- Secure SERCOM (configured as I²C) PLIB to read the temperature from a temperature sensor
- Secure Real-Time Clock (RTC) PLIB to periodically sample temperature sensor data
- Mix-Secure peripheral External Interrupt Controller (EIC) PLIB to change the periodicity of temperature sensor data read using switch SW0 press interrupt and switch SW1 press interrupt to toggle from Basic Functionality to Extended Functionality and vice-versa.
- Non-secure SERCOM (configured as Universal Synchronous Asynchronous Receiver Transmitter (USART)) and Non-secure Direct Memory Access (DMA) PLIBs to print the temperature values on a COM (serial) port terminal application running on a PC
- Non-secure PORT Pins (USART Pins only) to communicate with the serial terminal
- In the process, the lab will also demonstrate the use of callback functions.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://developerhelp.microchip.com/xwiki/bin/view/software-tools/harmony/pic32ck-trustzone-getting-started-training-module//" target="_blank">Arm® TrustZone® Technology Getting Started Application on PIC32CK SG01 (Cortex®-M33) MCUs </a>



## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
