# Cybersecurity : CSN150-Doc-Template

## Name of Project
ESP32 Introduction

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " Wifiscanner". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation

##### Video 1: https://youtu.be/pRa3cijuuik

##### Other Links: https://youtu.be/CruPE6q51u0


## Steps I followed
1. Installed Arduino IDE from the official site.  
2. Added ESP32 board manager URL in Preferences.  
3. Installed “ESP32 by Espressif Systems” via Boards Manager.  
4. Connected ESP32-CAM using a USB-to-Serial adapter.  
5. Selected “AI Thinker ESP32-CAM” as the board and correct COM port.  
6. Opened and uploaded the “WiFiScanner” sketch.  
7. Opened Serial Monitor to confirm WiFi networks were detected.  

## Problems
Problem 1 — Port not showing / “No matching device found”
Symptom: Arduino IDE shows no COM port, or upload fails with ERROR: no device found.
What I tried: Replugged cable, tried different USB ports, checked Device Manager, rebooted PC

Problem 2 — Camera init failed (error 0x105)
Symptom: Serial monitor shows Camera probe failed with error 0x105.
Root cause: Loose camera ribbon cable or wrong camera model in code.
Solution: Reseated the camera ribbon cable and selected the correct camera model in the sketch.

Problem 3 — Insufficient power / module resets during WiFi scan

Symptom: ESP32 resets during scan or camera streaming, or WiFi fails to connect.
What I tried: Used laptop USB, tried different ports.
Root cause: ESP32-CAM can draw high current (especially when camera + WiFi active). Many USB ports cannot supply steady 5V/500–900mA spikes.
How I solved: Used a dedicated 5V power supply or powered via a stable 5V regulator instead of directly from weak USB port. Problem resolved.



## Final Report
In the end, I successfully set up the ESP32 environment and ran the WiFiScanner sketch. I learned how to install board packages, troubleshoot serial connections, and solve power-related issues. This project helped me understand how embedded devices connect to wireless networks and how small setup mistakes (like weak power or wrong wiring) can affect performance.

