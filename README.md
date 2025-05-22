# Cybersecurity : CSN150-Doc-Template

## Name of Project
ESP32 WhatsApp Message Sender using CallMeBot API

## Purpose
To use an ESP32 development board to send automated WhatsApp messages using WiFi and the CallMeBot API. This project demonstrates how Internet of Things (IoT) devices can communicate directly with messaging platforms like WhatsApp.

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)
*ESP32 Dev Board
*Micro USB Data Cable
*Arduino IDE
*CallMeBot API (https://www.callmebot.com/)
*Personal WhatsApp Account


## Links to documentation
https://randomnerdtutorials.com/esp32-send-messages-whatsapp/

##### Video 1: 

##### Other Links: 


## Steps I followed
1.Opened Arduino IDE and connected ESP32 via USB
2.Selected the correct board: Tools > Board > ESP32 D
3.Selected the correct port: Tools > Port > Com
4.Used the following sketch:

## Problems
1. CallMeBot API Key Not Working
Initial API response said:
"This Bot is full. Please use a different number to generate your key."
2. No WhatsApp Message Received
After uploading the code and seeing "Connected to WiFi", nothing arrived on WhatsApp.
3. Serial Monitor Blank or Glitched
At one point the monitor only showed unreadable characters.

### Solution
1. Used a new number +34 694 242 562 to request a new API key.
2. Added debug lines in the code (e.g., printing full request URL).
Verified that the phone number included + and full international code.
Used URL encoding for the message (Hello%20from%20ESP32).
3.Made sure baud rate was set to 115200
Hit the RESET button on the ESP32 after uploading

### Example of Sketch Used
#include <WiFi.h>
#include <HTTPClient.h>

const char* ssid = "The name of my wifi";
const char* password = "and my password";

String phoneNumber = "my phone number";  
String apiKey = "the API thathave be send to my number";      

void setup() {
  Serial.begin(115200);
  Serial.println("ESP32 is starting...");

  WiFi.begin(ssid, password);
  Serial.print("Connecting to WiFi");

  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.print(".");
  }

  Serial.println("\n✅ Connected to WiFi!");
  sendMessage("Hello%20from%20ESP32");
}

void loop() {}

void sendMessage(String message) {
  if (WiFi.status() == WL_CONNECTED) {
    Serial.println("📡 Preparing to send message...");

    HTTPClient http;
    String url = "https://api.callmebot.com/whatsapp.php?phone=" + phoneNumber + "&text=" + message + "&apikey=" + apiKey;

    Serial.println("Request URL:");
    Serial.println(url);

    http.begin(url);
    int httpResponseCode = http.GET();

    Serial.print("HTTP Response code: ");
    Serial.println(httpResponseCode);

    if (httpResponseCode > 0) {
      String response = http.getString();
      Serial.println("Response:");
      Serial.println(response);
    } else {
      Serial.println("❌ Failed to send message");
    }

    http.end();
  } else {
    Serial.println("❌ Not connected to WiFi");
  }
}

## Final Report
it was successful
Serial monitor shows:
✅ Connected to WiFi!
📡 Preparing to send message...
HTTP Response code: 200
Message sent successfully!
and Whatapp message was received
