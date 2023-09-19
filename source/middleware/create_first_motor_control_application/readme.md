---
title: Create first Motor Control Application
parent: Middleware Examples
has_toc: false
nav_order: 24
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create your first Motor Control Application

This page shows you how to use MHC to create a motor control application Brushless DC (BLDC) block commutation using a hall sensor on a SAM E54 microcontroller.

This application reads the pattern from the hall sensor mounted on the motor shaft. Based on the hall pattern, the corresponding commutation is forced to the motor windings through three-phase inverters. The motor speed can be increased or decreased using the reference potentiometer in the MCLV-2 board. Two momentary switches are used, one for Start/Stop operation and the other for direction control (Forward/Reverse).  

The application will utilize:

- Position Decoder (PDEC) Peripheral Library (PLIB) to read the hall pattern from the hall sensor.
- Timer/Counter for Control Applications (TCC0) PLIB to create three pairs of Pulse Width Modulation (PWM) frequency for three-phase inverters and to trigger the ADC0 periodically.  
- Analog-to-Digital Converter (ADC0) PLIB to read the output voltage of potentiometer to determine the speed.  
- Timer/Counter (TC0) PLIB used as an internal 1 mS timer counter.  
- Timer/Counter (TC1) PLIB used as a timer to measure the time elapsed between two consecutive hall edges.  
- Event System (EVSYS) PLIB used as a traffic controller between TCC0 (event generator) and ADC0 (event user).

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:motor-control-getting-started-training-module" target="_blank">Create your first Motor Control Application using MPLAB Harmony v3</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()  
