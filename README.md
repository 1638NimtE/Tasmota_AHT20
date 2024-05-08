#**Add sensors BMP180 and AHT10 AHT20 to Tasmota v 13.04**

    Ready file for upload to ESP8266  (Tasmota v13.04)  - firmware.bin

Upload used [Tasmotizer](https://github.com/tasmota/tasmotizer)

Tunning pin I2C Tasmota

    AHT20_I2C_pin_Tasmota.png
   ![plot](https://github.com/1638NimtE/Tasmota_AHT20/blob/main/AHT20_I2C_pin_Tasmota.png)
    
##***Changed for compilate firmware.bin:***

###Changed in file - my_user_config.h (from Tasmota v13.04 Developer)
    
Deactivate line (sensors supports 0x38):    
    
    //  617 // VEML6070    
    //  668 // ADE7953
 
Activate line:
    
    614 BMP180/280
    
    690 AHT1x //The comment says only adress 0x38 but basicaly it supports 0x38 and 0x39 but for now only one sensor at a time.
    
    691 AHT2x 
  ![plot](https://github.com/1638NimtE/Tasmota_AHT20/blob/main/01_my_user_config.h%20_active_%20AHT10%20AHT20.PNG)
  
###Changed in file - xsns_63_aht1x.ino

    in line 64 address B1 -> BE :

    #define AHTX_CMD     0xB1  ->  #define AHTX_CMD     0xBE
   ![plot](https://github.com/1638NimtE/Tasmota_AHT20/blob/main/02_%20xsns_63_aht1x_%20change%20address%20B1%20to%20BE.PNG)
