# Cybersecurity : CSN150-Doc-Template

## Name of Project
ESP32 Introduction

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " Wifiscanner". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation

##### Video 1: 

##### Other Links: 


## Steps I followed
1. Watched the professor's YouTube tutorial in full.
2. Downloaded and installed the latest Arduino IDE.
3. Connected the ESP32-CAM module to my computer using a micro USB data cable via a USB-to-Serial adapter.
4. In the Arduino IDE:
   - Opened **File > Preferences**, added the ESP32 board URL:
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```
   - Went to **Tools > Board > Board Manager**, searched for “ESP32”, and installed it.
   - Selected the board as **AI Thinker ESP32-CAM** under Tools > Board.
   - Set the correct **Port** and upload settings:
     - Baud Rate: 115200
     - Partition Scheme: “Huge APP”
5. Wrote and uploaded the Blink sketch:
   - The LED was connected to GPIO4.
   - Sketch toggled the LED on and off every second.
6. Opened Serial Monitor to verify the board output and functionality.



## Problems
Note your problems or errors here.  Google any error you may come across, and not what you tried (even if it does not work), and what was the final answer. Document your errors and solutions that worked for you.  

1. E (485) camera: Camera probe failed with error 0x105(ESP_ERR_NOT_FOUND)
Camera init failed with error 0x105
 How did I solve: 

### Example Problem
1. Arduino code will not load on ESP32 Cam.
   Answer: Camera drivers were incorrect I needed to install the driver: [https://www.wch-ic.com/downloads/CH341SER_ZIP.html](https://github.com/martin-ger/esp32_nat_router).  I used file, "CH341SER.ZIP" and it worked.


## Final Report
