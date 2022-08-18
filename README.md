# RunCPM_Pyboard_v1_1
RunCPM Port for the Pyboard v1.1 STM32F405RGT6

![RunCPM_Pyboard_BootUpScreen](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/RunCPM_Pyboard_v1_1.jpg?raw=true)

## Links

Original Pyboard v1.1 at the Micropython-Store<br>
https://store.micropython.org/product/PYBv1.1#_

Pyboard v1.1 Pinout-Picture<br>
https://store.micropython.org/media/products/PYBv1_1-E.jpg

My start around 2 years ago (October 2020)<br>
https://forum.micropython.org/viewtopic.php?f=6&t=9219

First Tutorial from User @apples in forum.micropython.org<br>
https://forum.micropython.org/viewtopic.php?f=6&t=9496

Arduino_Core_STM32 v2.3.0 (STM32Duino)<br>
https://github.com/stm32duino/Arduino_Core_STM32

STM32CubeProgrammer v2.11.0<br>
https://www.st.com/en/development-tools/stm32cubeprog.html
<br>

## Files changed

SdFat Arduino Library v2.20
```
C:\Users\guido\Documents\Arduino\libraries\SdFat\src\SdFatConfig.h
```
![SDFatConfig_h](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/SdFatConfig_h_changes.jpg?raw=true)

STM32Duino Core v2.3.0
```
C:\Users\guido\AppData\Local\Arduino15\packages\STMicroelectronics\hardware\stm32\2.3.0\variants\STM32F4xx\F405RGT_F415RGT\variant_generic.h
```
![variant_generic_h](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/variant_generic_h_changes.jpg?raw=true)

<br>

## File not needed to be changed 

("old" Tutorial tells something about change 
```
FLASH_LATENCY_5
```

STM32Duino Core v2.3.0
```
C:\Users\guido\AppData\Local\Arduino15\packages\STMicroelectronics\hardware\stm32\2.3.0\variants\STM32F4xx\F405RGT_F415RGT\variant_generic.cpp
```

<br>

## Settings for Uploading in the ARDUINO-IDE via DFU-Mode

![Arduino IDE Steetings](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/RunCPM_STM32_Pyboard_settings.jpg?raw=true)

<br>

## Pin Connection for DFU-Mode 

connect 3.3V & BOOT-Pin and press RST (Reset) while powered on via USB<br>
The green, yellow and blue LED will lit up low in DFU-Mode (on my clone board)
![DFU-Mode 1](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/Pyboard_v1_1_DFU_FullBoard.jpg?raw=true)
![DFU-Mode 2](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/Pyboard_v1_1_DFU.jpg?raw=true)

<br>

## onboard MicroSD-Connection Pinout
![MicroSD Pinout](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/Pyboard_MicroSD.jpg?raw=true)

```
SdFat SD;
const uint8_t SD_CS_PIN     = 43; // PC11 - MicroSD-Pin 2
const uint8_t SOFT_MISO_PIN = 40; // PC8  - MicroSD-Pin 7
const uint8_t SOFT_MOSI_PIN = 48; // PD2  - MicroSD-Pin 3
const uint8_t SOFT_SCK_PIN  = 44; // PC12 - MicroSD-Pin 5
SoftSpiDriver<SOFT_MISO_PIN, SOFT_MOSI_PIN, SOFT_SCK_PIN> softSpi;
```

<br>

## STM32F405RGT6-CPU on the Pyboard v1.1

![STM32F405RGT6-CPU](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/STM32F405RGT6_CPU.jpg?raw=true)

<br>

## Backside of the Pyboard v1.1

see in the lower left edge - DFU Pins = 3.3V and P1/DFU (=BOOT)
![Pyboard Backside Pinout](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/Pyboard_v1_1_Back.jpg?raw=true)
