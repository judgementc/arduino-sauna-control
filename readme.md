Arduino Sauna Control
==== 

The arduino-sauna-control code when paired with appropriate HW allows one to replace a broken proprietary
control system of an Infrared Sauna.

HW Required
 - Arduino
 - LCDKeypad 16x2 screen
 - 4.7Kohm resister
 -  Dallas Thermometer DS18B20 Temperature Probe preferably waterproof with 2-3m lead
 - 4 channel 10A relay board or a 2 channel 20A relay
       1 channel for Light
       1-2 for heaters (I broke to two circuits for heaters so I could use the 10A board)
 - Buzzer / Speaker
 - 5V Power Supply for Arduino
 - Highly Recommend a physical power switch! (see safety note below)
 - Appropriate wires
 - Fuses
 

 I took apart the old proprietary control system and gutted it, but used the power plugs/connections
 and the fuse box. I bypassed both the built-in control panel and the speakers. The built-in control
 panel was built for 12V and I didn't want to figure out how it worked when a simple LCDKeypad could
 replace it. As for the speakers, I just figure a bluetooth speaker or just a smartphone would be good 
 enough for sound.
 
 SAFTEY NOTE: As I was putting all of the components together, I found that while using the 4 Channel Relay Board
 if the Arduino did not supply 5V power to the VCC in port, that the circuits would fail closed instead of open. 
 This could prove disastrous if the Arduino power supply was broken for some reason. So I added a reverse
 logic variable to have the pins Hot when the unit/overhead light are off instead of for when on. Also highly
 recommend a physical switch to power the whole thing off and on for safety sake.
 
 
 
 Features desired to raise to a 1.0 version: 
----
  a. Preheat mode with indication Sauna is to operating temp. I am thinking a beep when a minimum operating temperature is reached.
  b. Add ability to change between C and F.
 
 Future potential features that could be added: 
----
  a. Add variable stored in EEProm for tracking hours in use ( potentially since manually reset )
  b. IP connectivity for monitoring purposes (not likely)
  c. Track time for individual person in Sauna (If wanted to track days would need to add a RTC to the mix)
 

 Rev History 
----
 .7 Fixed the reverse logic for the Heater Operation. Also adjusted up the Maximums for temp. - Tested as functional and works.
 .6 Changed logic to allow for reverse logic on the control board, added delay to reading temp probe when light is turned off or on.
 .5 Bug fixes mostly and first fully functional version (I thought)
 .4 Bug fixes - First potentially usable version
 .3 Bug fixes and added Alarm State
 .2 First commit to Github
 .1 Initial logic
 
 Known Issues: 
----
- Temp in Sauna can crest 5F or more above the set temp due to the latent heat in the heaters.

Acknowledgements:
----
- A little code came from the arduino-sauna project posted by https:github.com/Kobra/arduino-sauna
- Some code was brought in and modified from sample code for the LCDKeypad at https://www.dfrobot.com/wiki/index.php/Arduino_LCD_KeyPad_Shield_(SKU:_DFR0009)#Sample_Code