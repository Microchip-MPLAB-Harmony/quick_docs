---
title: Arm TrustZone Getting Started Application on SAM L11 MCUs
parent: Peripheral Libraries
has_toc: false
nav_order: 13
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Arm TrustZone Getting Started Application on SAM L11 MCUs

This tutorial shows you how to create an Arm® TrustZone® feature application on SAM L11 microcontroller (MCU) using MPLAB Harmony v3 software framework.

The SAM L11 MCU is the implementation of the Arm TrustZone 45r for an ARMv8-M device. TrustZone for an ARMv8-M device is based on a specific hardware that is implemented in the Arm Cortex®-M23 core, which is combined with a dedicated Secure instructions set. It allows the creation of multiple software security domains that restricts access to selected memory, peripherals, and I/O to trusted software without compromising the system performances. The TrustZone technology enables secure and non-secure code to run on a single MCU.

For the detailed explanation of security features available on the Microchip SAM L11 MCU, go through the [SAM L11 Security Reference Guide](http://ww1.microchip.com/downloads/en/AppNotes/SAM-L11-Security-ReferenceGuide-AN-DS70005365A.pdf).

MPLAB® Harmony v3 is a flexible, fully integrated embedded software development framework for 32-bit microcontrollers (MCUs) and microprocessors (MPUs). MPLAB Harmony v3 includes the MPLAB Harmony Configurator (MHC) tool, a set of modular Peripheral Libraries (PLIBs), drivers, system services, middleware, and numerous example applications, all of which are designed to help you quickly and easily develop powerful and efficient embedded software for Microchip’s 32-bit PIC® and SAM devices. Also, the MPLAB Harmony v3 provides a TrustZone enviroment to develop security applications on different secured MCUs and MPUs like SAM L11, SAM A5D2 and SAM A5D4.

The application makes use of the [SAM L11 Xplained Pro Evaluation Kit](https://microchipdeveloper.com/boards:sam-l11-xpro) and the [I/O1 Xplained Pro](https://microchipdeveloper.com/boards:sam-l11-xpro#io1-xpro-extension) Extension Kit (sold separately).

The application has two projects pertaining to Secure and Non-secure modes of SAM L11, that work together on the same MCU and offers security isolation between the trusted and the non-trusted resources of the device.

The Secure mode application reads the current room temperature from the temperature sensor on the I/O1 Xplained Pro Extension Kit every 500 milliseconds. Additionally, the secure application writes the temperature readings to EEPROM and reads when a request received from the Non-secure mode application. Also, an LED (LED0) is toggled every time the temperature is displayed on the serial console. The periodicity of the temperature values reading can be changed to 1 second, 2 seconds, 4 seconds, and back to 500 milliseconds every time the user presses the switch SW0 on the SAM L11 Xplained Pro Evaluation Kit. The temperature readings are transferred to Non-secure mode application when it requests to secure application through Non Secure Callables (NSC).

The Non-secure mode application requests the Secure mode application to get the current temperature values and the Non-secure mode application print them on a serial console. Further, when it receives a request from the user (in the form of a key press on the serial console), it requests Secure mode application to retrieve the last five stored temperature values in the EEPROM. The Non-secure application prints the last five stored temperature values on the console.

The application you create will utilize the following peripherals:

- Secure PORT Pin to toggle the LED (By default, all PORT pins are secure)
- Secure SERCOM (configured as I²C) PLIB to read the temperature from a temperature sensor
- Secure Real-Time Clock (RTC) PLIB to periodically sample temperature sensor data
- Secure External Interrupt Controller (EIC) PLIB to change the periodicity of temperature sensor data read using switch SW0 press event
- Non-secure SERCOM (configured as Universal Synchronous Asynchronous Receiver Transmitter (USART)) and Non-secure Direct Memory Access (DMA) PLIBs to print the temperature values on a COM (serial) port terminal application running on a PC
- Non-secure PORT Pins (USART Pins only) to communicate with the serial terminal

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:saml11-trustzone-getting-started-training-module" target="_blank">Arm TrustZone Getting Started Application on SAM L11 MCUs </a>



## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()
