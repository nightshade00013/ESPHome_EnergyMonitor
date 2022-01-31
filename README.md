# Fork of DigiBLur's - Whole Home Power Monitoring with ESPHome

Whole home power monitoring and additional power circuits with ESPHome and Home Assistant. This implementation utilizes the ATM90E32AS based board from CircuitSetup and focuses on integration with HomeAssistant. Other home automation software supporting MQTT can also use this integration.

If you found this project helpful and want to throw a few bones my way I would greatly appreciate it. You have a couple options to do so. One is to make a purchase on Amazon using my affiliate link, donate through buy me a coffee, or toss a couple Satoshi to me using Bitcoin.

https://amzn.to/2v74aiY Amazon affiliate link, any purchases made after clicking this will help support the author. 
https://www.buymeacoffee.com/Slw0NRx donation link through Buy Me a Coffee. 
17pEPchqZrjVHv8oN3jKMDZp23A24j4Jj Bitcoin address for direct anonymous gifts.


Video demostration and setup courtesy of digiNRG.  Most information here will be viable to these YAML files.
https://youtu.be/BOgy6QbfeZk

ESP Home information for the atm90e32:   
https://esphome.io/components/sensor/atm90e32.html


Update 2019/08/24 - For v1.2 of the board your voltage calibration will be high, >64,000. This is normal.
Update 2022/01/30 - Major changes in this fork of the repo plus major adjustments to the read me files.  These changes should make things much easier to use.


Compatible parts for this setup can easily be found here:
https://circuitsetup.us/product-category/power-management/
Non-Affiliate Amazon links will be included for the CT's and Trasnformers.
Please consider using the Amazon Affiliate link above when purchasing if you would like to say thanks!

Amazon search for AC power Adapters - This link has a coupel results that should work.  Remember ALL of the boards sold by CircuitSetup will require a transformer that is between 9V AC and 12V AC.  Anything that is DC WILL NOT WORK!!!!!!!!!!  Also note that the plug is a 2.5MM anything smaller will have issues and anything larger WILL NOT WORK.!!

https://www.amazon.com/s?k=%22ac+to+ac%22+%22transformer%22+%222.5mm%22&crid=3SA7VWBELKP5S&sprefix=ac+to+ac+transformer+2.5mm+%2Caps%2C103&ref=nb_sb_noss

Amazon search for SCT's - Choose something that will support your expexted loads.  For a single 20A circuit one that is rated at 20A should suffice.
If you are doing a main panel setup take your panel service rating, most modern new installs will be a 200 Amp service, and choose two SCT's that will equal at minimum
what the main breaker will support divided in half.  In the US A 200 Amp panel should have two SCT's that are equal to at least 100 Amps.
In countries that ARE NOT split phase you should theoretically be able to use these meters but will need a SCT that can support the entire panel amperage.
https://www.amazon.com/s?k=Non-invasive+AC+Current+Sensor+Split+Core+Transformer&crid=3URMBOOXJLNRR&sprefix=non-invasive+ac+current+sensor+split+core+transformer%2Caps%2C105&ref=nb_sb_noss

### Sample Calibrations for AC Transformer
Here are common voltage calibrations for the Split Single Energy Meter:
For meter <= v1.3:
42080 - 9v AC Transformer 
32428 - 12v AC Transformer

For meter > v1.4:
38302 - 9v AC Transformer 
29462 - 12v AC Transformer 

For Meters >= v1.4 rev.3
3920 - 9v AC Transformer 

Here are common voltage calibrations for the Expandable 6 Channel Energy Meter:
For meter <= v1.2:
42080 - 9v AC Transformer
32428 - 12v AC Transformer

For meter > v1.3:
7305 - 9v AC Transformer

### Sample Calibrations for SCT's
Here are common current calibration values for the Split Single Phase Energy Meter when gain_pga is set to 4X:
200A/100mA SCT-024: 12597

Here are common current calibration values for the Split Single Phase Energy Meter when gain_pga is set to 2X:
20A/25mA SCT-006: 10170
100A/50mA SCT-013-000: 25498
120A/40mA SCT-016: 39473
Magnalab 100A: 46539

Here are common current calibrations for the Expandable 6 Channel Energy Meter when gain_pga is set to 1X:
20A/25mA SCT-006: 11131
30A/1V SCT-013-030: 8650
50A/1V SCT-013-050: 15420
80A/26.6mA SCT-010: 41996
100A/50ma SCT-013-000: 27961
120A/40mA: SCT-016: 41880


### Sample ESPHome YAML Configurations
NightShade4chan32.yaml - Included in this repo
digi_nrg_2chan32.yaml - Included in this repo   
digi_nrg_6chan32.yaml - Included in this repo
Note: If you elected to add expansion boards, refer to the two physical jumpers on the top of each expansion board. They will identify each of the CS_PINs you will need to include in the 6 channel example above. You can then replicate the code and change the CS_Pin and CT identifiers.

![alt text](https://raw.githubusercontent.com/nightshade00013/ESPHome_EnergyMonitor/master/jpgs/2chan_board.jpg "2 Channel")
![alt text](https://raw.githubusercontent.com/nightshade00013/ESPHome_EnergyMonitor/master/jpgs/energy_meter_solar_kit.jpg "4 Channel")  
![alt text](https://raw.githubusercontent.com/nightshade00013/ESPHome_EnergyMonitor/master/jpgs/6chan_board.jpg "6 Channel")  
![alt text](https://raw.githubusercontent.com/nightshade00013/ESPHome_EnergyMonitor/master/jpgs/Split%20Phase%20Monitor%204%20channel.jpg "Web Output Page")  
![alt text](https://raw.githubusercontent.com/nightshade00013/ESPHome_EnergyMonitor/master/jpgs/HA_Energy.jpg "HomeAssistant Energy Panel")  
