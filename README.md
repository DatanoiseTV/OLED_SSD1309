OLED_SSD1306
============

Hyper Fast driver for SSD1306, only SPI, for Arduino and Teensy3

It's just an experiment. It's a blazing fast version of the official Adafruit_SSD1306 Library but modified for work only in SPI
mode but optimized for speed. With Teensy3.x it uses the Paul Stoffregen's SPI/DMA routine and for DUE it uses another another
hyper fast SPI code.
Only limitations on Teensy3... DC and CS puns must follow this relationship:

!(_cs ==  2 && _rs == 10) && !(_rs ==  2 && _cs == 10)
	 && !(_cs ==  6 && _rs ==  9) && !(_rs ==  6 && _cs ==  9)
	 && !(_cs == 20 && _rs == 23) && !(_rs == 20 && _cs == 23)
	 && !(_cs == 21 && _rs == 22) && !(_rs == 21 && _cs == 22))
	 
On example I used CS=10,DC=9 and works fine.