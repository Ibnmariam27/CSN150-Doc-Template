# Cybersecurity : CSN150-Doc-Template

## Name of Project
ESP32 WiFi Scanner

## Purpose
This project uses an ESP32-CAM board to scan and list all nearby WiFi networks. The scan result shows each network's SSID, signal strength (RSSI), channel, and encryption type.

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)
* Arduino IDE

## Links to documentation

##### Video 1: 

##### Other Links: 


## Steps I followed
1.Opened the Arduino IDE.
2.Connected the ESP32-CAM to my computer using a USB-to-Serial adapter.
3.Selected the correct board from the Arduino menu:
Tools > Board > AI Thinker ESP32-CAM
4.Selected the correct COM port under Tools > Port
5.Set the baud rate to 115200 in the Serial Monitor.
6.Opened a new sketch and pasted the WiFi Scanner code (from the WiFiScan example or the code provided).
7.Opened the Serial Monitor and observed the list of nearby WiFi networks successfully printed.

## Problems
No issues at all. used chatgpt to guide me. its seems to be an easy one thou not lots of steps require

### Solution


### Example of Sketch Used
#include "WiFi.h"

void setup() {
  Serial.begin(115200);
  delay(1000);
  Serial.println("Setup done");

  Serial.println("Scan start");

  int n = WiFi.scanNetworks();
  Serial.println("Scan done");
  if (n == 0) {
    Serial.println("No networks found");
  } else {
    Serial.println(String(n) + " networks found");
    Serial.println("Nr | SSID            | RSSI | CH | Encryption");
    for (int i = 0; i < n; ++i) {
      Serial.print(i + 1);
      Serial.print(" | ");
      Serial.print(WiFi.SSID(i));
      Serial.print(" | ");
      Serial.print(WiFi.RSSI(i));
      Serial.print(" | ");
      Serial.print(WiFi.channel(i));
      Serial.print(" | ");
      switch (WiFi.encryptionType(i)) {
        case WIFI_AUTH_OPEN: Serial.println("Open"); break;
        case WIFI_AUTH_WEP: Serial.println("WEP"); break;
        case WIFI_AUTH_WPA_PSK: Serial.println("WPA"); break;
        case WIFI_AUTH_WPA2_PSK: Serial.println("WPA2"); break;
        case WIFI_AUTH_WPA_WPA2_PSK: Serial.println("WPA+WPA2"); break;
        case WIFI_AUTH_WPA2_ENTERPRISE: Serial.println("WPA2-EAP"); break;
        case WIFI_AUTH_WPA3_PSK: Serial.println("WPA3"); break;
        default: Serial.println("Unknown");
      }
      delay(10);
    }
  }
}

void loop() {
  // Nothing here
}


## Final Report
The ESP32-CAM WiFi Scanner project was successful. And encoutered no issues at all.
