---
title: Create new TrustZone Project
parent: Harmony Basics
has_toc: false
nav_order: 15
---
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)



# Creating a New TrustZone Project
To create a new TrustZone project, in MPLAB® X IDE, Select File > New Project or click <img src = "images/btn_new_project.png">. The New Project wizard will open. Perform following steps:

1. Choose Project:
    - In the Choose Project pane, select the Microchip Embedded category.
    - In the Projects pane, select 32-bit MCC Harmony Project, then click Next.

    - <img src = "images/new_project_step1.png" width="730" height="500" align="middle">

    **Note**: If the 32-bit MCC Harmony Project type is not listed under the Microchip Embedded category, please download and install MPLAB® Code Configurator before continuing with these steps.
2. Framework Selection:
    - Provide the framework path where Harmony 3 repositories have been downloaded, then click Next.

    - <img src = "images/new_project_step2.png" width="750" height="550" align="middle">

3. Project Settings:
    - Location: Indicates the path to the root folder of the new project. All project files will be placed in this folder.
    - Folder: Indicates the name of the MPLAB® X IDE folder.
    - Name: Enter name of the project which you want to see in MPLAB® X IDE, click Next.
    - Path: The path information will be updated automatically as and when users make changes to other fields.

    - <img src = "images/new_trustzone_project_step3.png" width="750" height="550" align="middle">

    **Note**: Click the "Show Visual Help" button to open a contextual help window for a detailed description of various fields in the Project Settings.

4. Configuration Settings:
    - Name: Enter the configuration name.
    - Target Device: Choose target device
    - Click Finish button to launch MPLAB® Code Configurator (MCC). After clicking the Finish button, MCC will create Secure and Non-secure MPLAB® X Projects.

    - <img src = "images/new_trustzone_project_step4.png" width="750" height="550" align="middle">

    - The MCC plug-in will open inside MPLAB® X window
	
    - <img src = "images/trustzone_project.png" width="800" height="415" align="middle">

    - TrustZone Project uses two projects viz., **Secure** and **Non-Secure** Project that work together on the same MCU and offering security isolation between the Trusted and the Non-trusted resources in the device.
    - **Secure Project:**
        - Secure project contains harmony project file harmony.prj. And this project also contains a configuration file for both Secure and Non-secure project.
        - Secure project must be selected as Main Project to launch MCC.
        - Once the Harmony code is generated, Secure user application should be developed in secure "main.c".
		- "nonsecure_entry.c" and "nonsecure_entry.h" files should be used for the Non-secure to Secure function calls.
        - Secure project is a loadable project from the Non-secure project. When Secure Project builds it generates Secure Gateway (SG) library ([configuration name]_Secure_sg_veneer.lib) which will be used by the Non-secure project while building the Non-secure project.
    - **Non-secure Project:**
        - Once the Harmony code is generated, Non-secure user application should be developed in Non-secure "main.c".
        - When Non-secure Project builds, it first builds Secure Project and then Non-secure project and  generates target binaries to be executed on the device.

## Running TrustZone Project
Following steps need to be done to run TrustZone project:
- In MPLAB® X Non-secure Project properties, appropriate compiler, hardware tools and DFP should be selected as shown in the figure below.

    - <img src = "images/nonsecure_project_properties.png" width="750" height="480" align="middle">

- Select Non-secure Project as Main Project, Non-secure Project can be then build and programmed using MPLAB® X "Make and Program Device Main Project" option.

## Note
<span style="color:blue"> *This page has been verified with the following versions of software tools:*</span>

- [MPLAB X IDE v6.15](https://www.microchip.com/mplab/mplab-x-ide)
- [MPLAB XC32 Compiler v4.30](https://www.microchip.com/mplab/compilers)
- [MPLAB Code Configurator v5.3.7](https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator) 
- MCC Harmony v1.3.2
- [MPLAB Harmony v3 "csp" repo v3.18.0](https://github.com/Microchip-MPLAB-Harmony/csp/releases/tag/v3.18.0)
- [MPLAB Harmony v3 "dev_packs" repo v3.18.0](https://github.com/Microchip-MPLAB-Harmony/dev_packs/releases/tag/v3.18.0)

<span style="color:blue"> Because Microchip regularly update tools, occasionally there could be minor differences with the newer versions of the tools. </span>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
