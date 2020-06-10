---
title: Create Hello World application on PIC MCUs
parent: Harmony Basics
has_toc: false
nav_order: 12
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Create "Hello World" application on PIC MCUs

## Introduction

<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank">MPLAB Harmony v3</a> is a software development framework consisting of compatible and interoperable modules that include peripheral libraries (PLIBs), drivers, system services, middleware and third-party libraries. The MPLAB Harmony Configurator (MHC) is a GUI-based tool that provides an easy way to enable and configure various MPLAB Harmony modules. The MHC is a plug-in to the MPLAB X Integrated Development Environment (IDE).  
This page describes how to create an application on a 32-bit PIC32 microcontroller (MCU) using MHC with MPLAB Harmony v3 modules. This application sends a “Hello World!” string to a console running on a computer. For this demonstration, the following MPLAB Harmony v3 modules are used and configured using the MHC:

- Clock PLIB using the Clock Manager to configure the microcontroller clock.
- GPIO PLIB using the Pin Manager to configure the microcontroller I/Os.
- UART PLIB to configure USART peripheral as serial port.

## Required Software
The instructions in this tutorial assume that you have already installed following software.

- <a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank">MPLAB X Integrated Development Environment </a>
- <a href="https://www.microchip.com/mplab/compilers" target="_blank">MPLAB XC32/32++ C Compiler</a>
- <a href="https://github.com/Microchip-MPLAB-Harmony/mhc" target="_blank">MPLAB Harmony Configurator</a>


## Required Hardware

The instructions in this tutorial use <a href="https://www.microchip.com/DevelopmentTools/ProductDetails/DM320209" target="_blank">Curiosity PIC32MZ EF 2.0 Development Board</a>. Similar kits will work similarly, but the setup and steps may not be exactly as described.

**Setup**: The following figure shows the hardware setup details:

- Connect Curiosity PIC32MZ EF 2.0 Development Board micro USB port to PC using a micro USB cable

<img src = "images/hardware_connection.png" width="680" height="300" align="middle">

## Procedure

### Step 1: Creating an MPLAB Harmony v3-based Project:

1. Launch MPLAB X IDE.
2. In MPLAB X IDE, select *File > New Project* (or click the New Project icon).
3. In the **New Project** window, select **Microchip Embedded** in the **Categories** pane and select **32-bit MPLAB Harmony 3 Project** in the **Projects** pane.  
**Note**: If the option 32-Bit MPLAB Harmony v3 Project is not available, install the MPLAB Harmony v3 Configurator plug-in from Tools > Plugins > Available Plugins before continuing with this demonstration.
<img src = "images/figure1_1.png" width="660" height="455" align="middle">

4. Click **Next**.
5. Under **Framework Selection**, in the **Manage Framework** section, enter the **Framework Path** (Path to the
folder in which the MPLAB Harmony v3 packages are downloaded). For this demonstration, the MPLAB
Harmony v3 packages are downloaded in the following location: *D:\microchip\github\h3*.
<img src = "images/figure1_2.png" width="680" height="500" align="middle">
**Note**: For this demonstration application, the following MPLAB Harmony v3 packages are required: **mhc**,
**dev_packs**, and **csp**. The MPLAB Harmony 3 Content Manager tool simplifies the downloading of the MPLAB
Harmony v3 packages. If these packages are not downloaded, then the user can use the <a href="https://github.com/Microchip-MPLAB-Harmony/contentmanager/wiki" target="_blank">MPLAB Harmony 3 Content Manager</a> tool to download them onto their computer.

6. Click **Next**.
7. Under **Project Settings**, in the **Name and Location** section, enter the following details:
- Location: Indicates the path to the root folder of the new project. All project files will be placed in this
folder. The project location can be any valid path, for example: *D:\microchip\github\h3\tech_brief*.
- Folder: Indicates the name of the MPLAB X IDE folder. Enter hello_world to create a hello_world.X
folder.
- Name: Enter name of the project as *hello_world_pic32mz_ef_curiosity2*. This name will be displayed in the
MPLAB X IDE.
- Path: The path information will be updated as and when users make changes to other fields.
<img src = "images/figure1_3.png" width="660" height="485" align="middle">  
**Note**: Click the **Show Visual Help** button to open a contextual help window for a detailed description of
various fields in the Project Settings.

8. Click **Next**.
9. Under the **Configuration Settings** section, enter the details as given below:
- **Name**: Enter the configuration name as **pic32mz_ef_curiosity2**.  
- **Target Device**: Choose **PIC32MZ2048EFM144**.
<img src = "images/figure1_4.png" width="570" height="420" align="middle">  
**Note**: Click the **Show Visual Help** button to open a contextual help window for a detailed description of
various fields in the Project Settings.  
10. Click **Finish** to launch the MHC.  
**Note**: After clicking the Finish button, if MHC does not launch, users can launch it by selecting *Tools > Embedded > MPLAB® Harmony 3 Configurator* from the MPLAB X IDE.
11. Before launching the MHC, the **Configuration Database Setup** window will be displayed, where the Device Family Pack (DFP) and Cortex Microcontroller Software Interface Standard (CMSIS) path can be changed, if required. For this demonstration, the default settings are used.
<img src = "images/figure1_5.png" width="670" height="170" align="middle">
12. Click **Launch**.
13. The MHC plug-in will open in a new window. The image below highlights different section available in the
MHC.
<img src = "images/figure1_6.png" width="670" height="360" align="middle">
**Note**: For this demonstration, Stand-alone mode is used for the MHC Window Manager by changing the settings in the MPLAB X IDE, by *selecting > Tools > Options > Plugins > MPLAB Harmony Configurator 3 > Window Manager*. If the Native Netbeans mode of the MHC is required, users can set it as default mode by configuring it.

### Step 2: Adding and configuring the MPLAB Harmony components:

1. From Tools, select Clock Configuration to launch the Clock Easy View.
<img src = "images/figure1_7.png" width="395" height="175" align="middle">  
The Clock Easy View window will be displayed inside the MHC Window.
2. In the Clock Easy View window, scroll to the right and verify that the SYSCLK is set to 200 MHz.
<img src = "images/figure1_8.png" width="580" height="615" align="middle">

3. To add and configure the UART Peripheral Library follow these steps:
- Under **Available Components**, expand **Peripherals** and then expand the options available for UART.  
- Double-click on UART6 to add it to the project graph  
<img src = "images/figure1_9.png" width="208" height="600" align="middle">

4.Select the **UART6** Peripheral Library in the **Project Graph**, and in the Configuration Options window.
Configure it as follows:
- Verify that the default baud rate is set to 115,200
<img src = "images/figure1_10.png" width="570" height="200" align="middle">
5. Configure the UART pins in the Pin Settings window. In the MHC, select *Tools > Pin Configuration* to open the
**Pin Settings window**.  
<img src = "images/figure1_11.png" width="394" height="175" align="middle">
6. The MHC Pin Settings window will open and display these options: Pin Diagram, Pin Table, and Pin Settings.  
<img src = "images/figure1_12.png" width="480" height="380" align="middle">  
**Note**: According to schematic of the Curiosity PIC32MZ EF 2.0 Development Board, the PICkit™ On Board 4 (PKOB4) can be used as Virtual Com Port to have serial communication between PIC32MZ EF device and connected computer console. For that, RF2 (Pin #79) of the PIC32MZ EF must be configured as U6TX.
7. Click the Pin Settings tab and configure the RF2 pin as U6TX.
<img src = "images/figure1_13.png" width="480" height="390" align="middle">
8. The same pin (RF2) can be configured by clicking the Pin Table tab.
<img src = "images/figure1_14.png" width="660" height="163" align="middle">  
**Note**: The demonstration will use the UART PLIB for printing messages on the serial terminal. Therefore, in the UART6 configuration, only the transmit pin is configured and the receive pin is not configured.


### Step 3: Generating the Code
1. In MHC click on the **Save MHC State** icon to save the MHC state before generating the code.  
<img src = "images/figure1_15.png" width="320" height="85" align="middle">

2. Save the configuration in its default location, when prompted.
<img src = "images/figure1_16.png" width="590" height="415" align="middle">

3. Click on the generate code icon to generate the code.  
<img src = "images/figure1_17.png" width="340" height="85" align="middle">

4. The Modified Configuration window is prompted, click Save to save the configuration.
<img src = "images/figure1_18.png" width="650" height="130" align="middle">

5. In the Generate Project window, click Generate to generate the code.
<img src = "images/figure1_19.png" width="540" height="550" align="middle">
6. The above step triggers these actions in MHC:
    - Generate the code as per the configurations done.
    - Place the generated code and required MPLAB Harmony framework files in the MPLAB Harmony project directory, in this case: *D:\microchip\github\h3\tech_brief\firmware\src*.
    - Add all generated codes and MPLAB Harmony framework files into the MPLAB Harmony project, as shown in the following figure.  
<img src = "images/figure1_20.png" width="260" height="414" align="middle">  
**Note**: The MPLAB Harmony project will be shown in another window as this project is in Standalone mode.

7. The generated code descriptions are as follows:  

    - definitions.h: Includes all the header files required for the project.
    - initialization.c: Initializes all the MPLAB Harmony modules used in the application.
    - interrupts.c: Contains the mapping of all the interrupt vectors on the selected device.
    - main.c: A function call to initialize the system present in this file. The user needs to develop their
application in this file.
    - peripheral: All peripheral source codes are added in this folder.  

**Note**: The MHC provides an option to change the generated file name, and if this option is not used, by default, the file name main.c is generated.  
<img src = "images/figure1_21.png" width="500" height="400" align="middle">

### Step 4: Developing and Running an Application
To develop and run an application, follow these steps:  

1. Developing an application: For this demo application, add the highlighted codes (as shown in image below) in the main.c file. This will send the “Hello World!” string to the console running on the PC. The following code is provided for convenience:  

    ```c
    uint8_t buffer[]= "Hello World!\r\n";

    UART6_Write(&buffer[0], sizeof(buffer));
    ```
    <img src = "images/figure1_22.png" width="620" height="420" align="middle">

2. Selecting Hardware Tool and Compiler: In the MPLAB X IDE Project Properties window perform these actions:  
3. Under Categories section, select Conf: (pic32mz_ef_curiosity2), and in the Configuration section, select the hardware tool and compiler toolchain.
<img src = "images/figure1_23.png" width="670" height="435" align="middle">  
4. Click **Apply**, and then click **OK**.
5. Connecting Hardware: Connect a micro-USB cable between the DEBUG USB on the board and the PC. This enables the programming of the microcontroller and provide a serial connection with the console device (computer).
<img src = "images/hardware_connection.png" width="670" height="350" align="middle">
6. Setting up the Serial Console: Open a terminal application, such as Tera Term on the PC and perform the serial port setup. Below is the default setup details for Tera Term.  
<img src = "images/figure1_25.png" width="640" height="335" align="middle">
7. Programing and Running the Application: Build and program the Curiosity PIC32MZ EF 2.0 Development Board by using the MPLAB X IDE.  
<img src = "images/figure1_26.png" width="285" height="50" align="middle">

8. Select MPLAB PKoB 4 under Curiosity/Starter Kits (PKOB4) when prompted.  
<img src = "images/pkob4_select.png" width="390" height="625" align="middle">

9. Observing the Output: Observe the “Hello World!” string on the console. If the desired output is not found on the console, press the **Reset** button on the Curiosity Development board to reset the device, and ensure that the UART message is communicated.  
<img src = "images/figure1_27.png" width="630" height="330" align="middle">

## Note
<span style="color:blue"> *This page has been verified with the following versions of software tools:*</span>  

 - [MPLAB Harmony v3 "csp" repo v3.7.1](https://github.com/Microchip-MPLAB-Harmony/csp/releases/tag/v3.7.1)
 - [MPLAB Harmony v3 "dev_packs" repo v3.7.0](https://github.com/Microchip-MPLAB-Harmony/dev_packs/releases/tag/v3.7.0)
 - [MPLAB Harmony v3 "mhc" repo v3.4.0](https://github.com/Microchip-MPLAB-Harmony/mhc/releases/tag/v3.4.0)
 - MPLAB Harmony Configurator Plugin v3.5.0
 - [MPLAB X IDE v5.40](https://www.microchip.com/mplab/mplab-x-ide)
 - [MPLAB XC32 Compiler v2.41](https://www.microchip.com/mplab/compilers)

 <span style="color:blue"> Because Microchip regularly update tools, occasionally there could be minor differences with the newer versions of the tools. </span>  


## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()  
