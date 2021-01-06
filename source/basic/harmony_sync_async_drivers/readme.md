---
title: Differences Between Synchronous and Asynchronous Drivers
parent:  Harmony Basics
has_toc: false
nav_order: 17
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Differences Between MPLAB Harmony v3 Synchronous and Asynchronous Drivers
MPLAB Harmony v3 drivers provide a simple and abstracted ‘C’ language interface to the peripherals and other
system resources. Some functions are similar across on all the device drivers, while other functions are unique to a
specific driver or peripheral. Driver interface functions are generally independent of the details of how a given
peripheral is implemented on any specific hardware, or how many instances of that peripheral exist in each system.
Applications can control and easily interact with the peripherals by calling the driver interface.

MPLAB Harmony v3 allows users to configure the drivers in any one of these operating modes: Synchronous
(Blocking) or Asynchronous (Non-Blocking).
* **Asynchronous Mode**  - Non-blocking Application Program Interfaces (APIs).  - Allows queuing of multiple requests. Each instance of an Asynchronous driver has a dedicated queue.  - Works seamlessly in bare-metal and RTOS environment.  - Interrupt and thread-safe.
* **Synchronous Mode**  - Blocking APIs  - Support only RTOS environment  - Interrupt and thread-safe

This guide describes Synchronous and Asynchronous operating modes and how to use them.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="http://ww1.microchip.com/downloads/en/DeviceDoc/The-Difference-Between-MPLAB-Harmonyv3-Synchronous-and-Asynchronous-Drivers-and-When-to-Use-DS90003269A.pdf" target="_blank">The Differences Between MPLAB Harmony v3
Synchronous and Asynchronous Drivers and When to Use
Them</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()