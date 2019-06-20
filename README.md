# QHY5 on breadboard
This repository is a result of reverse engineering of the QHY5 astronomical guide camera 

# What is this repository about
The goal of this repository is to share my investigations about how to create an equivalent of the well-known QHY5 grayscale astrocamera by just wiring two fairly cheap boards (the MT9M001 adapter board and a the CY7C68013A dev board) together.

# Wiring table
| Description | CY7C68013A | CY7C68013A 56-pin | MT9M001 | MT9M001 board pin | Note |
| ----------- | ---------- | ----------------- | ------- | ----------------- | ---- | 
| CLKIN       | CTRL0 + PA3| 36 + 43           | 29      | 8                 | Connect CTRL0 and PA3 in parallel |
| SCL         | SCL        | 22                | 46      | 3                 |      |
| SDA         | SDA        | 23                | 45      | 4                 |      |
| PIXCLK      | --         | --                | 31      | 7                 | Not connected |
| OE          | --         | --                | 13      | --                | Wired to ground on the board |
| RESET       | PA0        | 40                | 10      | 19                |      |
| STANDBY     | GND        | Any GND           | 7       | 20                | Connect to any GND pin on the controller board |
| TRIGGER     | --         | --                | 8       | 21                | Not connected |
| HSYNC (LV)  | --         | --                | 40      | 9                 | Not connected |
| VSYNC (FW)  | --         | --                | 41      | 5                 | Not connected |
| STROBE      | --         | --                | 39      | 22                | Not connected |
| VCC         | VCC        | Any VCC           | Many    | 1                 |      |
| GND         | GND        | Any GND           | Many    | 2                 |      |
| DOUT 9      | PB7        | 32                | 36      | 9                 |      |
| DOUT 8      | PB6        | 31                | 35      | 10                |      |
| DOUT 7      | PB5        | 30                | 34      | 11                |      |
| DOUT 6      | PB4        | 29                | 33      | 12                |      |
| DOUT 5      | PB3        | 28                | 32      | 13                |      |
| DOUT 4      | PB2        | 27                | 28      | 14                |      |
| DOUT 3      | PB1        | 26                | 27      | 15                |      |
| DOUT 2      | PB0        | 25                | 26      | 16                |      |
| DOUT 1      | PD7        | 3                 | 25      | 17                |      |
| DOUT 0      | PD6        | 2                 | 24      | 18                |      |

# About hardware / boards
As a camera board I used the "MT9M001 1.3Mp HD CMOS Infrared Camera Module with Adapter board" from Arducam (http://www.arducam.com/product/mt9m001-1-3mp-hd-cmos-infrared-camera-module-adapter-board/). I found this board on ebay for about $18. ![](images/MT9M001-board.jpg?raw=true)

Controller board I used is a CY7C68013A development board from geeetech (http://www.geeetech.com/wiki/index.php/CY7C68013, also here https://sigrok.org/wiki/Lcsoft_Mini_Board). I ordered my board on aliexpress for less as 4 euro, you can found it by searching for "CY7C68013A USB logic analyzer core board". Probably you can found such boards on ebay too. ![](images/CY7C68013A.jpg?raw=true)

# Connection
As a prototype I used dupont wires 15 centimeter long to connect boards together.
 ![](images/camera-module.jpg?raw=true)
 ![](images/camera-module-back-side.jpg?raw=true)
 ![](images/controller-board.jpg?raw=true)