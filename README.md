# Cybersecurity : CSN150-Doc-Template

## Name of Project
ESP32-CAM Camera Setup

## Purpose
Install and configure the camera firmware on the ESP32-CAM module using the Arduino IDE, and test camera streaming functionality over Wi-Fi. 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation
https://lastminuteengineers.com/getting-started-with-esp32-cam/
https://github.com/ereedsanchez/CSN150-Doc-Template)

##### Video 1: 
   Video 1: *(https://youtu.be/4inE-n6kXSE)*


##### Other Links: 


## Steps I followed
1. Watched the professor's YouTube tutorial in full.
2. Connected the ESP32-CAM module to my computer using a USB-to-Serial adapter:
3. Installed the ESP32 board package via Board Manager.
4. Selected AI Thinker ESP32-CAM from the Tools > Board menu.
5. Selected the proper COM port, set Baud Rate: 115200
6. Opened the example sketch CameraWebServer from File > Examples > ESP32 > Camera.
7. Updated the sketch with my Wi-Fi SSID and password.

## Problems
After uploading/running the sketch and resetting the ESP32-CAM, the Serial Monitor remained blank—no IP address, no output. The board was powered and appeared to boot, but nothing printed to the Serial Monitor.

### Solution
I used Chatgpt mostly and google and i was  the guided through the following troubleshooting:
Ensure Serial Monitor baud rate is set to 115200, not a lower value like 9600.
Make sure the Serial Monitor is opened after pressing the reset button on the ESP32-CAM.
Unplug and plug the cable, startover the cable is working and the ESP32 becuase my last project was very successful

Ultimately, it was determined that the sketch likely uploaded correctly, and the issue was most likely a Serial communication mismatch or power instability. Following the solution advice, I verified the serial settings and retried the process.

### Example of Sketch Used

## Final Report
The ESP32-CAM camera firmware setup was mostly successful. The sketch uploaded, and the wiring was verified correctly. However, the Serial Monitor didn’t show any output initially. After troubleshooting serial settings and connections. Actually after finishing the report the serial monitor finally give some mesage but i beleive its because am using my hotspot however the message mean my ESP32-CAM is successfully booted
