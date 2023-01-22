# RunCPM_Pyboard_v1_1
RunCPM Port for the Pyboard v1.1 - STM32F405RGT6 CPU

![RunCPM_Pyboard_BootUpScreen](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/RunCPM_v6_0_Pyboard_v1_1.jpg?raw=true)

## URLs / Links

Original Pyboard v1.1 at the Micropython-Store<br>
https://store.micropython.org/product/PYBv1.1#_

Pyboard v1.1 Pinout-Picture<br>
https://store.micropython.org/media/products/PYBv1_1-E.jpg

My start around 2 years ago (October 2020)<br>
https://forum.micropython.org/viewtopic.php?f=6&t=9219

First Tutorial from User @apples in the forum of micropython.org<br>
https://forum.micropython.org/viewtopic.php?f=6&t=9496

Arduino_Core_STM32 v2.3.0 (STM32Duino)<br>
https://github.com/stm32duino/Arduino_Core_STM32

![STM32Duino](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/BoardsManager_STM32Duino.jpg?raw=true)

STM32CubeProgrammer v2.11.0 ( I used the Win64 version )<br>
https://www.st.com/en/development-tools/stm32cubeprog.html
<br>

## Files changed

SdFat Arduino Library v2.20 ( SdFatConfig.h )
```
C:\Users\guido\Documents\Arduino\libraries\SdFat\src\SdFatConfig.h
```
![SdFatConfig_h](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/SdFatConfig_h_changes.jpg?raw=true)

STM32Duino Core v2.3.0 ( variant_generic.h )
```
C:\Users\guido\AppData\Local\Arduino15\packages\STMicroelectronics\hardware\stm32\2.3.0\variants\STM32F4xx\F405RGT_F415RGT\variant_generic.h
```
![variant_generic_h](https://github.com/guidol70/RunCPM_Pyboard_v1_1/raw/main/pictures/variant_generic_h_changes.jpg?raw=true)

<br>

## File not needed to be changed anymore

("old" Tutorial tells something about change 
```
FLASH_LATENCY_5
```

STM32Duino Core v2.3.0 ( variant_generic.cpp )
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

STM32CubeProgrammer DFU Upload-Log
```
Sketch uses 110720 bytes (10%) of program storage space. Maximum is 1048576 bytes.
Global variables use 71628 bytes (54%) of dynamic memory, leaving 59444 bytes for local variables. Maximum is 131072 bytes.
C:\Users\guido\AppData\Local\Arduino15\packages\STMicroelectronics\tools\STM32Tools\2.1.1/win/busybox.exe sh C:\Users\guido\AppData\Local\Arduino15\packages\STMicroelectronics\tools\STM32Tools\2.1.1/stm32CubeProg.sh 2 C:\Users\guido\AppData\Local\Temp\arduino_build_442781/RunCPM_PyBoard11.ino.bin -g 
      -------------------------------------------------------------------
                       STM32CubeProgrammer v2.11.0                  
      -------------------------------------------------------------------



USB speed   : Full Speed (12MBit/s)
Manuf. ID   : STMicroelectronics
Product ID  : STM32  BOOTLOADER
SN          : 316D386B3436
DFU protocol: 1.1
Board       : --
Device ID   : 0x0413
Device name : STM32F405xx/F407xx/F415xx/F417xx
Flash size  : 1 MBytes (default)
Device type : MCU
Revision ID : --  
Device CPU  : Cortex-M4


Memory Programming ...
Opening and parsing file: RunCPM_PyBoard11.ino.bin
  File          : RunCPM_PyBoard11.ino.bin
  Size          : 108.54 KB 
  Address       : 0x08000000 


Erasing memory corresponding to segment 0:
Erasing internal memory sectors [0 4]
erasing sector 0000 @: 0x08000000 done
erasing sector 0001 @: 0x08004000 done
erasing sector 0002 @: 0x08008000 done
erasing sector 0003 @: 0x0800c000 done
erasing sector 0004 @: 0x08010000 done
Download in Progress:


File download complete
Time elapsed during download operation: 00:00:04.627

RUNNING Program ... 
  Address:      : 0x8000000
Start operation achieved successfully
```

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

<br>

## Main features of the hardware

- STM32F405RG(T6) microcontroller<br>
- 168 MHz Cortex M4 CPU with hardware floating point<br>
- 1024KiB flash ROM and 192KiB RAM<br>
- Micro USB connector for power and serial communication<br>
- Micro SD card slot, supporting standard and high capacity SD cards<br>
- 3-axis accelerometer (MMA7660)<br>
- Real time clock with optional battery backup<br>
- 24 GPIO on left and right edges and 5 GPIO on bottom row, plus LED and switch GPIO available on bottom row<br>
- 3x 12-bit analog to digital converters, available on 16 pins, 4 with analog ground shielding<br>
- 2x 12-bit digital to analog (DAC) converters, available on pins X5 and X6<br>
- 4 LEDs (red, green, yellow and blue)<br>
- 1 reset and 1 user switch<br>
- On-board 3.3V LDO voltage regulator, capable of supplying up to 250mA, input voltage range 3.6V to 16V<br>
- DFU bootloader in ROM for easy upgrading of firmware<br>
- The two mounting tabs on the pyboard have perforations so that you can snap them off cleanly if needed.<br>
