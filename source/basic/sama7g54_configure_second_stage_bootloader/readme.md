---
title: Open an Existing Harmony 3 Project
parent: Harmony Basics
has_toc: false
nav_order: 13
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)


### Note:
<span style="color:blue"> **This guide will teach you how to configure the second stage bootloader for SAMA7G54 based MPUs.**
- [SAMA7G54 data sheet](https://www.microchip.com/en-us/product/SAMA7G54)
- [SAMA7G54 Evaluation kit](https://www.microchip.com/en-us/development-tool/EV21H18A)

## Introduction
This training module describes the following for at91bootstrap, a second-stage bootloader for Microchip Technology Arm®-based Microprocessor Units (MPU), 
  where to get the source code, how to configure, compile and debug using MPLAB® X IDE on windows host.

* The following solution is tested based on **at91bootstrap version 4.0.5**.

* The at91bootstrap bootloader can be stored in external NVMs like (SD Memory Card, Embedded Multimedia Card (eMMC), QSPI Flash).
  The first-stage bootloader (ROM Boot Code) will load at91bootstrap from external NVM depending on the value of the Boot Configuration Packet. 

* [Click here to learn how to configure Boot Configuration Packet for SAMA7G54.](../sama7g54_configure_first_stage_bootloader/readme.md)


* at91bootstrap if configured to do so, will initialize the following peripherals and memory controllers:
  * **Advanced Interrupt Controller (AIC)**
  * **Peripheral I/O Controller (PIO)**
  * **Power Management Controller (PMC)**
  * **Clock Generator (CKGR)**
  * **Static Memory Controller (HSMC)**
  * **NAND Flash Controller (NFC)**
  * **Multiport DDR-SDRAM Controller (MPDDRC)**
  * **Secure Digital Multimedia Card Controller (SDMMC)**

* at91bootstrap can be configured to load one of the following from external NVM into external volatile memory (DRAM) (main memory) and jump to:
  * **The third-stage bootloader (for example, Das U-Boot or BusyBox).**
  * **The Linux® kernel directly, thus it does not require a third-stage bootloader.**
  * **The Real Time Operating System (RTOS application).**
  * **Turn over control to the debugger (JTAG-Debugging alone).**
  * **The main program (Baremetal application).**

* at91bootstrap is written and maintained by Microchip Technology and hosted on GitHub.


## Required software and hardware tools
<details>
  <summary> Details
</summary>  <br>
This document is written with the assumption that the user is aware of the external NVMS & DDR memory available in the respective SAMA7G54 boards (Like Evaluation Kits, SIP or SOM) by reading the respective user guide.

* To build/debug at91bootstrap using MPLAB® X IDE on windows host, the following tools should be installed properly:
  * [Download and install MPLAB® X IDE.](https://www.microchip.com/en-us/tools-resources/develop/mplab-x-ide)
  * [Download and install XC32 Compiler.](https://www.microchip.com/en-us/tools-resources/develop/mplab-xc-compilers)
* User can use below hardware tools:
  * [SAMA7G54 Evaluation kit.](https://www.microchip.com/en-us/development-tool/EV21H18A)
  
</details> 

## Getting at91bootstrap Source Code
<details>
  <summary> Details
</summary>  <br>
  
  1. **Create a Project Directory:** Create a project directory to keep all the sources together for a given project. For the purpose of this tutorial topic, the created project directory is  **Harmony3**. 

  2. **Get at91bootstrap:** Get the complete source code of at91bootstrap by either of the following ways:
      * If you have git installed, clone the repo into the project directory by using the command:
         
		 $ git clone git@https://github.com/linux4sam/at91bootstrap
      * If you don't have git installed, then
        [Download at91bootstrap](https://github.com/linux4sam/at91bootstrap) and unzip into your project directory.
        <img src = "images/directory.png" align="middle">

</details> 
 
## Configure, build and debug at91bootstrap
<details>
  <summary> Details
</summary>  <br>
at91bootstrap can be configured to load the final application from any of the external NVMs available on the board like QSPI, e.MMC, SD CARD to DRAM and execute from it.

User should follow the below steps to build the at91bootstrap as per their external NVM preference:
1. Preparing the build Environment.
2. Configure the at91bootstrap.
3. Create a Custom Board Configuration.
4. Building the at91bootstrap.
5. Debugging the at91bootstrap.

### 1. Preparing the build Environment
<details>
  <summary> Details
</summary>  <br>
  
  1.1. **Open at91Bootstrap project:** To begin, launch MPLAB® X IDE and then go to File --> Open Project -->choose downloaded at91bootstrap project.
      <img src = "images/1_1.png" align="middle">

    Now set it as main project.
  <img src = "images/1_1a.png" align="middle">

  1.2. **Compiler setting:** User can use XC32 compiler to build at91bootstrap.   
       Go to Project --> Properties --> Makefile ---> Copy the XC32 installation path and update it in the build/debug and clean command --> Apply ---> ok.

   E.g. Build/Debug command: make CROSS_COMPILE="C:/Program Files/Microchip/xc32/v4.30/bin/bin/pic32c-"

       Clean command: make mplabclean CROSS_COMPILE="C:/Program Files/Microchip/xc32/v4.30/bin/bin/pic32c-"

   <img src = "images/1_2.png" align="middle">
 
 
</details>

### 2. Configure the at91bootstrap
<details>
  <summary> Details
</summary>  <br>
The at91bootstrap can be configured to load from any one of the user-preferred NVMs by using KCONFIG. 

Depending on your hardware setup (sama7g54<board>) and the preferred NVMs (Either QSPI or e.MMC or SD-Card) or to debug on MPLAB® X IDE, select one of the below options explained in the following sub-chapters.


**Legendry:** board can be evaluation Kit (ek). E.g., sama7g54-ek.

   2.1. Configure at91bootstrap for debug use with MPLAB® X IDE.
   
   2.2. Configure at91bootstrap to load application from QSPI.
   
   2.3. Configure at91bootstrap to load application from e.MMC.
   
   2.4. Configure at91bootstrap to load application from SDCARD.

In addition to the above configuration for the external NVMs, user can also customize the default configuration like external RAM size and type, external clock source etc. which is explained in section 2.5.

#### 2.1 Configure at91bootstrap for debug use with MPLAB® X IDE
<details>
  <summary> Details
</summary>   <br>
The at91bootstrap built from sama7g54<board>_bkptnone_defconfig can only be used for debugging the application using MPLAB® X IDE.

**Note:** bkptnone_defconfig configures the at91bootstrap to continuously loops at the end of its execution, hence IDE can take over control (time-out message) and now continue to download the application in the user space. Therefore, this bkptnone_defconfig should be used only to debug the application using MPLAB X IDE.


To do this, go to
Project --> Properties --> Kconfig --> load --> **project directory** --> configs --> **sama7g5ek_bkptnone_defconfig** --> Open.

<img src = "images/2_1a.png" align="middle">

This will do the kconfig for building at91bootstrap for debug use with MPLAB X IDE.

After opening the configuration file, the Kconfig will be as shown below.
<img src = "images/2_1b.png" align="middle">

Now Click **Apply** --> **OK**.
</details>

#### 2.2. Configure at91bootstrap to load application from QSPI
<details>
  <summary> Details
</summary>  <br>

at91bootstrap can be configured to load the harmony application from QSPI into external volatile memory (DRAM) as follows.

To do this, go to
Project --> Properties --> Kconfig --> load --> **project directory** --> configs --> **sama7g5ekdf_qspi_uboot_defconfig**  --> Open

**Legendry:** df --> Data Flash

<img src = "images/2_2a.png" align="middle">

Then perform the following changes:
  * Next software type --> **Load 4MB into the start of SDRAM**.
  * Demo application image storage setup:
    * Flash offset for Demo App --> QSPI offset where a user wants to flash the application.: Eg: 0x200000.
    * Demo app image size --> Size of the app image to be copied from QSPI to DRAM by at91bootstrap.
    * External RAM address to load Demo-App image --> It should match the .text load address in your application linker script. Eg:0x6ff00000.

An example configuration for SAMA7G54-EK is shown below.

<img src = "images/2_2b.png" align="middle">

This completes the configuration for building at91bootstrap to load the harmony application from QSPI into external volatile memory (DRAM) and then execute it from DRAM.
</details>

#### 2.3. Configure at91bootstrap to load application from e.MMC
<details>
  <summary> Details
</summary>  <br>
at91bootstrap can be configured to load the harmony application from NAND flash into external volatile memory (DRAM) as follows.

Project --> Properties --> Kconfig --> load --> **project directory** --> configs --> **sama7g5ekemmc_uboot_defconfig** --> Open.

<img src = "images/2_3a.png" align="middle">

Then perform the following changes:
  * Select SD Card Host Controller as **On SDHC0**.
  * Next software type --> **Load 4MB into the start of SDRAM**.
  * Demo application image storage setup:
    * External RAM address to load Demo-App image --> It should match the .text load address in your application linker script. Eg:0x6ff00000.
    * Next Software Image File name --> Name of your application binary. Eg:harmony.bin.

An example configuration for SAMA7G54-EK is shown below.
 
<img src = "images/2_3b.png" align="middle">

It completes the kconfig for building at91bootstrap to load the harmony application from e.MMC flash into external volatile memory (DRAM) and then execute it from DRAM.

</details>

#### 2.4. Configure at91bootstrap to load application from SDCARD
<details>
  <summary> Details
</summary>   <br>

at91bootstrap can be configured to load the harmony application from SD card memory into external volatile memory (DRAM) as follows.
Project --> Properties --> Kconfig --> load --> **project directory** --> configs --> sama7g5eksd_uboot_defconfig --> Open.

<img src = "images/3_4a.png" align="middle">
 
Then perform the following changes:
  * Select SD Card Host Controller as **On SDHC1**.	
  * Next software type --> Load 4MB into the start of SDRAM.
  * Demo application image storage setup.
    * External RAM address to load Demo-App image --> It should match the .text load address in your application linker script. Eg:0x6ff00000.
    * Next Software Image File name --> Name of your application binary. Eg:harmony.bin.

An example configuration for SAMA7G54-EK is shown below.

<img src = "images/2_4b.png" align="middle">

It completes the kconfig for building at91bootstrap to load the harmony application from SD card memory into external volatile memory (DRAM) and then execute it from DRAM.

</details>

#### 2.5. Customizing other default configuration
<details>
  <summary> Details
</summary>  <br>
User can customize the clock source, Display Banner (Display banner is the output string in the serial console when at91bootstrap begins running), external RAM-type and size, different SD card slot if SDCard is the user preferred NVM on the default configuration.

To do this, go to Project --> Properties --> Kconfig.

An example customization using SAMA7G54-EK board is shown below:
<img src = "images/3.png" align="middle">

</details>
</details>

### 3. Create a Custom Board Configuration
<details>
  <summary> Details
</summary>  <br>
This section is for advanced developers who wish to create a custom board configuration (almost from scratch) for the at91bootstap bootloader for their custom board.

* **Dependencies**
  * **Linux Host:** It is recommended to do customization using Linux Host.

  * **GIT:** Install GIT and clone at91bootstrap by using the following command:
  
       $ git clone https://github.com/linux4sam/at91bootstrap.git
  
  * Then follow the steps in [this link](https://microchipdeveloper.com/32mpu:at91bootstrap-board) to do customization and contribution of your customized code to Microchip at91bootstrap.

</details>


### 4. Building the at91bootstrap
<details>
  <summary> Details
</summary>   <br>
To build the at91bootstrap go to project --> Clean and build or simply click the build icon in the IDE.

<img src = "images/4a.png" align="middle"> 

**Note:** When building using XC32 compiler, if a user doesn’t have XC32 pro compiler, a warning saying cannot optimize size will pop up in the compiler output window as follows. To avoid this either use XC32 pro compiler or just ignore this.

<img src = "images/4b.png" align="middle"> 

Once the build is successful, you will get the build success message in the IDE as shown in the above Image.

Now user will be able to see the boot.bin file in the **project directory**/build/binaries.

boot.bin file is the at91bootstrap file.

<img src = "images/4c.png" align="middle"> 

Now the user can use the boot.bin file to 
  * [Flash it to the respective NVM.](../sama7g54_flash_boot_application_using_samba/readme.md)
                                    (or)
  * Debug the at91bootstrap using MPLAB X IDE as explained in the next section.
</details>

### 5. Debugging the at91bootstrap
<details>
  <summary> Details
</summary>  <br>
To debug the at91bootstrap, go to project --> Set as main project.
Then click project --> Debug or simply click the debug icon in the IDE.
Now user can start debugging the at91bootstrp by clicking the debug symbols available in the IDE like Step into, Reset, Step over etc.

<img src = "images/5a.png" align="middle">

When debugging the application, serial console outputs can be monitored by connecting windows host with the board (Eg: SAMA7G54-EK) through a terminal emulation program.
An example image showing the serial console output while debugging at91bootstrap is shown below.
<img src = "images/5b.png" align="middle">

This completes the training module to configure, build & debug at91bootstrap for different user preferred NVMs.
</details>
</details>

## Note
  * **[Click here to learn how to configure first stage bootloader for SAMA7G54 MPU](../sama7g54_configure_first_stage_bootloader/readme.md)**

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()  
