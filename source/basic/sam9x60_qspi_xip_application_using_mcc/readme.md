---
grand_parent: Developing an application getting executed from QSPI flash on SAM9X60-EK
parent: Harmony Basics
has_toc: false
nav_order: 16
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Blink LED Application getting executed from QSPI flash on SAM9X60 Evaluation kit
<h2 align="center"> <a href="https://github.com/Microchip-MPLAB-Harmony/reference_apps/releases/latest/download/sam9x60_ek_qspi_xip.zip" > Download </a> </h2>

-----
## Description

>   This application demonstrates how to run and debug an application executed from QSPI flash on SAM9X60 Evaluation Kit. Blue LED turn ON when user input key(sw1) is pressed.

## Key Highlights of [SAM9X60 Evaluation kit](https://www.microchip.com/en-us/development-tool/dt100126):

* LCD Interface.
* External Non-Volatile Memories like NAND, SD, and MicroSD card interfaces.
* Additional sensors can be interfaced using "click boards" through an on-board [mikroBUS connector](https://www.mikroe.com/click).
* Two mechanical programmable buttons.
* One User Input Switch(sw1) and one RGB LED.
* UART, USB and CAN Interfaces.
* Raspberry pi connectors.

## Modules/Technology Used:

- Peripheral Modules
    - BSP
    - DBGU	<br>
<img src = "images/project_graph.png" align="middle">

## Hardware Used:  

- [SAM9X60 Evaluation kit](https://www.microchip.com/en-us/development-tool/dt100126).
- SD Card.

## Software/Tools Used:
- [MPLAB® X IDE](https://microchipdeveloper.com/mplabx:installation).
- [MPLAB® XC32 Compiler](https://microchipdeveloper.com/install:xc32).
- [MPLAB® Code Configurator (MCC)](https://microchipdeveloper.com/install:mcc).

<span style="color:blue"> This project has been verified to work with the following versions of software tools:</span>
  * mcc_version: v5.4.1
  * mcc_core_version: v5.6.1
  * mplabx_version: v6.15
  * harmony_version: v1.2.0
  * compiler: XC32 (v4.40) 

## Hardware Setup : <span id="Setup1"><span>
- Power up the board by connecting 5V/2A power adapter to J1 or connect the USB Micro-B port(J7) to the Host PC using a micro-USB cable.
- Connect the USB Micro-B port (J22- J-Link-CDC) on board to the computer using a micro-USB cable (to print debug messages on the serial console).
- Default jumper settings should be as follows: <br>
<img src = "images/jumper.png">
<img src = "images/setup.png">

## Developing an application executed from QSPI flash memory:

<details>
  <summary> Details
</summary>   <br> 

- Launch MPLAB® X IDE- From the main menu, click on File, then New Project. Under `Projects` choose `32-bit MCC  Harmony Project`, click Next- For `Framework Path` choose the location on your PC where you want to download the Harmony 3 framework- Click Next.  <br>
Note: ***If you have already downloaded the Harmony 3 framework, enter the location of the harmony framework.*** <br>
<img src = "images/step1.png"> <br>
<img src = "images/step2.png">  <br>

- Enter `Location` , `Folder` and `Name of the project`. Click Next.  <br>
<img src = "images/step3.png">  <br>

- In the `Configuration Settings` window, for `Name`  enter `default`, for `Device Family` select `SAM`, for `Target Device` select `SAM9X60`. Click Finish.  <br>  
This creates an empty project and set this project as `main project`. If there are other projects open in the project explorer window, set this project as main project by right clicking on the project, choose 'Set as Main Project'.  <br>
<img src = "images/step4.png">  <br>

- After the project is created, MCC will be automatically launched. (To launch MCC manually, from main menu, click on `Tools` -> `Embedded` -> `MPLAB® Code Configurator` or click MCC button in the MPLAB® X IDE tool bar). It will launch Content manger Wizard. Then select MPLAB® Harmony.  <br>
<img src = "images/step5.png">  <br>

- In addition to the required packages, download the optional packages bsp, csp, core, dev_packs  and then click Finish. Content download will take some time. Please wait till all the contents are downloaded.  <br>
<img src = "images/step7.png">  <br>

- Now a project graph will be displayed. From `Device Resource` add `Board Support Packages`  for `SAM9X60 Evaluation kit BSP ` to `Project Graph`.  <br>
<img src = "images/step8.png">  <br>

- From `Device Resource`, `Peripherals` -> add `DBGU` to the `Project Graph`and ensure the configuartion options of DBGU as shown below. This helps to print the debug messages (console serial communication messages) via comm port.  <br>
<img src = "images/step16.png">  <br>

- Ensure  all the pins are configured as below:  <br>
PA9 and PA10 are for console serial debugging. PD18 should be configured for user input switch. PB11, PB12, PB13 are for LEDs red, green, and blue respectively. <br>
Configure the pins PB19, PB20,PB21, PB22, PB23, PB24 for QSPI as mentioned in the below image.
<img src = "images/step17.png">  <br>

- Now Save all. Then click generate code. This will generate code for all the Device Resource that have been added in the project graph.  <br>
<img src = "images/step18.png">  <br>

- Up to this point in the project creation process, you used MPLAB Code Configurator(MCC) to configure and generate code to initialize the device (SAM9X60) . <br>
  Refer initialization.c file in your project configuration path and find all the device resource added in the project graph got initialized.  All that is left is for the user to write the application code in the main.c file.
  Documentation for each of the peripheral libraries or bsp libraries can be accessed as follows:
  1.	Peripheral libraries APIs can be accessed as a HTML file (*.html) from the Harmony 3 Framework path. (framework_path/csp/docs/index.html)
  2.    BSP libraries APIs can be found in bsp.h

- APIs used for this application are as follows:
  * bool DBGU_Write( void* buffer, const size_t size );
  * bool DBGU_WriteIsBusy( void );
  * LED_BLUE_On();
  * LED_BLUE_Off);
  * SW1_Get();

- Sample code can be as follows:
<img src = "images/step32.png">  <br>

- Now right click on the project and click `Properties`. For `Connected Hardware Tool` -> select connected hardware debugger used, for `Compiler Toolchain` -> select XC32 and click Apply.  <br>
<img src = "images/step19.png">  <br>

- From J-32 , `Option categories` choose `Communication` and for `JTAG Method`, select `4-wire JTAG`.  <br>
<img src = "images/step20.png">  <br>

- Select Bootstrap for Categories and select the `Use Bootstrap` checkbox. For `bootstrap file` -> select the at91bootstrap elf file generated by following the steps mentioned in [this document.](../configure_at91bootstrap_to_enable_qspi_xip_mpus/readme.md)

- By default, MPLAB X only produces ELF and Hex format output files.
    To generate application output in binary format, a post build step needs to be added to the project properties.
	To do this, go to project properties, building, click the check box `Execute this line after build`, then enter the below command. <br>
	***${MP_CC_DIR}/xc32-objcopy -O binary ${DISTDIR}/${PROJECTNAME}.${IMAGE_TYPE}.elf ${DISTDIR}/harmony.bin*** <br>
<img src = "images/24.png" align="middle"> <br>
</details> 

## Linker file modifications to execute an application from QSPI flash(offset 0x40000)

In this example we have demonstrated an application getting executed from QSPI flash offset 0x40000. <br>
Note : **To change the QSPI offset from where application will get executed, at91bootstrap kconfig must be configured and built.** <br>

The following linker file(ddram.ld) modifications are required to enable application getting executed from QSPI:
* Define only two memory regions:
<img src = "images/step22.png" align="middle"> <br>

* Assign text section to rom(qspi) and data section to relocate section(so, it will be copied from qspi memory to sram during runtime).<br>
  ***Note : bss and relocate sections should be load from rom(qspi) and run from ram(sram)***
<img src = "images/step23.png" align="middle"> <br>

* Remove cache aligned sections and assign  _ramcode_lma and  _ramdata_lma to ram as shown below.
<img src = "images/step24.png" align="middle"> <br>

* Its a good practice to remove unused input section while building output binary. To do this, go to project properties , xc32-ld config , check Remove Unused Sections as shown below.
<img src = "images/step30.png" align="middle"> <br>

* Now clean and build the project. You should see a message on the output console that the project was successfully built. This completes the development of the application.  <br>
</details>

## SAM-BA Installation and Setup:
* Install SAM-BA tool on your windows host PC.
  * To Download the latest version of SAM-BA tool for Windows [click this link](https://www.microchip.com/en-us/development-tool/SAM-BA-In-system-Programmer).
  * Download the ZIP file and unzip it into a working directory of your choice.
  * Add the SAM-BA directory path to the environment variables.
    * To do this from your PC --> Open the Start Search, type in “env”.
    * Choose “Edit the system environment variables” --> Click "Environment Variables" --> "System Variables" --> add SAM-BA directory path to path variables.
      <img src = "images/7.png" align="middle">
  * Once the SAM-BA Host program has been installed, the execution of the application is from the Windows command prompt.
* Setup to flash using SAM-BA:
  * Open Disable boot Jumper(J13) on SAM9X60 Evaluation Kit.
  * Ensure there is no SD memory card inserted and there is no application on any of the external NVMs.
  * Press start button.
  * Push and hold the "BOOT_DIS" button.(This disables booting from the onboard memories - NAND and NOR(QSPI) flash Memory)
  * Reset the board by pressing and then releasing the reset "nRST" button.
  * Release the "BOOT_DIS" button.

## Configure first stage bootloader to boot from QSPI flash:
Use the below SAM-BA commands to configure first stage bootloader to boot from  QSPI.
[Click here to learn about boot process and first stage boot configuration.](https://microchipdeveloper.com/32mpu:boot-sam9x60) <br>
Note: ***This is not the mandatory step.***
* sam-ba -p j-link -b sam9x60-ek -a bootconfig -c writecfg:bscr:EMULATION_ENABLED // Enable Emulation
* sam-ba -p j-link -b sam9x60-ek -a bootconfig -c readcfg:bscr // Read bscr and verify emulation is enabled
* sam-ba -p j-link -t 5 -b sam9x60-ek -a bootconfig -c resetemul  // Emulation SRAM Reset
* sam-ba -p j-link -b sam9x60-ek -a bootconfig -c writecfg:bcp-emul:DBGU,QSPI0_IOSET1  // Enable debug, QSPI0 as external NVM
* sam-ba -p j-link -b sam9x60-ek -a bootconfig -c readcfg:bcp-emul // Read bcp_emul and verify whether QSPI is set as external NVM <br>
<img src = "images/step31.png" align="middle"> <br> 

Now reset the board by pressing reset button. <br>

Note: ***Boot configuration using Emulation SRAM has to be set every power cycle.*** <br>
      ***User can also write boot configuration packet(BCP) to OTPC(One Time Programmable Memory Controller). Refer SAM-BA installation directory on how to write BCP to OTPC***

## Debugging Application Project executed from QSPI on MPLAB® X IDE:
- Open the project (sam9x60_ek_blink_led_qspi_xip/firmware/sam9x60_ek.X) in MPLAB® X IDE.  
- In the project properties, ensure `SAM9X60` is selected as the 'Device' and for `Connected Hardware Tool`, select connected J-Link debugger with the board to program/debug the application.  
- Build the code.
- ***Before debugging ensure that harmony.bin file in your project directory is flashed in the QSPI offset.***
- Refer the section “SAM-BA Installation and Setup" for initial device setup and tool installation procedure.
### Use the below sam-ba commands to erase QSPI flash and program the application.
   * sam-ba -p j-link -b sam9x60-ek -a qspiflash -c erase //To erase entire QSPI flash
   * sam-ba -p j-link -b sam9x60-ek -a qspiflash -c erase:0x40000:0x20000 //Erase only 0x20000 bytes of data from the QSPI offset 0x40000
   * sam-ba -p j-link -b sam9x60-ek -a qspiflash -c write:harmony.bin:0x40000  //Program the application in the QSPI offset 0x40000 <br>
Note : ***Don't flash boot.bin to QSPI memory to debug the application on MPLAB® X IDE.*** <br>
<img src = "images/step27.png" align="middle"> <br>
- Debug the code by clicking on the "Debug" button in MPLAB® X IDE tool bar and observe that the application is getting executed from QSPI flash memory.  
- Run the application by clicking the “run" button in MPLAB® X IDE tool bar.
A terminal emulation program running on the Host PC communicates with the SAM9X60 Evaluation kit J-Link CDC.
Ensure the terminal emulation program(Eg: PUTTY) is configured to the COM port and settings are:
  * Speed: 115200
  * Data: 8
  * Parity: None
  * Stop Bits: 1 
- Now, you will get the debug message on the serial console as "This application is getting executed from QSPI-offset 0x40000".
  Now press the user button(sw1) and observe LED getting turned ON.<br>
 <img src = "images/step25.png" align="middle"> <br> 

  
## Steps to execute the harmony application from QSPI flash:
### SAM-BA commands to program the boot and application file to QSPI flash:
   * sam-ba -p j-link -b sam9x60-ek -a qspiflash -c erase //To erase entire QSPI flash
   * sam-ba -p j-link -b sam9x60-ek -a qspiflash -c writeboot:boot.bin //To program bootstrap bin file
   * **Note:** Use the boot.bin file generated by following the steps mentioned in [this document.](../configure_at91bootstrap_to_enable_qspi_xip_mpus/readme.md)
   * sam-ba -p j-link -b sam9x60-ek -a qspiflash -c write:harmony.bin:0x40000  //Program the application in the QSPI offset 0x40000
   <img src = "images/step27.png" align="middle"> <br>
Note : ***Flash both boot.bin and harmony.bin to QSPI memory to execute the application from QSPI upon reset .*** <br>

- Press the reset button.
-  Now, you will get the debug message on the serial console as "This application is getting executed from QSPI-offset 0x40000".
  Now press the user button(sw1) and observe LED getting turned ON.<br>
 <img src = "images/step26.png" align="middle"> <br> 


* **NOTE**
  * **[Click here to learn how to configure at91bootstrap to enable QSPI-XIP on MPUs](../configure_at91bootstrap_to_enable_qspi_xip_mpus/readme.md)**
  
## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]()  [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()

