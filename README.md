# reflash_printrboard
How to reflash the firmware on a printrboard

Download the latest printrboard firmware from [here](https://github.com/Printrbot/Marlin/releases/)
For the printrbot simple metal I used the file RevF4-v1-SimpleMetal.hex

Download avrdude
Connect a usbasp or other programmer cable to the SPI pins on the bottom of the printrboard. You don't need to use jumpers. You don't need to hit the reset button. If it doesn't work, unplug and try spinning the programmer 180.
Type in the following to terminal:  
avrdude -c usbasp -p at90usb1286 -U lfuse:w:0xDE:m -U hfuse:w:0x9B:m -U efuse:w:0xF0:m  
avrdude -c usbasp -p at90usb1286 -U flash:w:<NAME_OF_YOUR_FILE.hex>:i  
