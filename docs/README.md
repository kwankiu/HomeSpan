# Welcome!

## This is a fork that was modified for [DashHome](https://github.com/DashHome/DashHome)
## I forked it because i would like to test and work on a few features
## I will do this only on my free time, there is no priority which feature will come first and I might never have time to work on this, so dont expect anything.

## Some Ideas/Thoughts :
- Add support for OTA upload through a Web Server
- Create a system log file and output all system logs to web log (useful if you do not have access to the Serial Monitor)
- Print mac address and wifi channel if WifiApAdress is true (for ESP8266 ESPNOW)
- Add ESP-32 HomeKit Camera support
- Add support to use this library for ESP8266
- Create a Web Dashboard (Check out my another project [DashHome](https://github.com/DashHome/DashHome))
- Support to control other Smart Home device (such as Tuya devices) and act as a bridge (Check out my another project [DashHome](https://github.com/DashHome/DashHome))
- Alternative control of accessories (eg Control then through a web dashboard or ESPNOW)

Welcome to HomeSpan - a robust and extremely easy-to-use Arduino library for creating your own [ESP32-based](https://www.espressif.com/en/products/modules/esp32) HomeKit devices entirely within the [Arduino IDE](http://www.arduino.cc).

HomeSpan provides a microcontroller-focused implementation of [Apple's HomeKit Accessory Protocol Specification Release R2 (HAP-R2)](https://developer.apple.com/homekit/specification/) designed specifically for the Espressif ESP32 microcontroller running within the Arduino IDE.  HomeSpan pairs directly to HomeKit via your home WiFi network without the need for any external bridges or components.  With HomeSpan you can use the full power of the ESP32's I/O functionality to create custom control software and/or hardware to automatically operate external devices from the Home App on your iPhone, iPad, or Mac, or with Siri.

HomeSpan requires version 2.0.0 or later of the [Arduino-ESP32 Board Manager](https://github.com/espressif/arduino-esp32), and has been tested up through version 2.0.6 (recommended).  HomeSpan can be run on the original ESP32 as well as Espressif's ESP32-S2, ESP32-C3, and ESP32-S3 chips.

### HomeSpan Highlights

* Provides a natural, intuitive, and **very** easy-to-use framework
* Utilizes a unique *Service-Centric* approach to creating HomeKit devices
* Takes full advantage of the widely-popular Arduino IDE
* 100% HAP-R2 compliance
* 41 integrated HomeKit Services
* Operates in either Accessory or Bridge mode
* Supports pairing with Setup Codes or QR Codes

### For the HomeSpan Developer

* Extensive use of the Arduino Serial Monitor
  * Real-time, easy-to-understand diagnostics
  * Complete transparency to every underlying HomeKit action, data request, and data response
  * Command-line interface with a variety of info, debugging, and configuration commands
* Built-in database validation to ensure your configuration meets all HAP requirements
* Dedicated classes that utilize the ESP32's 16-channel PWM peripheral for easy control of:
  * LED Brightness
  * Servo Motors
* Integrated Push Button and Toggle Switch functionality supporting single, double, and long presses of:
  * Physical pushbuttons that connect an ESP32 pin to either ground or VCC
  * Touch pads/sensors connected to an ESP32 pin (for ESP32 devices that support touch pads)
* Integrated access to the ESP32's on-chip Remote Control peripheral for easy generation of IR and RF signals
* Dedicated classes to control one- and two-wire addressable RGB and RGBW LEDs and LED strips
* Dedicated class that faciliates seemless point-to-point communication between ESP32 devices using ESP-NOW
* Integrated Web Log for user-defined log messages
* Extensively-commented Tutorial Sketches taking you from the very basics of HomeSpan through advanced HomeKit topics
* Additional examples and projects showcasing real-world implementations of HomeSpan
* A complete set of documentation explaining every aspect of the HomeSpan API

### For the HomeSpan End-User

* Embedded WiFi Access Point and Web Interface to allow end-users (non-developers) to:
  * Set up Homespan with their own home WiFi Credentials
  * Create their own HomeKit Pairing Setup Code
* Status LED and Control Button to allow end-users to:
  * Force-unpair the device from HomeKit
  * Perform a Factory Reset
  * Launch the WiFi Access Point
* A standalone, detailed End-User Guide

## ❗Latest Update - HomeSpan 1.7.1 (2/4/2023)

* **SpanPoint support for the ESP8266!**
  * Use ESP-NOW on an ESP8266 to connect to HomeSpan running on an ESP32
  * See the [SpanPoint Tutorial Page](NOW.md) for more info as well as a detailed ESP8266 example
  
* **SpanPoint WiFi channel scanning upgrade**
  * SpanPoint now saves the last WiFi channel successfully used for transmission in non-volatile storage
  * Avoids the need for SpanPoint to restart a full scan of all channels upon reboot
  * Dramatically extends battery life when used in conjunction with deep-sleep functionality
  
* **New SpanToggle class**
  * Similar to SpanButton, but designed for toggle switches
  * Integrated de-bounce logic prevents false triggers
  * Ideal for use with Contact Sensors
  * See the [API Reference](Reference.md) for details
  
* **Added Television Speaker Service**
  * Control the volume of a Television from Apple's Remote App
  * See the [Television Services Page](TVServices.md) for details and examples
  
* **Added support for byte-array ("DATA") Characteristics**
  * Useful for experimentation with other HomeKit applications, such as *Eve for HomeKit*
  * Includes three new Characteristic methods: `setData()`, `getData()`, and `getNewData()`
  * Includes new macro `CUSTOM_CHAR_DATA()` to easily create custom byte-array Characteristics
  * See the [API Reference](Reference.md) for details
  
* **LedPin upgrade**
  * New option to invert the PWM signal
  * Useful for generating two, separate out-of-phase PWM signals (one inverted, one not) to drive certain two-pin devices in a push/pull manner, such as a piezo-electric buzzer
  * See the [PWM Page](PWM.md) for details

* **Bug Fixes**
  * Added logic to prevent the extraneous broadcasting of an Access Point SSID when SpanPoint is being used

See [Releases](https://github.com/HomeSpan/HomeSpan/releases) for details on all changes and bug fixes included in this update.

# HomeSpan Resources

HomeSpan includes the following documentation:

* [Getting Started with HomeSpan](GettingStarted.md) - setting up the software and the hardware needed to develop HomeSpan devices
* [HomeSpan API Overview](Overview.md) - an overview of the HomeSpan API, including a step-by-step guide to developing your first HomeSpan Sketch
* [HomeSpan Tutorials](Tutorials.md) - a guide to HomeSpan's tutorial-sketches
* [HomeSpan Services and Characteristics](ServiceList.md) - a list of all HAP Services and Characterstics supported by HomeSpan
* [HomeSpan Accessory Categories](Categories.md) - a list of all HAP Accessory Categories defined by HomeSpan
* [HomeSpan Command-Line Interface (CLI)](CLI.md) - configure a HomeSpan device's WiFi Credentials, modify its HomeKit Setup Code, monitor and update its status, and access detailed, real-time device diagnostics from the Arduino IDE Serial Monitor
* [HomeSpan User Guide](UserGuide.md) - turnkey instructions on how to configure an already-programmed HomeSpan device's WiFi Credentials, modify its HomeKit Setup Code, and pair the device to HomeKit.  No computer needed!
* [HomeSpan API Reference](Reference.md) - a complete guide to the HomeSpan Library API
* [HomeSpan QR Codes](QRCodes.md) - create and use QR Codes for pairing HomeSpan devices
* [HomeSpan OTA](OTA.md) - update your sketches Over-the-Air directly from the Arduino IDE without a serial connection
* [HomeSpan PWM](PWM.md) - integrated control of standard LEDs and Servo Motors using the ESP32's on-chip PWM peripheral
* [HomeSpan RFControl](RMT.md) - easy generation of RF and IR Remote Control signals using the ESP32's on-chip RMT peripheral
* [HomeSpan Pixels](Pixels.md) - integrated control of addressable one- and two-wire RGB and RGBW LEDs and LED strips
* [HomeSpan SpanPoint](NOW.md) - facilitates point-to-point, bi-directional communication between ESP32 Devices using ESP-NOW
* [HomeSpan Television Services](TVServices.md) - how to use HomeKit's undocumented Television Services and Characteristics
* [HomeSpan Message Logging](Logging.md) - how to generate log messages for display on the Arduino Serial Monitor as well as optionally posted to an integrated Web Log page
* [HomeSpan Projects](https://github.com/topics/homespan) - real-world applications of the HomeSpan Library
* [HomeSpan FAQ](FAQ.md) - answers to frequently-asked questions
* [Solutions to Common Problems](Solutions.md) - resolutions to some common problems when using/compiling HomeSpan
* [HomeSpan Reference Sketches](https://github.com/HomeSpan/HomeSpanReferenceSketches) - a collection of self-contained Reference Sketches showcasing some of the more complex HomeKit Services, such as Thermostats and Irrigation Systems 

Note that all documentation is version-controlled and tied to each branch.  The *master* branch generally points to the latest release.  The *dev* branch, when available, will contain code under active development.

# External Resources

In addition to HomeSpan resources, developers who are new to HomeKit programming should download Apple's [HomeKit Accessory Protocol Specification, Release R2 (HAP-R2)](https://developer.apple.com/homekit/specification/). The download is free, but Apple requires you to register your Apple ID for access to the document.

You ***do not*** need to read the entire document.  The whole point of HomeSpan is that it implements all the required HAP operations under the hood so you can focus on just programming whatever logic is needed to control your real-world appliances (lights, fans, RF remote controls, etc.) with the device.  However, you will find Chapters 8 and 9 of the HAP guide to be an invaluable reference as it lists and describes all of the Services and Characteristics implemented in HomeSpan, many of which you will routinely utilize in your own HomeSpan sketches.

---

### Feedback or Questions?

Please consider adding to the [HomeSpan Discussion Board](https://github.com/HomeSpan/HomeSpan/discussions), or email me directly at [homespan@icloud.com](mailto:homespan@icloud.com).

### About the Author

HomeSpan was developed and continues to be maintained and supported by Gregg Berman.  It was originally conceived to solve the pesky problem of not being able to operate an RF-controlled kitchen vent hood with Siri.  I hope you find it useful as well as fun to use.

This is my second large-scale open-source project --- my first was the design of an open-source sytem for operating model railroads using nothing more than an Arduino Uno and Arduino Motor Shield to generate digital command and control (DCC) signals.  Though I have not been involved with the model railroading hobby for many years, videos showcasing my original system (dubbed DCC++), along with detailed tutorials of how it works, are still available on the [DCC++ YouTube Channel](https://www.youtube.com/@dcc2840/videos). 
