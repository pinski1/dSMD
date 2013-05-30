#dSMD#
#####dSpin Stepper Motor Driver#####

This is a triple axis stepper motor driver board based on the L6470 chip.

The L6470 is a very advanced stepper motor driver chip. It can be controlled accurately though an SPI interface. Through this interface acceleration, decceleration, maximum speed and minimum speed can be programmed in. This then allows the user to simply command the chip to move the motor in a specific direction by 'n' number of steps. Alternatively a target speed or a target position may be set. The aim is to reduce the overhead on the host processor for motion control.

This board puts 3 of these fantastic chips together on a single PCB. This should be ideal for a CNC or 3D printer with steppers requiring up to 3 Amps each.

Please note:
* That should you require a fourth or fifth stepper, say for an extruder/s then this will require a seperate board.
* This board has yet to be prototyped so I cannot offer any guarantees of it working.

More information on the L6470 can be found [here](http://www.st.com/internet/analog/product/248592.jsp).

##The Board##
In addition to the 3 stepper motor drivers the board also contains connections for attaching a power supply, 6 limit switches which are also conneced to a 10 way IDC header, a 16 way IDC header for connecting to your host processor of choice.

###Dimensions###
**To be checked**

###Power Supply Input###
* Motor supply: +8 to +45V at a maximum of 9A
* Logic supply: +5V at a maximum of 0.2A

Power can be supplied either via screw terminals or a PC PSU molex connector.

###Endstops Pinout####

|Pin Func|Pin|Pin|Pin Func|
|---:|:--:|:--:|:---|
|GND|1|2|+5V|
|min_x|3|4|max_x|
|min_y|5|6|max_y|
|min_z|7|8|max_z|
|GND|9|10|+5V|

###Control Pinout####

|Pin Func|Pin|Pin|Pin Func|
|---:|:--:|:--:|:---|
|GND|1|2|+5V|
|/flag_x|3|4|SCK|
|/flag_y|5|6|MISO|
|/flag_z|7|8|MOSI|
|step_x|9|10|/cs_x|
|step_y|11|12|/cs_y|
|step_z|13|14|/cs_z|
|GND|15|16|+5V|

##Firmware##
This is difficult as it can vary between architectures (AVR, PIC & ARM) as well as between IDEs (MPLab, Arduino, AVR Studio etc). I shall try to add links & relevent bits of code as this project progresses.

Notes:
* the /cs line must be raised after every byte.
* if you are expecting a response you should send a dummy byte (0x00 or 0xFF).
* the L6470 requires both power supply rails, +12V and +5V to operate.

##Licence##
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/deed.en_US"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">dSMD</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/deed.en_US">Creative Commons Attribution-ShareAlike 3.0 Unported License</a.>
