---
title: Getting Started with USB on SAM MCUs Using MPLAB Harmony v3
parent: Middleware Examples
has_toc: false
nav_order: 2
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Getting Started with USB on SAM MCUs Using MPLAB Harmony v3

This tutorial shows you how to use MHC to create a simple USB CDC class serial terminal menu application and will help you get started on developing USB based applications for SAM MCUs using the MPLAB Harmony v3 software framework.

The training module application makes use of the [SAM E70 Xplained Evaluation Kit](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/ATSAME70-XPLD) and the [I/O1 Xplained Pro Extension Kit](https://microchipdeveloper.com/boards:io1-xpro-extension) (sold separately).

This application reads the current room temperature from the [AT30TSE758A](https://www.microchip.com/wwwproducts/en/AT30TSE758A) temperature sensor chip on the I/O1 Xplained Pro every second using I²C. This is indicated by a blinking orange LED on the I/O1 Xplained Pro. Further, it also writes these temperature values into the sensor chip's own integrated EEPROM using the same I²C peripheral instance. The application also uses an ADC channel to read the output voltage of the [TEMT6000](https://www.vishay.com/docs/81579/temt6000.pdf) ambient light sensor on the I/O1 Xplained Pro Extension Kit and displays it as a percentage of the sensor's full-scale output when requested through the serial terminal menu. This serial terminal menu is made available through the SAM E70 Xplained Evaluation Kit's Target USB port by configuring it as a USB CDC class device. This menu allows you to fetch temperature, light sensor data, and even toggle the LED on the SAME70 Xplained Evaluation Kit.

The application you create will utilize the following Harmony v3 components:

- I²C Driver (TWIHS) to fetch the temperature and access the EEPROM on the AT30TSE758A.
- Timer System Service (TC) to periodically sample temperature sensor data every second.
- CDC Function Driver of the USB Device Stack (USBHS) for the serial terminal menu accessible via PC.
- ADC Peripheral Library (AFEC) to read the TEMT6000 ambient light sensor output voltage.
- PIO Peripheral Library (PIO) to toggle some LEDs and multiplex pin functions.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:usb-getting-started-training-module" target="_blank">Getting Started with USB on SAM MCUs Using MPLAB® Harmony v3</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()  
