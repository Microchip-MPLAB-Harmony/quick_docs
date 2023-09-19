---
title: Secure Boot on PIC32CM LS60 Curiosity Pro Evaluation Kit using MPLAB Harmony v3
parent: Middleware Examples
has_toc: false
nav_order: 6
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Secure Boot on PIC32CM LS60 Curiosity Pro Evaluation Kit using MPLAB Harmony v3

This tutorial shows how to use the Secure Boot feature on the PIC32CM LS60 microcontroller (MCU) using ATECC608B to create a Secure Bootloader and an application that is loaded using the Secure Bootloader. This tutorial helps you get started in developing secure applications on PIC32CM LS60 MCUs using Microchip's Trust Platform Design Suite (TPDS) and MPLAB Harmony v3 software framework. The project you create will run on the PIC32CM LS60 Curiosity Pro Evaluation Kit (EV76R77A).  

The application demonstrates the development of two projects.

- A Secure Bootloader
- A Test Application

**Secure Bootloader:**
The Secure Bootloader on PIC32CM LS60 provides a layer of security to the boot process by checking the integrity of the Bootloader before moving to program a firmware image into the device's Flash memory. This helps prevent unauthorized access and malicious code from being loaded onto the device.
The Secure Bootloader implements a security layer through the Secure Boot feature on PIC32CM LS60 devices. The process typically involves:

1. Storing cryptographic keys: Public and private key pairs are generated, with the private key securely stored in the secure element and the public key programmed into the MCU.
2. Signing: The bootloader code is signed using the private key, creating a digital signature that is appended to the bootloader code image.
3. Verification: When the MCU boots, the Bootloader's digital signature is checked using the public key stored in the device. If the signature is valid, it confirms the Bootloader's integrity and authenticity, allowing it to execute and load the application firmware (if needed).  

**Test Application:**
The test application firmware is sent by a host PC (running a script) interfaced to the PIC32CM LS60 MCU through UART. The test application image is received and loaded by the Secure Bootloader.

The test application you create will utilize the following peripherals:

- SERCOM2 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)) peripheral library to communicate with the PC utility for receiving the test application image using the Bootloader library.
- NVMCTRL peripheral library to read or write the firmware image from the Flash memory.


For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:secure-boot-application-on-pic32cm-ls60" target="_blank">Secure Boot on PIC32CM LS60 Curiosity Pro Evaluation Kit using MPLAB Harmony v3e </a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()  
