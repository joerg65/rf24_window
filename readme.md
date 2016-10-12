Magnetic RF24 Window Sensor

Runs on ATtiny84.
Monitors the REED contact. It sends every 4s the state of contact and battery voltage via nRF24.
It goes to sleep after sending. The current consumption is about 17uA average. A lithium cell
CR2450 (650mAh), should stay about 4 years.

To make it with Eclipse, it must be added the 'AVR Eclipse Plugin' to Eclipse.
Goto File/Import and select Existing code Makefile project and the AVR-GCC Toolchain. Then give the project name and browse for the downloaded folder.

