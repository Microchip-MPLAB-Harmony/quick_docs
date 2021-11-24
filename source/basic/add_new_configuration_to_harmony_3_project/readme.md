---
title: Add a New Configuration to an Existing MPLAB Harmony v3 Project
parent:  Harmony Basics
has_toc: false
nav_order: 20
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Add a New Configuration to an Existing MPLAB Harmony v3 Project

MPLAB X IDE allows multiple build configurations for the same project. This feature is useful for the code that is
compiled on many hardware platforms. However, when you create a new project, a default configuration is created.  

Historically, MPLAB Harmony v2 projects typically used the build configuration feature of MPLAB X IDE to share
application code across different development boards or kits. However, MPLAB Harmony v3 example projects do not
use the build configuration option of MPLAB X IDE to enable sharing of application code across hardware platforms.  

MPLAB Harmony v3 contains example projects for many applications supporting different configurations. However, a
custom board will require its own configuration to run an existing example project.  

This guide describes porting an MPLAB Harmony v3 project to another configuration when using a different
development board. For example, the UART echo blocking application example, available for the PIC32MZ EF in
MPLAB Harmony package csp_apps_pic32mz_ef, is available for the PIC32MZ Embedded Connectivity with FPU
(EF) Starter Kit board. This document also describes how to use the source code files of the existing project on the
Curiosity PIC32MZ EF 2.0 Development Board.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://ww1.microchip.com/downloads/en/DeviceDoc/How-to-Add-a-New-Configuration-to-an-Existing-MPLAB-Harmony-v3-Project-DS90003304.pdf" target="_blank">How to Add a New Configuration to an Existing MPLAB Harmony v3 Project</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()
