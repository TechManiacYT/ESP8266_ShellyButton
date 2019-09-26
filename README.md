# ESP8266_ShellyButton

Goal of these short Arduino-IDE scripts is to provide a small software to interface with the excellent Shelly Smart Home devices.<br>I do not want to use a home server, or cloud for basic functions such as switching the light, but some switches could not be hard wired to the Shelly switches.
Shelly themself offer the ability to use a switch, and also to use a switch over wifi, however some functions are not available, for example:

* Battery powered wifi switch
* Adjust the brightness of a Shelly RGBW2 over wifi
* Adjust the brightness of a single RGBW2 Shelly channel 
* For the shelly 2 relay devices: a 0,1,2 incremental switching

The software contains basically 2 parts
1) ESP8266 basic software and button interface (long/short push detection without interrupts)
2) Shelly wifi communication using the http JSON API (reading current status and adjusting accordingly, in case some setting was changed from another switch or cloud)
3) Giving some sort of feedback (LED brightness for the non-battery switches) according to the Shelly status
I will try to add more comments to the code, however I dont think the code is that hard to understand.

Requirements:
* ESP8266 (or later ESP32) Support
* JSON library (TODO:add link)


