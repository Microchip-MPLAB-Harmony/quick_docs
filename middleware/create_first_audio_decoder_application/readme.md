---
title: Create first Audio Decoder Application
parent: Middleware
has_toc: false
nav_order: 4
---

# Creating Your First Audio Decoder Application from Scratch

This tutorial provides information on how to create an audio decoder project using MPLAB Harmony 3 and the <a href="https://www.microchip.com/Developmenttools/ProductDetails/DM320113" target="_blank">SAM E70 Xplained Ultra board</a>. It starts with a blank MPLAB® project and finishes with an audio decoder capable of playback of a WAV encoded file located on a USB flash drive, very similar to the audio_player_basic app in the <a href="https://github.com/Microchip-MPLAB-Harmony/audio/tree/master/apps" target="_blank">audio</a> 

To keep the application as simple as possible, no graphics or other program controls are included. It simply reads the statically specified file from the USB flash drive, sets up the codec sample rate, and outputs the data from the WAV file over the I2S interface at the sample rate specified in the WAV file. The WAV file for this project will be created externally as dual channel, 16 bit data, at 16,000 Hz sample rate and will say “Hello World”.

For more information refer the **[links](#Web-Links)** below.

## <a id="Web-Links"> </a>
## Web Links

- <a href="https://github.com/Microchip-MPLAB-Harmony/audio/wiki/decoder_quick_start" target="_blank">Creating Your First Audio Decoder Application from Scratch</a>

## Reference Links
- <a href="https://www.microchip.com/design-centers/32-bit" target="_blank">Microchip 32-bit MCUs</a>
- <a href="https://www.microchip.com/mplab/mplab-x-ide" target="_blank">Microchip MPLAB X IDE</a>
- <a href="https://www.microchip.com/mplab/mplab-harmony" target="_blank">Microchip MPLAB Harmony</a>
- <a href="https://www.microchip.com/mplab/compilers" target="_blank">MPLAB XC32/32++ C Compiler</a>
