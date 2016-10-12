Magnetic RF24 Window Sensor

Runs on ATtiny84. This is part of my Alarm Central written on Odroid C1 / Android.
Monitors the REED contact. It sends every 4s the state of contact and battery voltage via nRF24.
After sending the cpu goes sleep. The current consumption is about 17uA average. A lithium cell CR2450 (650mAh), should stay about 4 years. To ensure the minimum of current during sleeping the Brown Out Detection is switched off, this made me to save data like AES key and node to Flash memory, as the EEProm data was inconsistent with switched off Brown Out Detection.  
An unconfigured sensor sends it node FFh to the Central in plain data then changes to receiving mode. The Central does a autonumbering an sends the node and the AES key to the sensor. The sensor stores this data to its Flash and does a reboot. From now on it sends every 4 seconds or and pin change of reed contact node, battery value and state (open/closed) to the Central.

The basic of the mirf library I found here: https://github.com/MattKunze/avr-playground/tree/master/mirf  

And the AESLib I found here: https://github.com/DavyLandman/AESLib  

To make it with Eclipse, it must be added the 'AVR Eclipse Plugin' to Eclipse.  

To import the source code to Eclipse I found the easiest way as this:  

Select File/New/Other and then select C Project and Next. Give Project name and select AVR Cross Target Application and Next. Deselect Debug and the select Finish.
Next, select your new Project with right mouse click and select Import.../Filesystem and browse for the source code folder. Mark in the left window to select everything and select Finish.

It should build now without errors. To build select Project/Build Project. The output should be:
```
Device: attiny84

Program:    3488 bytes (42.6% Full)
(.text + .data + .bootloader)

Data:        116 bytes (22.7% Full)
(.data + .bss + .noinit)


Finished building: sizedummy
 

16:41:36 Build Finished (took 1s.283ms)
```
