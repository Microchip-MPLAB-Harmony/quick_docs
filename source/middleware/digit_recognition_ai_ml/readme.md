---
title: Digit Recognition AI/ML Application on SAM E51 IGAT CURIOSITY EVALUATION KIT Using MPLAB Harmony v3
parent: Middleware Examples
has_toc: false
nav_order: 4
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[<img src="../../r_images/quick_home.png" title="Home">](../../../readme.md) [<img src="../../r_images/quick_back.png"  title="Back">](../readme.md)
# Digit Recognition AI/ML Application on SAM E51 IGAT CURIOSITY EVALUATION KIT Using MPLAB Harmony v3

This tutorial shows you how to create an Artificial Intelligence/Machine Learning (AI/ML) application using TensorFlow Lite for Microcontroller (TFLM) to recognize handwritten digits on a SAM E51 Integrated Graphics and Touch (IGAT) Curiosity Evaluation Kit with the help of MPLAB® Code Configurator (MCC) and the MPLAB Harmony v3 software framework.

The application reads the touchpoints drawn by the user on the touch display, evaluates whether the outlined touchpoints are numeric digits (0 to 9) or not by using the convolution neural network, then displays the digit recognized on the same display screen.

This training module guides you in training an ML model using TensorFlow and converts it to TensorFlow Lite interpreter format compatible with microcontrollers (MCUs).

The neural network model is created, trained and converted to Tensorflow Lite format for inferencing on a microcontroller using TFLM runtime engine. The converted model is integrated with the application developed using MPLAB® Harmony v3 and MCC. The application uses the MPLAB Harmony v3 TFLM and CMSIS NN (Common Microcontroller Software Interface Standard Neural Network) Application Programming Interfaces (APIs) to use the model and demonstrate the end functionality.

The development of this application can be classified into two parts:

- Development of the model
- Development of the embedded project and integration of the model  

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://microchipdeveloper.com/harmony3:digit-recognition-ai-ml-same51-igat-training-module" target="_blank">Digit Recognition AI/ML Application on SAM E51 IGAT CURIOSITY EVALUATION KIT Using MPLAB Harmony v3</a>

## Reference Links
[<a href="https://www.microchip.com/design-centers/32-bit" target="_blank"> <img src="../../r_images/32_bit_mcus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/design-centers/32-bit-mpus" target="_blank"> <img src="../../r_images/32_bit_mpus.png"> </a>]()  &nbsp; &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank"> <img src="../../r_images/mplab_x_ide.png"> </a>]()  &nbsp; &nbsp; [<a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank"> <img src="../../r_images/mplab_harmony.png"> </a>]() [<a href="https://www.microchip.com/mplab/compilers" target="_blank"> <img src="../../r_images/mplab_compiler.png"> </a>]() [<a href="https://www.microchip.com/en-us/tools-resources/configure/mplab-code-configurator" target="_blank"> <img src="../../r_images/mcc_harmony.png"> </a>]()  
