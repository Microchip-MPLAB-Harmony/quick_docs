---
title: Application migration from 8 bit PIC18F to 32 bit SAM D21
parent: Migration Guides
has_toc: false
nav_order: 9
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)

# Application migration from 8-bit PIC18F to 32-bit SAM D21 MCU

> This page acts as a reference for migrating applications from 8-bit PIC Microcontroller (MCU) to 32-bit SAM MCU. This page shows how to migrate an application from **PIC18F47Q10** MCU to **SAMD21G17D** MCU with the help of an example.

> For the migration to a 32-bit MCU, the application uses **SAM D21 Curiosity Nano Evaluation Kit** and is developed on MPLAB® Harmony v3 software framework.

> The [SAM D21 Curiosity Nano Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/DM320119) is a hardware platform to evaluate the SAMD21G17D microcontroller (MCU). It is supported by the MPLAB® X Integrated Development Environment (IDE) and MPLAB Harmony v3 software development framework. The evaluation kit provides easy access to the features of the SAM D21 MCU to integrate the device into a custom design. Because the evaluation kit contains an On-Board Nano Debugger for programming and debugging, no external tools are necessary to program the SAMD21G17D device. The evaluation kit is compatible with Curiosity Nano  Base board (Part Number - [AC164162](https://www.microchip.com/Developmenttools/ProductDetails/AC164162)) which allows you to quickly scale and prototype your next innovative design using the SAMD21G17D MCU.

> [MPLAB® Harmony v3](https://www.microchip.com/mplab/mplab-harmony) is a flexible, fully integrated embedded software development framework for 32-bit microcontrollers (MCUs) and microprocessors (MPUs). MPLAB Harmony v3 includes the MPLAB Code Configurator (MCC) tool, a set of modular Peripheral Libraries (PLIBs), drivers, system services, middleware, and numerous example applications, all of which are designed to help quickly and easily develop powerful and efficient embedded software for Microchip’s 32-bit PIC® and SAM devices.

> This migration guide refers an existing application [Getting Started with UART Using EUSART on PIC18](http://ww1.microchip.com/downloads/en/Appnotes/Getting-Started-with-UART-Using-EUSART-on-PIC18-90003282A.pdf) developed on [PIC18F47Q10 Curiosity Nano](https://www.microchip.com/Developmenttools/ProductDetails/DM182029) evaluation kit using [MPLAB® Code Configurator (MCC)](https://www.microchip.com/mplab/mplab-code-configurator) and discuss steps to migrate the existing application to SAM D21 Curiosity Nano Evaluation Kit using MPLAB® Code Configurator (MCC). The application is further extended by adding more peripheral specific functionality.

> The application developed on SAM D21 MCU will utilize:
- PORT PLIB to control the LED.
- External Interrupt Controller (EIC) PLIB and Systick PLIB to toggle the LED on SWITCH press event
- SERCOM (as Universal Synchronous Asynchronous Receiver Transmitter (USART)), STDIO Library and Direct Memory Access (DMA) PLIBs to print the Info messages on a COM (serial) port terminal application running on a PC and to receive command from serial terminal.
- SERCOM (as SPI) to run a self-loopback test.

> Two ways to use this guide:
1. Create the project from scratch:
  -	Follow step-by-step instructions below.
2. Use the solution project as an example:
  - Build the [solution project](https://github.com/Microchip-MPLAB-Harmony/reference_apps/releases/latest/download/pic18f_to_samd21_migration.zip) and program it to the SAM D21 Curiosity Nano Evaluation Kit to observe the expected behavior.

> This following bullet points provides links to the topics:

- [Hardware Used](#hardware-used)
- [Software/Tools Used](#software-tools-used)
- [Hardware Setup](#hardware-setup)
- [Description](#Description)
  - [Overview](#Overview)
  - [Install MCC](#Install-MCC)  
  - [Create MPLAB Harmony v3 Project](#Create-MPLAB-Harmony-v3-Project)  
  - [Configure Clock](#Configure-Clock)  
  - [Add SERCOM (USART) Peripheral](#Add-SERCOM-(USART)-Peripheral)  
  - [Generate Code](#Generate-Code)  
  - [Add Code](#Add-Code)  
  - [Build and Program](#Build-and-Program)  
  - [Verify "Hello World" output](#Verify-Hello-World-output)  
  - [Configure/Enable Formatted STDIO, USART Receive and SWITCH/LED functionality](#Configure_Enable-Formatted-STDIO-USART-Receive-and-SWITCH_LED-functionality)  
  - [Verify Formatted STDIO, USART Receive and SWITCH/LED functionality](#Verify-Formatted-STDIO,-USART-Receive-and-SWITCH/LED-functionality)  
  - [Extend application to configure SPI loopback using DMA based Transfers](#Extend-application-to-configure-SPI-loopback-using-DMA-based-Transfers)  
  - [Verify extended functionality - SPI loopback](#Verify-extended-functionality---SPI-loopback)  
- [Results](#results)
- [Analysis](#analysis)
- [Conclusions](#conclusions)

## <a id="hardware-used"> </a>
## Hardware Used:
- [SAM D21 Curiosity Nano Evaluation Kit](https://www.microchip.com/Developmenttools/ProductDetails/DM320119)   
- Connection wires

## <a id="software-tools-used"> </a>
## Software/Tools Used:
<span style="color:blue"> *This project has been verified to work with the following versions of software tools:*</span>  

- [MPLAB Harmony v3 "csp" repo v3.18.5](https://github.com/Microchip-MPLAB-Harmony/csp/releases/tag/v3.18.5)
- [MPLAB Code Configurator Plugin v5.5.1](https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator)
- [MPLAB X IDE v6.20](https://www.microchip.com/mplab/mplab-x-ide)
- [MPLAB XC32 Compiler v4.40](https://www.microchip.com/en-us/tools-resources/develop/mplab-xc-compilers/xc32)
- Any Serial Terminal application like Tera Term terminal application.  

<span style="color:blue"> *Because Microchip regularly update tools, occasionally issue(s) could be discovered while using the newer versions of the tools. If the project doesn’t seem to work and version incompatibility is suspected, It is recommended to double-check and use the same versions that the project was tested with.* </span>

## <a id="hardware-setup"> </a>
## Hardware Setup
- Connect the SAM D21 Curiosity Nano Development Board to the Host PC as a USB Device through a Type-A male to micro-B USB cable connected to Micro-B USB (Debug USB) port.
- Connect a wire from **PA16 to PA19** on SAM D21 Curiosity Nano Development Kit for SPI Self Loopback testing.  

  <img src = "images/hardware.png" width="800" height="500" align="middle">  
  <img src = "images/samd21_cnano_angle.png" width="800" height="500" align="middle">  

## <a id="Description"> </a>
## Description

## <a id="Overview"> </a>
### Overview  
This migration guide uses the PIC18 application which helps in “**Getting Started with UART Using EUSART on PIC18**”.   
-	Click [Here](https://github.com/microchip-pic-avr-examples/pic18f47q10-cnano-eusart-commands-fs) to view/download the application.
-	For details on the application, refer “Section 4” in the [user guide](http://ww1.microchip.com/downloads/en/Appnotes/Getting-Started-with-UART-Using-EUSART-on-PIC18-90003282A.pdf).


The PIC18 application shows how to implement a command line interface. This way, the microcontroller can receive control commands via the EUSART. In this use case, an LED is controlled using commands sent from the MPLAB Data Visualizer.  

The application flow is as follows:

1.	 Configures the system clock  
  The clock is configured to 1 MHz using High Frequency Internal Oscillator (HFINTOSC).

2.	 Configures USART3 
  USART3 is configured for 9600 baud rate and the standard 8-N-1 (eight data bits, no parity bit and one Stop bit) frame format.

3.	 Configures pins   
  The USART TX, RX pins and LED pin are configured

4.	 Implements STDIO receive and send functions   
  STDIO library is implemented to receive and send commands from serial terminal

5.	 Reads and execute valid commands  
  Receives command from serial terminal and executes it

Follow the below steps to get started migrating to SAMD21 and later extend the functionality by adding more peripherals.

<a id="Install-MCC"> </a>
### Install MCC
1.	Install the MPLAB® Code Configurator v5 (MCC) Plug-in in the MPLAB X IDE if not installed.
2.	Verify the MPLAB® Code Configurator v5 (MCC) Plug-in is installed.
 - Launch MPLAB X IDE from the Windows® Start Menu. Close all the projects and files that are currently open.
 - Go to **Tools > Embedded**.
 -	You will see **MPLAB® Code Configurator v5** in the menu    
 <img src = "images/mcc_lanuch.png" width="700" height="250" align="middle">  

<a id="Create-MPLAB-Harmony-v3-Project"> </a>
### Create MPLAB Harmony v3 Project
3.	Create MPLAB Harmony v3 Project Using MPLAB X IDE  
 - Select **File > New Project** from the main IDE menu    
 <img src = "images/new_project_selection.png" width="500" height="400" align="middle">  
 - In the **Categories pane** of the **New Project** dialog window, select **Microchip Embedded**. In the **Projects pane**, select **Application Project(s)**, then click **Next**.    
 <img src = "images/choose_project.png" width="700" height="500" align="middle">  
 - In the **Select Device** pane, select ATSAMD21G17D as the target device in the **Device** edit box and select **Next**.    
 <img src = "images/select_device.png" width="700" height="500" align="middle">
 - In the **Select Compiler pane** of the **New Project** dialog window, select the latest **XC32 Compiler**, then click **Next**.    
 <img src = "images/select_compiler.png" width="725" height="450" align="middle"> 
 - In the **Project Settings** window, apply the following settings:  
   1.	**Project Name**: enter the project’s logical name as "*pic18f_to_sam_d21_cnano*". This is the name that will be shown from within the MPLAB X IDE.
   2.   **Project Location**: indicates the path to the root folder of the new project. All project files will be placed inside this folder. The project location can be any valid path, for example: `<your project path>`\pic18f_to_sam_d21_proj.
   3.	**Project Folder**: indicates the name of the MPLAB X .X folder. It will automatically be created by using the *Project Name*.   
 - click **Finish** to launch MCC.      
 <img src = "images/project_settings.png" width="700" height="500" align="middle">    
 - The MCC plugin’s main window for the project will be displayed as shown in the following image    
 <img src = "images/mcc.png" align="middle">  

<a id="Configure-Clock"> </a>
### Configure Clock
4.	Configuring Clock Settings  
The SAM D21 family of microcontrollers (MCUs) contains a sophisticated clock distribution system designed to give maximum flexibility to the user application. The clock system allows the tuning of the performance and power consumption of the device in a dynamic manner. The MCC provides an easy to use UI (User Interface) window, and a Clock Easy View window to configure the system and peripheral clocks.
 - Launch **Clock Easy View** by going to **Project Graph > Plugins** menu and then select **Clock Configuration**.    
 <img src = "images/clock_launch.png" width="600" height="300" align="middle">  
 -	In the **Clock Easy View**, SAM D21 can operate at maximum 48 MHz, therefore **Main Clock** is set to 48 MHz.
 -	Change the **Main Clock** to 1MHz
 -	The Open loop Digital Frequency Locked Loop (DFLL 48 MHz) is configured and enabled to run the main clock. The configured DFLL is fed as input to the GCLK generator ‘0’ and a suitable clock divider (48) and masker must be selected to achieve a maximum frequency of 1 MHz. Refer to the following figure to configure the main clock to run at 1MHz    

 <img src = "images/samd21_clk.png" width="700" height="500" align="middle">     

  MCC clock easy view provides all the clock options available in the SAMD21 in a UI, which makes easier to configure the clock whenever necessary.

<a id="Add-SERCOM-(USART)-Peripheral"> </a>
### Add SERCOM (USART) Peripheral
5.	Adding SERCOM (USART) Peripheral  
MCC Graphical User Interface helps in selecting and configuring the peripherals needed by the project. It lists all the peripherals available in SAMD21 in an *Device Resources* tab.  

 -	Click on the **Device Resources** tab in the left pane in the MPLAB® Code Configurator (MCC) window. Expand **Harmony > Peripherals > SERCOM**.
 -	Double click or drag and drop **SERCOM5** to add the USART Peripheral Library (PLIB) to the project graph.  

 **Note:** SAM D21 Curiosity Nano On-Board Nano Debugger also includes a Virtual Com port which is routed to SERCOM5, therefore in this application, SERCOM5 is chosen.    
 <img src = "images/selecting_sercom5.png" width="780" height="520" align="middle">    

 -	Select the **SERCOM5 Peripheral Library** in the project graph. Verify that the default "SERCOM Operation Mode" configuration is set as USART and configure 9600 baud rate and then select **SERCOM PAD[2]** in Recieve Pinout and the standard 8-N-1 (eight data bits, no parity bit and one Stop bit) frame format.    

 <img src = "images/sercom5_config.png" width="620" height="380" align="middle">  

6. Configuring USART pins using MCC PIN Configurator  
The Pin Manager consists of Pin Settings, the Pin Diagram, and the Pin Table tabs, which enables users to configure (assign peripheral function, set pin direction, configure pull-up or pull-down and so on) and map the I/O pins.  

  The following color combinations are associated with the pins in the graphical or table View:  
  	**Gray**: This pin is not usable in the selected configuration, and there is no enabled module which has any functionality on that pin. The grayed-out locks on a white background indicates the pins that are locked out by selected system functions.  
  	**Blue**: This pin is available and can be allocated to a module.  
  	**Green** (with a lock): This pin is allocated and selected for a module. The name displayed against the pin is either the name of the pin in the module’s context or a custom name entered.
 
 -	Open the **Pin Configuration** tabs by clicking on **Project Graphs > Plugins > Pin Configuration**.	    
 <img src = "images/pin_conig_launch.png" width="600" height="300" align="middle">  
 -	Launching Pin configuration opens Pin Settings, the Pin Diagram, and the Pin Table tabs.
 -	select the MCC **Pin Table** tab and then scroll down to the **SERCOM5** module as shown below.  
 	Enable USART_TX on PA22 (Pin #31)    
 	Enable USART_RX on PB22 (Pin #37)    
 <img src = "images/sercom5_pin_config.png" width="600" height="200" align="middle">    

<a id="Generate-Code"> </a>
### Generate Code
7.	Generate Code  
 -	Now, generate the code by using MCC. From the left side tab **Resource Management [MCC]**, go to **Project Resources** and then click on the **Generate** button.
 <img src = "images/generate_code.png" width="450" height="300" align="middle">
 -	Navigate to the **Projects** tab in MPLAB X IDE to view the project tree structure.
 -  Examine the generated code as shown below.
 
 <img src = "images/project_tree.png" width="350" height="600" align="middle">
 
 MCC will include all the MPLAB Harmony library files and generate the code based on the MCC selections. The generated code would add files and folders to your Harmony project as shown. Among the generated code, notice the Peripheral Library (PLIB) files generated for SERCOM 5 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)), Clock and PORT peripherals. 

<a id="Add-Code"> </a>
### Add Code

8. Navigate to the **Projects** tab in MPLAB X IDE and select main.c, add below code snippet in main function to print “Hello World” string on the serial terminal.  
        uint8_t welcomeData[]  = "Hello World\r\n";

        while ( true )
        {
          SERCOM5_USART_Write(&welcomeData[0],sizeof(welcomeData));
        }  
 <img src = "images/code_snippet1.png" width="400" height="300" align="middle">  

<a id="Build-and-Program"> </a>
### Build and Program
9.	Before proceeding to Build and program, set up the compiler toolchain. Click on the **Projects** tab on the top left pane in MPLAB X IDE. Right click on the project name **pic18f_to_sam_d21_cnano** and go to **Properties**.  
 <img src = "images/project_view.png" width="400" height="700" align="middle">  
10.	Make sure that XC32 (v4.40) is selected as the Compiler Toolchain for XC32. Click on **Apply** and then click on **OK**.  
 <img src = "images/project_properties.png" width="900" height="500" align="middle">  
11.	Clean and build your application by clicking on the **Clean and Build** button as shown below.    
 <img src = "images/clean_and_build_icon.png" width="300" height="100" align="middle">  
12.	Program your application to the device by clicking on the **Make and Program** button as shown below.    
  
  <img src = "images/make_and_program.png" width="300" height="50" align="middle">    

   The lab should build and program successfully.
  
<a id="Verify-Hello-World-output"> </a>
### Verify "Hello World" output
13.	Now, open the **Tera Term** terminal application on your PC (from the Windows® Start menu by pressing the **Start** button). Select the **Serial Port** as shown below.    
 <img src = "images/tera_term_settings.png" width="600" height="400" align="middle">    
14.	Change the baud rate to 9600.    
 <img src = "images/tera_term_settings1.png" width="600" height="400" align="middle">    
15.	You should see the “Hello World” message displayed on the terminal as shown below.    
   
   <img src = "images/output1.png" width="600" height="400" align="middle">    

   You successfully completed printing the “Hello World” message on serial terminal. Let us continue and extend the functionality of the application as below.  

<a id="Configure_Enable-Formatted-STDIO-USART-Receive-and-SWITCH_LED-functionality"> </a>
### Configure/Enable Formatted STDIO, USART Receive and SWITCH/LED functionality
 - Configure STDIO Library to use **printf** and **scanf** function to write and read data from the serial terminal respectively.  
 - Receive the command from serial terminal and control the LED0 on the SAM D21 Curiosity evaluation kit.  
 - Use Switch SW0 on the SAM D21 Curiosity Evaluation Kit to toggle the LED twice when it is pressed. External Interrupt controller (EIC) and Systick peripherals are used to achieve this.  
16.	If you closed MCC accidently and would like to open it again, go to **Tools > Embedded > MPLAB Code Configurator v5** in MPLAB X IDE.
17.	In the **Project Graph**, Select **SERCOM5**. Right click on yellow diamond and select consumer as **STDIO** as shown below.  
   <img src = "images/sercom5_stdio.png" width="600" height="350" align="middle">  
18.	Select the MCC **Pin Settings** tab and then scroll down to the PORT pin **PB10** (Pin Number 19) in the **Pin ID** column and configure **PB10** as an output pin for LED functionality as shown below.  
   <img src = "images/led_pin_settings.png" width="1000" height="450" align="middle">  
19.	Select the **Pin Settings** tab and then scroll down to the PORT pin **PB11** (Pin Number 20) in the **Pin ID** column and configure **PB11** as an external interrupt pin for switch functionality as shown below. Internal pull-up is enabled to avoid false edge detection as there is no external pull-up on the SAM D21 Curiosity Nano Evaluation Kit.  
   <img src = "images/switch_pin_settings.png" width="1000" height="450" align="middle">  
20.	Select the Project Graph tab.  
   - Under the **Device Resources** tab, expand **Harmony > Peripheral > EIC**. Select and double click on **EIC** to add the EIC module to the project.    

    <img src = "images/eic_settings.png" width="800" height="650" align="middle">      

   - Configure the EIC block to generate an interrupt every time the user presses the switch SW0 as shown below and enable filter functionality to avoid electrical noise on the switch pin.    
   <img src = "images/eic_settings1.png" width="500" height="500" align="middle">    
21.	Enable Systick to create a delay for toggling LED0, click on **System** in **Project Graph** and Configure as below.  
   <img src = "images/systick_settings.png" width="550" height="450" align="middle">  
22.	Click on the **Generate** button to generate the code.
23.	Navigate to the **Projects** tab in MPLAB X IDE and select main.c, add below code snippet to receive the command from serial terminal and a function to control the LED0 on the SAM D21 Curiosity Nano Evaluation Kit.
 -	In main.c, add the below function above “main” function
                         #include <string.h>

                         void executeCommand(char *command)
                         {
                             if(strcmp(command, "ON") == 0)
                             {
                                 LED_Clear();
                                 printf("OK, LED ON.\r\n");
                             }
                             else if (strcmp(command, "OFF") == 0)
                             {
                                 LED_Set();
                                 printf("OK, LED OFF.\r\n");
                             }
                             else
                             {
                                 printf("Incorrect command.\r\n");
                             }
                         }    
    <img src = "images/code_snippet2.png" align="middle">                            
 -	Move “SERCOM5_USART_Write” function above while loop and add **scanf** inside the while loop as shown below.    
 <img src = "images/code_snippet3.png" align="middle">     
24.	Clean and build your application by clicking on the **Clean and Build** button.      

25.	Now, open the **Tera Term** terminal application on your PC. Enable **Local echo** in **Setup > Terminal** as shown below.

 <img src = "images/tera_term_settings2.png" width="600" height="300" align="middle">

<a id="Verify-Formatted-STDIO,-USART-Receive-and-SWITCH/LED-functionality"> </a>
### Verify Formatted STDIO, USART Receive and SWITCH/LED functionality
26.	Program your application to the device by clicking on the **Make and Program** button. The lab should build and program successfully.
27.	In Tera Term you should see “**Hello World**” message displayed.
28.	Type **ON** in serial terminal and press **Enter** to turn on LED0 on SAMD21 Curiosity Nano kit and Type **OFF** in serial terminal and press **Enter** to turn off LED0 on SAMD21 Curiosity Nano Evaluation Kit.  
 <img src = "images/output2.png" width="400" height="200" align="middle">    
29.	Switch SW0 is configured as interrupt using EIC peripheral, therefore register a call back in main function. Whenever user presses the switch, a callback will be notified and inside the call back, toggle the LED0 twice.
 - In main.c file, inside main function, add the below code.
                   EIC_CallbackRegister(EIC_PIN_11,EIC_User_Handler, 0);
                   SYSTICK_TimerStart();
 - In main.c, add the below code above main function
                  static void EIC_User_Handler(uintptr_t context)
                  {
                     uint8_t i = 0;

                     while(i<4){
                      LED_Toggle();
                      SYSTICK_DelayMs(500);
                      i++;
                     }
                  }  
 <img src = "images/code_snippet4.png" align="middle">    

30.	Clean and build your application by clicking on the **Clean and Build** button.
31.	Program your application to the device by clicking on the **Make and Program** button.
32.	Press the Switch SW0 on SAM D21 Curiosity Nano Evaluation Kit and observe LED0 Toggling twice at 500ms rate.

    You successfully completed controlling the LED0 on the SAMD21 Curiosity Nano Evaluation Kit by receiving the commands from the serial terminal through USART and also toggled the LED0 on Switch SW0 press using EIC and Systick peripheral.

<a id="Extend-application-to-configure-SPI-loopback-using-DMA-based-Transfers"> </a>
### Extend application to configure SPI loopback using DMA based Transfers

    Let us extend the functionality and add Serial Peripheral Interface (SPI) to perform a Self-Loopback test and add Direct memory address (DMA) to send the status of the SPI Transfer to the terminal without using CPU.


33. Select the **Project Graph** tab. Under the **Device Resources** tab, expand **Peripheral > SERCOM**. Select and double click on **SERCOM1** to add the SPI module to the project.    
   <img src = "images/sercom1_config.png" width="650" height="500" align="middle">    
34.	In **Project Graph** select **SERCOM1** and configure as below  
   <img src = "images/spi_config.png" width="750" height="450" align="middle">    

35.	Open **Pin Table**, Select **SERCOM1** and configure the pins as shown below  
   <img src = "images/spi_pin.png" width="800" height="200" align="middle">  

36.	Launch **DMA Configurator** from **Project Graph > Plugins > DMA Configuration**  
   <img src = "images/dma_launch.png" width="400" height="300" align="middle">  
37.	The DMA Configuration is open in the new popup window. Click on **ADD Channel** and Select **SERCOM5_Transmit** to configure the DMA.  
   <img src = "images/dma_settings.png" width="700" height="350" align="middle">  
38.	Click on the **Generate** button to generate the code.
39.	In main.c, Add below code snippet
            SERCOM1_SPI_WriteRead(&txData[0], sizeof(txData), &rxData[0], sizeof(rxData));

            /* Compare received data with the transmitted data */
            if ((memcmp(txData, rxData, sizeof(txData)) == 0))
            {
                /* Pass: Received data is same as transmitted data */
                DMAC_ChannelTransfer(DMAC_CHANNEL_0, "Received SPI Valid Data\r\n", \
                (const void *)&(SERCOM5_REGS->USART_INT.SERCOM_DATA), \
                25);
            }
            else
            {       
                /* Fail: Received data is not same as transmitted data */
                DMAC_ChannelTransfer(DMAC_CHANNEL_0, "Received Invalid SPI Data\r\n", \
                (const void *)&(SERCOM5_REGS->USART_INT.SERCOM_DATA), \
                27);
            }
 - Add below code snippet above main function
             uint8_t txData[]  = "SELF LOOPBACK DEMO FOR SPI!";
             uint8_t rxData[sizeof(txData)];  
<img src = "images/code_snippet5.png" align="middle">  

40.	Clean and build your application by clicking on the **Clean and Build** button.
41.	Program your application to the device by clicking on the **Make and Program** button.

<a id="Verify-extended-functionality---SPI-loopback"> </a>
### Verify extended functionality - SPI loopback

42.	Connect PA16 and PA19 on SAM D21 Curiosity Nano Evaluation Kit using a connecting wire.
43.	Open Tera Term and observe the data as shown below.    
   
   <img src = "images/output3.png" align="middle">    

   You can still control the LED0 by sending the commands through serial terminal.

## <a id="results"> </a>
## Results
You observed the migration of application from PIC18F to SAMD21. You successfully used USART and STDIO to print the messages and receive the commands. Ports and EIC were used to control the LED and also configured SPI and DMA to perform self-loop back test.

## <a id="analysis"> </a>
## Analysis
You have successfully created your first application using MPLAB Harmony v3 on a SAM D21 microcontroller. Your application used all the fundamental elements that go into building a real-time application. Your successfully migrated application from PIC18F to SAMD21.
In this application, you used MPLAB Code Configurator (MCC) to configure the SAM D21 and also used the MPLAB Harmony v3 Framework. You used the clock configurator to set up the CPU clock and also configured Systick. You configured SERCOM 5 (as Universal Synchronous Asynchronous Receiver Transmitter (USART)), SERCOM 1 (SPI), and External Interrupt Controller (EIC) Peripheral Libraries (PLIBs). You also configured the Direct Memory Access (DMA) using the DMA configurator. You used the pin configurator to set up the pins for LED and switch functions.

## <a id="conclusions"> </a>
## Conclusions
This guide provided you overview of migrating an application from PIC18F to SAMD21.
This guide also provided steps to configure and using all the fundamental components needed to build an application on a SAM D21 microcontroller with MPLAB Harmony v3 framework.

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()
