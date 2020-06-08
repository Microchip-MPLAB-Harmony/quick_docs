---
title: Open an Existing Harmony 3 Project
parent: Basic
has_toc: false
nav_order: 13
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Open an Existing Harmony 3 Project

This page shows you how to open one of the many demonstration application projects that are included in the MPLAB® Harmony framework.

Before doing this, you'll need to do the following:

- <a href="https://microchipdeveloper.com/mplabx:installation" target="_blank">Install MPLAB X IDE</a>
- <a href="https://microchipdeveloper.com/xc32:installation" target="_blank">Install MPLAB XC32 Compiler</a>
- <a href="https://microchipdeveloper.com/harmony3:mhc-overview#install" target="_blank">Install the MPLAB Harmony Configurator (MHC)</a>
- <a href="https://github.com/Microchip-MPLAB-Harmony/contentmanager/wiki" target="_blank">Download the MPLAB Harmony Framework</a> 

## Steps

1. In the MPLAB X IDE, select **File** > **Open Project**.
<img src = "images/existingproj1.png" width="440" height="203" align="middle">

2. Demonstration applications come with most of the libraries. These can be found in each library's **apps** folder. Browse to the **firmware** folder (as shown below) to find all evaluation boards that support the application. Select your evaluation board and click **Open Project**.  
<img src = "images/existingproj2.png" width="700" height="540" align="middle">

3. After the project opens, start MHC. In the MPLAB X IDE, select **Tools  > Embedded > MPLAB® Harmony 3 Configurator**.  
<img src = "images/existingproj3.png" width="470" height="240" align="middle">


4. Select the path to the folder containing the MPLAB Harmony framework and click **Launch**.
<img src = "images/existingproj4.png" width="700" height="300" align="middle">


5. The **Configuration Database Setup** window opens. You shouldn't have to change anything in this window. Click Launch.  
Please be patient while waiting for the last window to open. It will ask if you want to open the default saved state file. This file is used to save all selections made in MHC for the project you are opening. Click **Open**.  
You can now use the MPLAB Harmony Configurator. Please see the MHC Wiki for instructions on how to use it.
<img src = "images/existingproj5.png" width="700" height="415" align="middle">


Note: You can save or load an MHC configuration at any time. The default name of the MHC state file is:
```text
<MPLAB X project configuration name>.xml  
```
It can be found in the following folder:
```text
…\<project name>\firmware\src\config\<project configuration name>\.  
```

If you are not using MPLAB X Project Configurations, the MHC state file can be found in the following folder:
```text
…\<project name>\firmware\src\config\default\default.xml
```

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()  
