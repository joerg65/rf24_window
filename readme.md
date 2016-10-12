Magnetic RF24 Window Sensor

Runs on ATtiny84.
Monitors the REED contact. It sends every 4s the state of contact and battery voltage via nRF24.
It goes to sleep after sending. The current consumption is about 17uA average. A lithium cell
CR2450 (650mAh), should stay about 4 years.

To make it with Eclipse, it must be added the 'AVR Eclipse Plugin' to Eclipse.
To import the source code to Eclipse I found the easiest way as this:

Select File/New/Other and then select C Project and Next. Give Project name and select AVR Cross Target Application and Next. Deselect Debug and the select Finish.
Next, select your new Project with right mouse click and select Import.../Filesystem and browse for the source code folder. Mark in the left window to select everything and select Finish.

It should build now without errors. To build select Projec t/Build Project. The output should be:
```
Device: attiny84

Program:    3488 bytes (42.6% Full)
(.text + .data + .bootloader)

Data:        116 bytes (22.7% Full)
(.data + .bss + .noinit)


Finished building: sizedummy
 

16:41:36 Build Finished (took 1s.283ms)
```
