## Signal visualization

[Video url](https://imgur.com/a/AgrIYKC)


The video demonstrates an oscilliscopes reading of various waveforms, generated by a function generator.

## [set_pulse.js](https://github.com/Introduction-to-Computer-Engineering/final-project-assignment-8-week-13-O11WL1D/blob/master/set_pulse.js)

[Video url](https://imgur.com/a/Id4Lk6G)

-We forgot to record a video for this one, but it would essentially look the same as the varying duty cycle program, but with only one setting.   


Description:

A simple javascript program which emits square pulses with a 20 millisecond period, and with a wave length of 1.5 milliseconds. 

## [varying_duty_cycle.js](https://github.com/Introduction-to-Computer-Engineering/final-project-assignment-8-week-13-O11WL1D/blob/master/varying_duty_cycle.js)

[Video url](https://imgur.com/a/Id4Lk6G)

Description:

A program which allows you to change the wave length of a square wave which has a 20 millisecond period. Pressing the A button will result in a %5 increase in the signals duty cycle, and Pressing the B button will result in a 5% decrease in the duty cycle.  


## Exploring the servo.write function

[Demo video](https://imgur.com/a/OUNa16G)

[Code used](https://github.com/Introduction-to-Computer-Engineering/final-project-assignment-8-week-13-O11WL1D/blob/master/servo.js)

Description: 
Various tests exploring the servo.write function, which determined that only values passed to the function in the range of 0-180 were capable of changing the pulse width. Moreover, it was found that for each 45 degree increment to the passed value, the pulse width increases by 1.5 milliseconds.   

## i2c vs uart/spi

--DRAWBACKS

The primary disadvantages of the uart protocol is that all connected devices must be properly calibrated with the same baud rate for it to work, and that overall it is slower due to featuring a start and stop bit per packet. Not to mention, the uart protocol can usually only support communication between two devices, otherwise the risk of bus contention is presented. 

The spi protocol's main disadvantage is that it each slave device requires 4 connections to the master device, which may get complicated in the case of multiple slave devices.  

THe i2c protocol differs in the fact that each slave device is automatically synchronized with the master's clock signal, sent packets are faster due to not having a stop/start bit and that multiple devices can be connected, without bus contention.

## SDA
Line which sends actual data//data destination, ack bit, r/w bit
## Scl
line which features the master devices clock signal.

## Master vs slave devices
The main difference between master and slave devices is that master devices generate the clock signal for all connected slave devices and that slave devices can delay the reading/writing of said clock signal.


## Difference between protocol frames
Uart frames or packets feature a start and stop bit, one byte of transmitted data,and sometimes a parity bit for error checking.
I2c frames on the otherhand feature slave addressing data, A read/write bit and An ack bit, along with a standard transmitted byte 

## Trigger mode
Due to the each packet being signaled by a high to low transistion, falling edge triggering is the best option for visualizing i2c packets.


## (advanced question) : 
given that you had 2 microbits, both configured as the master device, and you connected both of their SDA and Scl lines together, how would they communicate?

because multiple slave devices can be connected to a masters sda and scl lines, the slave devices/peripherals of both microbits would become accessable by both of the master microbits. Also, the two master devices would not be able to communicate with each other so if one wanted to transfer data between the two masters it would need to be through some intermediary peripheral device or register.


## [I2c write number](https://github.com/Introduction-to-Computer-Engineering/final-project-assignment-8-week-13-O11WL1D/blob/master/write_number.js)

Description:
Writes a number using the i2c communication protocol to a random slave device address.

A) : We captured a some of the address frame, and some of the sent data 

B) : when nothing is connected, the i2c write function transmits the signal as usual. In some systems a high ack bit indicates that a slave device did not recieve a signal or doesn't know how to parse data, and that a retransmission should occur. In our testing, a retransmission was not observed, dispite not having a slave device to recieve the data.

c) : The only difference between the three addresses captured patterns is the slave address near the start of the capture. 

## [I2c_different_address_practice](https://github.com/Introduction-to-Computer-Engineering/final-project-assignment-8-week-13-O11WL1D/blob/master/i2c_practice.js)

<-------Results are indicated in the programs comments --->

