<div align="center">
  <h1>ESP32 TFT Animated Halloween Skulls</h1>
</div>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e3c41563-c999-483f-a331-19dc9efcca93" width=40% height=40%>
</p>

<h1>About</h1>
 &emsp; This is a guide and build log of how to implement animated eyes into a halloween skull using the ESP32 microcontroller and two 1.44" SPI TFT screens. This is a fairly easy project, though it does take some TFT_eSPI library configuration to optimize the ESP32 and the 1.44" SPI TFT hardware.

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
8. Time to install system into skull!

<h1>Skull Assembly</h1>

<p align="center">
  <img src="https://github.com/user-attachments/assets/19e2d2e3-2418-494b-9161-9be76953c31e" width=40% height=40%>
</p>

With my halloween skull, I cut the back off of the skull with a hacksaw and used a dremel to carve out the eye holes in the front. To keep moisture out of the skull, I used a thin sheet of transparent plastic similar to a milk carton to glue to the eye holes. That way, it'll add water protection and durability protection as the TFT screens can be a bit fragile.

As you can see in the photo above, I used a waterproof tape like duck tape to secure the screens just in case I needed to modify or fix my setup. I also used double sided tape to secure the ESP32 and buck converter (to step down my 12 volt supply to 5 volts) to the top of the skull to help protect against moisture damage in case some water did get inside. 

For the wiring, I spliced together female to female jumper wires used for breadboards to make the connections easy to install and modify in case of breakage. 

Once I made sure everything works as expected, I put the back half of the skull back on with waterproof tape to keep moisture out the best I could.

<h1>Closing</h1>

If you made it this far, thank you so much for reading about my animated halloween skulls build. Hopefully this inspired you to create your own animated eyes for halloween decorations or any other project you might be pursuing. 
