---
title: TCP/IP Application Harmony2 to Harmony 3 Guide
parent: Migration
has_toc: false
nav_order: 5
---

# MPLAB Harmony 2 to Harmony 3 USB Application Migration Guide

This guide provides a step by step procedure to migrate USB applications from MPLAB® Harmony v2.xx to a v3.x.x framework. There are no API level differences between the MPLAB® Harmony v2.xx and v3.x.x USB Stacks. However, there may be API level changes in other components such as Clock, Timer, Ports etc. There are also differences in the MHC GUI. In order to migrate a USB application from MPLAB® Harmony v2.xx to v3.x.x, the user must recreate the application using MPLAB® Harmony v3.x.x MHC.

In this guide an existing MPLAB® Harmony v2.xx USB Device CDC single com port demonstration is used to show the step by step procedure to migrate to the MPLAB® Harmony v3.x.x framework. This guide demonstrates how to use the MHC to configure various modules such as Clock, Ports, USB Device Layer, USB Controller Driver, and CDC Function driver etc.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://github.com/Microchip-MPLAB-Harmony/usb/wiki/MPLAB-Harmony-2-to-Harmony-3-USB-Application-Migration-Guide" target="_blank">MPLAB Harmony 2 to Harmony 3 USB Application Migration Guide</a>


## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() 
