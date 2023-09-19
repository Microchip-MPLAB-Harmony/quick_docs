---
title: MPLAB Harmony v3 Project Manifest Feature
parent:  Harmony Basics
has_toc: false
nav_order: 21
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# MPLAB Harmony v3 Project Manifest Feature

The MPLAB® Harmony v3 software framework is distributed as packages on GitHub under the [Microchip MPLAB
Harmony project](https://github.com/Microchip-MPLAB-Harmony). MPLAB Harmony v3 provides several software packages (as GitHub repositories), including device setup repositories (csp, core, dev_packs, mhc, etc.), technology-specific repositories (usb, net, wireless, etc.), and reference application (reference_apps) repositories. In addition to the device or technology-specific libraries, these repositories also have application examples.

The release tags identify the MPAB Harmony v3 packages released on GitHub. Microchip regularly updates the
packages for new feature additions and issue fixes with a new release. Each new release has a dedicated release
tag.  

An MPLAB Harmony v3 application is developed using these packages. At a minimum, the application would use
device-specific repositories such as csp, dev_packs, and mhc. If the application is extensive and has feature-rich
functionality, it could use several packages for development.  

An application example released in an MPLAB Harmony v3 package is developed on specific released versions of
the dependent repositories. For example, the application [Getting Started Application on Curiosity PIC32MZ EF 2.0
Development Board](https://github.com/Microchip-MPLAB-Harmony/reference_apps/releases/download/v1.2.0/getting_started_ext.zip) was developed using csp v3.8.3, dev_packs v3.8.0 and mhc v3.6.5 packages.

As Microchip provides newer releases, the version number of the repositories used to develop this application are
upgraded. There could be situations wherein the user would like to develop the project with the same dependent
package version they initially created or received. This document explains how to develop an application with the
same dependent packages used when it was created or received.  

**Note:**  In this document, the phrase code generation tool refers to any one of the two Microchip code generation
tools: MPLAB Harmony Configurator (MHC) and MPLAB Code Configurator (MCC). At the time of publication of this
guide, the MPLAB Harmony v3 library code can be generated using either of these tools, however, in the future,
only MCC will support MPLAB Harmony v3 code generation.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://ww1.microchip.com/downloads/en/DeviceDoc/How-to-Use-the-MPLAB-Harmony-v3-Project-Manifest-Feature-DS90003305.pdf" target="_blank">How to Use the MPLAB Harmony v3 Project Manifest
Feature</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
