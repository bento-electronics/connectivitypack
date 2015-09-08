Connectivity Pack
===================

The connectivity kit contains 3 modules for wireless communication as well as an RFID reader. These modules generally talk to the Arduino over a serial protocol (UART for the wireless modules, SPI for the RFID module) and act as a direct pipe
to the other  "side" e.g. a phone app, webserver or RFID tag.

Bluetooth Serial Transceiver HC-05
-------------
HC-05 is a popular Bluetooth module used to emulate a UART (Universal Asynchronouse Receiver/Transmitter) interface over the Bluetooth wireless protocol. Operation is meant to be very simple; either side of the serial connection can simply write to and read bytes from the other side.

Hooking this module up to the existing TX/RX pins on an Arduino will allow you to immediately send and receive data using the built in hardware serial library. However, this connection is also used by the board when connected to your computer via USB, which means you will need to disconnect HC-05 everytime you upload new code. The solution is to use Arduino's SoftwareSerial library to create a UART connection on two other pins of your selection.

**NOTE:** Always remember to cross TX/RX wires when connecting UART devices. i.e., TX from one side connects to RX on the other side, and vice versa. 

> http://www.instructables.com/id/Arduino-AND-Bluetooth-HC-05-Connecting-easily/
> http://arduinofy.blogspot.com/2013/10/tutorial-programming-hc-05-at-mode-with.html
> http://www.martyncurrey.com/arduino-with-hc-05-bluetooth-module-in-slave-mode/
> https://www.arduino.cc/en/Reference/SoftwareSerial
> https://www.arduino.cc/en/Reference/Serial

----------

Wifi Transceiver ESP8266
-------------
The ESP8266 is widely used in low-cost Arduino projects with an integrated TCP/IP stack and enough processing power to run it's own webserver onchip!
The module must be configured first with the SSID and password of your intended Wifi network. It can communicate with the Arduino via serial UART (careful; the module can only handle 3.3V level logic, so use a level-shifter or your own voltage divider from 5V!), has a plethora of functions that can be controlled using AT commands, and can run custom scripts in BASIC.
Check the tutorials below for more detailed information.
There also exist addons for the Arduino IDE that let you program the ESP8266 directly using Arduino code, but without needing an actual Arduino board!

> http://rancidbacon.com/files/kiwicon8/ESP8266_WiFi_Module_Quick_Start_Guide_v_1.0.4.pdf
> https://learn.sparkfun.com/tutorials/esp8266-thing-hookup-guide/installing-the-esp8266-arduino-addon
> https://github.com/esp8266/Arduino


> http://www.instructables.com/id/Using-the-ESP8266-module
> https://github.com/esp8266/esp8266-wiki/wiki
> http://www.esp8266.com/arduino
> https://www.sparkfun.com/products/13678

----------

RFID Reader MFRC-522
-------------
This module can read and write from the most common RFID card/tag standard (MIFARE Classic 1k i.e. ISO/IEC 14443 Type A) at short range. It includes an onboard antenna already tuned for the correct operating frequency of 13.56MHz.
Arduinos can communicate and send commands over SPI to this module, but the provided library should be used as it provides a simple interface to the reader's functions.

> https://github.com/miguelbalboa/rfid
> http://makecourse.weebly.com/week10segment1.html
----------


Bluetooth LE Module HM-10
-------------
This module is similar to the HC-05, but uses the new Bluetooth Low Energy protocol instead. It essentially acts as a beacon, which can be written to over UART and also receive data from smartphones. 
Like many other connectivity modules, it can be controlled using AT commands sent over UART.

> http://www.openhwdesign.com/ble-hm-10/
> https://github.com/danasf/hm10-android-arduino
> https://developer.android.com/guide/topics/connectivity/bluetooth-le.html
