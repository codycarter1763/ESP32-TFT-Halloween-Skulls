<div align="center">
  <h1>ESP32 TFT Animated Halloween Skulls</h1>
</div>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e3c41563-c999-483f-a331-19dc9efcca93" width=40% height=40%>
</p>

<h1>About</h1>
<h6> &emsp; This is a guide and build log of how to implement animated eyes into a halloween skull using the ESP32 microcontroller and two 1.44" SPI TFT screens. This is a fairly easy project, though it does take some TFT_eSPI library configuration to optimize the ESP32 and the 1.44" SPI TFT hardware.</h6>

<h1>Parts List</h1>

- Plastic Skull or other halloween decoration
- ESP32 Microcontroller Board
- 2x 1.44" TFT LCD with SPI 128x128
- 5 Volt Power Supply
  - If using 12 V supply make sure to use a buck voltage converter as the max recommended Vin     voltage is 5V
- Jumper wires for connection

<h1>Wiring</h1>

| TFT | ESP32 |
|-----------------|-----------------|
| MOSI or SDA | D23 |
| SCL | D18 |
| CS TFT 1 | D22 |
| CS TFT 2 | D21 |
| DC or A0 | D2 |
| RST | D4 |
| BL or LED | 3.3V (Or 100ohm resistor in series with 5V) |

<h1>Setting Up Arduino Libraries</h1>

1. Download the ESP32 board package by navigating to Boards Manager and typing esp32
2. Download the eSPI Arduino library by navigating to Library Manager and typing TFT_eSPI
3. Navigate to your Arduino folder through your computer's file manager, click on libraries, click on TFT_eSPI, open User_Setup.h with Notepad++ or a similar notepad, scroll to around line 210 and edit the config to the following for ESP32 and particular display:

![Screenshot 2024-10-18 224908](https://github.com/user-attachments/assets/bb7206d9-0ecf-4d7c-96db-7ecae27ad309)

4. Save and close
5. Open up Animated_Eyes_2 example in eSPI library
6. Uncomment #define USE_DMA as the display performance will be better
7. If you want to configure the types of eyes to be displayed, navigate to config.h and uncomment #include fucntions for whichever design you prefer
8. Enjoy!



