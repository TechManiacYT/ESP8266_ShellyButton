# ESP8266_ShellyButton

Goal of these short Arduino-IDE scripts is to provide a small software to interface with the excellent Shelly Smart Home devices.<br>I do not want to use a home server, or cloud, for basic functions such as switching the light, but some switches could not be hard wired to the Shelly switches.
Shelly themself offer the ability to use a seperate shelly device as wifi-switch, however some functions are not available, for example:

* Battery powered wifi switch
* Adjust the brightness of a Shelly RGBW2 over wifi
* Adjust the brightness of a single RGBW2 Shelly channel (Shelly RGBW2 has no incr or decr functionality)
* For the shelly 2 relay devices: a 0,1,2 incremental switching

The software contains basically 3 parts
1) ESP8266 basic software and button interface (long/short push detection without interrupts)
2) Shelly wifi communication using the http JSON API (reading current status and adjusting accordingly, in case some setting was changed from another switch or cloud)
3) Giving some sort of feedback (LED brightness for the non-battery switches) according to the Shelly status
I will try to add more comments to the code, however I dont think the code is that hard to understand.

Requirements:
* ESP8266 (I will add ESP32 support as soon as I receive my samples)
* JSON library (https://arduinojson.org/v6/doc/installation/)

Result - 3 Different configurations are available:

1) Normal shelly relay ON/OFF switch
* possible to adress the relay, regardless of shelly1 or shelly 2
* Toggle the status of the relay by button push
* Indicate the status of the relay on the LED (LOW, HIGH)

2) Shelly2 Shelly2.5 relay 0/1/2 configuration
* a lamp has 2 bulbs, but is treated by one single switch
* every push of the button should change the status of the lamp: OFF, 1 Lamp on, Both lamps on
* Indicate the status of the relays on the LED (LOW, MID, HIGH)

3) Shelly RGBW2 White Mode
* short push will toggle ON/OFF
* Long push will increase/decrease the brightness
* Indicate the status of the relay on the LED (LOW, HIGH)

Status:
* early stage
* no failsafe operation yet (for example, what happens if a relay is not online)
* Need code cleanup

