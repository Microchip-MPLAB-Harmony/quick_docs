---
title: Create First Harmony 3 Project
parent: Harmony Basics
has_toc: false
nav_order: 10
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

<span style="color:blue">

### Note
**MPLAB Harmony v3 is now configurable through MPLAB Code Configurator (MCC). Though the instructions in this guide are for the MPLAB Harmony Configurator (MHC), the flow and experience of creating a project, configuring peripherals, and generating code using MCC is similar. Refer to the below links for specific instructions to use MPLAB Harmony v3 with MCC.**
- [Create a new MPLAB Harmony v3 project using MCC](https://microchipdeveloper.com/harmony3:getting-started-training-module-using-mcc)
- [Update and Configure an Existing MHC-based MPLAB Harmony v3 Project to MCC-based Project](https://microchipdeveloper.com/harmony3:update-and-configure-existing-mhc-proj-to-mcc-proj)
- [Getting Started with MPLAB Harmony v3 Using MPLAB Code Configurator](https://www.youtube.com/watch?v=KdhltTWaDp0)

</span>

# Create First MPLAB Harmony 3 Project

## Overview
The purpose of this tutorial is to show you how to use Microchip MPLAB® Harmony 3 to create a simple “heartbeat” LED application that flashes an LED using the MPLAB® X IDE and the MPLAB® Harmony Configurator (MHC). As a bonus, you can reuse the heartbeat LED application in future projects as a simple indicator of system health. This tutorial focuses on direct use of MPLAB® Harmony peripheral libraries to build an application. If you are interested in using interoperable MPLAB® Harmony drivers, services, or middleware in your application, please see “Creating Your First Project – Harmony” when you’ve finished with this tutorial.
The application can be defined by the following flowchart:

<img src = "images/flowchart.png" width="300" height="330" align="middle">

## Required Software
The instructions in this tutorial assume that you have already installed following software.

- <a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank">MPLAB X Integrated Development Environment</a>
- <a href="https://www.microchip.com/mplab/compilers" target="_blank">MPLAB XC32/32++ C Compiler</a>
- <a href="https://github.com/Microchip-MPLAB-Harmony/mhc" target="_blank">MPLAB Harmony Configurator</a>

## Required Hardware
The instructions in this tutorial use <a href="https://www.microchip.com/developmenttools/ProductDetails/atsamc21n-xpro" target="_blank">SAMC21N Xplained Pro Evaluation Kit</a>and it has one Yellow Color user LED (PC05) connected GPIO. Similar kits will work similarly, but the setup and steps may not be exactly as described.

**Setup**: The following figure shows the hardware setup details:

- Connect SAMC21N Xplained Pro Evaluation Kit micro USB port to PC using a micro USB cable

    <img src = "images/hardware_setup.png" width="470" height="520" align="middle">

## Procedure
The following are the steps to create, generate, build and flash LED Blinking application. Before proceeding, make sure you have downloaded the required Harmony 3 packages (for directions, the MPLAB® Harmony Configurator (MHC) User’s Guide) and setup the required hardware as shown previously.

## Create a new project
1. Open the MPLAB® X IDE.
2. Create a New Project by clicking the New Project icon <img src = "images/btn_new_project.png"> or by selecting File > New Project.
3. In the New Project window select 32-Bit MPLAB® Harmony 3 Project.
4. Click Next.

    <img src = "images/new_project_step1.png" width="727" height="500" align="middle">

    **Note**: If the option 32-Bit MPLAB Harmony v3 Project is not available, install the **MPLAB® Harmony 3 Launcher** plug-in from Tools > Plugins > Available Plugins before continuing with this demonstration.
5. Enter the path to the folder in which you downloaded the MPLAB® Harmony 3 packages in the Framework Path edit box.

    <img src = "images/new_project_step2.png" width="684" height="500" align="middle">

6. In the Project Setting dialog window, fill in or select the information needed as follows:
    - Location: Create a “**MyBlinky**” folder in the location of your choice.
    - Folder: Project Folder name i.e. “**sam_c21n_xpro**”
    - Name: Project Name i.e. “**my_blinky_sam_c21n_xpro**”

    <img src = "images/new_project_step3.png" width="685" height="500" align="middle">

7. In the Configuration Settings dialog window, enter the configuration name as “**sam_c21n_xpro**” and select the Target Device **ATSAMC21N18A** from the drop-down menu as shown below.

    <img src = "images/new_project_step4.png" width="685" height="500" align="middle">

8. Click **Finish**.
9. When the Configuration Database Setup dialog appears, just click Launch as shown below to open MPLAB® Harmony Configurator plugin. If the below dialog window doesn’t appear then MHC can be launched by selecting MPLAB® Harmony 3 Configurator under Tools ? Embedded.

    <img src = "images/new_project_step5.png" width="700" height="165" align="middle">

## Setup MPLAB® Harmony Project Configurator to Generate Code
1. From the “**Available Components**” panel of MHC (on the left side of the MHC window), drag and drop the TC0 peripheral into the Components Graph:
    <img src = "images/setup_step1.png" width="649" height="450" align="middle">

2. Click on the “**TC0**” component and configure as below and in the figure:

    - Select Prescaler value to “**Prescaler: GCLK_TC/1024**”
    - Set Timer Period (Milli Sec) to “**500**”

    <img src = "images/setup_step2.png" width="649" height="319" align="middle">

    This will toggle the LED every 0.5 seconds, producing a LED blink every second.

3. Launch the Pin Configuration manager from the MHC’s Tools menu:

    <img src = "images/setup_step3.png" width="385" height="361" align="middle">

4. Setup pin “**PC05**” as the board’s **LED**, set custom name as “LED” and Direction as “**Out**”:

    <img src = "images/setup_step4.png" width="898" height="316" align="middle">

    This is necessary because the project doesn’t use a Board Support Package (BSP).

5. Generate the application’s code for the first time.

6. Select the Generate Code button of MHC’s window <img src = "images/btn_generate.png">


7. Save the project’s configuration (any name will do for the .xml file):

    <img src = "images/setup_step5.png" width="597" height="119" align="middle">

    <img src = "images/setup_step6.png" width="603" height="440" align="middle">

8. Select default as the Merge Strategy (i.e. USER_ALL) and click Generate

    <img src = "images/setup_step7.png" width="603" height="605" align="middle">

    Now the project’s initial software has been configured.

    **Note**: Here is a brief explanation of the different merge strategies that are available:
    - **ALL**: The user will be prompted with a merge window for all generated files. This includes files that have no user modifications but are changed because of changes in MHC configuration or component updates. (This choice is always the safest.)
    - **USER_ALL**: The user will always be prompted with a merge window for all generated files that contain user modifications.
    - **USER_RECENT**: The user will be prompted with a merge window for all generated files that contain user modifications.
    - **OVERWRITE**: All generated file content will be replaced by the contents of this generate operation. All user changes will be overwritten.

9. Let’s examine the software just created in the Projects panel of MPLAB® X IDE Header Files are shown on the top and Source Files are shown on the bottom.

    **Note:** The icons used in this picture of the project’s organization make it seem like the files of the project are organized this way on disk. In fact, this is a virtual organization of these files, not an actual one. On disk, the source and header files are not separated.
    The following table describes the Header and Source files generated from the sample project:

    |  # |  Source File | Descriptions  |
    | ---|---|---|
    |  1 |definitions.h	   |Provides configuration-specific definitions   |
    |  2 |exceptions.c	   |Implements exception handlers    |
    |  3 |initialization.c	   |Implements SYS_Initialize to initializes all libraries and applications   |
    |  4 |interrupts.c	   |Implements the interrupt vectors   |
    |  5 |peripheral [libraries]	   | Implements peripheral libraries used by the project   |
    |  6 |startup.c	   | Startup code for the application  |

    If you click on the Files tab you will see the actual organization of these files on your drive:

    <img src = "images/setup_step9.png" width="310" height="480" align="middle">

## Adding Code to main.c
Double click on main.c to bring up an editor window and update it to obtain the following code:

```c
#include "definitions.h" // SYS function prototypes

static bool volatile bToggleLED = false;

// This function is called after period expires
void TC0_CH0_TimerInterruptHandler(TC_TIMER_STATUS status, uintptr_t context)
{
    bToggleLED = true;
}

// *****************************************************************************
// *****************************************************************************
// Section: Main Entry Point
// *****************************************************************************
// *****************************************************************************

int main ( void )
{
    // Initialize all modules
    SYS_Initialize(NULL);

    // Register callback function for CH0 period interrupt
    TC0_TimerCallbackRegister(TC0_CH0_TimerInterruptHandler, (uintptr_t)NULL);

    // Start the timer channel 0
    TC0_TimerStart();

    while ( true )
    {
        if ( bToggleLED )
        {
            bToggleLED = false;
            LED_Toggle();
        }
    }

    // Execution should not come here during normal operation
    return EXIT_FAILURE;
}
```
If you do a control click on “LED_Toggle()” the editor will bring up where this token is defined in the file plib_port.h:

    <img src = "images/code1.png" width="700" height="150" align="middle">

    <img src = "images/code2.png" width="700" height="210" align="middle">

## Upload project to SAMC21N Xplained pro Evaluation Kit
1. Do a right mouse click on the project’s name and bring up the Project Properties dialog:

    <img src = "images/upload1.png" width="347" height="307" align="middle">

2. Under Categories section, select Conf: (sam_c21n_xpro), and in the Configuration section, select the hardware tool and XC32 Compiler toolchain (here v2.41). Click Apply, and then click OK

    <img src = "images/upload2.png" width="800" height="513" align="middle">

3. Build and run the project: The board’s LED should flash with a 1 second period

    <img src = "images/upload3.png" width="170" height="68" align="middle">

We have now implemented a heartbeat for future applications. The LED blinking indicates that the application hasn’t frozen or isn’t stuck in a while(1){} loop (e.g.: assert or exception).

## Result
If configured correctly, the LED PC05 on the <a href="https://www.microchip.com/developmenttools/ProductDetails/atsamc21n-xpro" target="_blank">SAMC21N Xplained Pro Evaluation Kit</a> should now flash ON/OFF at **500 ms** intervals.

## Note
<span style="color:blue"> *This page has been verified with the following versions of software tools:*</span>

- [MPLAB Harmony v3 "csp" repo v3.10.0](https://github.com/Microchip-MPLAB-Harmony/csp/releases/tag/v3.10.0)
- [MPLAB Harmony v3 "dev_packs" repo v3.10.0](https://github.com/Microchip-MPLAB-Harmony/dev_packs/releases/tag/v3.10.0)
- [MPLAB Harmony v3 "mhc" repo v3.8.2](https://github.com/Microchip-MPLAB-Harmony/mhc/releases/tag/v3.8.2)
- MPLAB Harmony 3 Launcher Plugin v3.6.4
- [MPLAB X IDE v5.50](https://www.microchip.com/mplab/mplab-x-ide)
- [MPLAB XC32 Compiler v3.01](https://www.microchip.com/mplab/compilers)

<span style="color:blue"> Because Microchip regularly update tools, occasionally there could be minor differences with the newer versions of the tools. </span>

## References
- <a href="https://www.microchip.com/developmenttools/ProductDetails/atsamc21n-xpro" target="_blank">SAMC21N Xplained Pro Evaluation Kit User Guide and Datasheet</a>
- <a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank">MPLAB X IDE User’s Guide</a> see Documentation section at bottom of the page.
    - <a href="http://www.microchip.com/mymicrochip/filehandler.aspx?ddocname=en556757" target="_blank">User’s Guide direct download</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()
