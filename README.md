# Embedded-Systems-Development-Task
control (I/O) pin using button with arduino 




Embedded Systems Development Task

control (I/O) pin using button with measuring the temperature

 
Introduction :
Writing   arduino function to control one input and output (IO Pins) the input pin is a switch as interrupt once it pressed it should lighting the led connected to output pin.
if the switch pressed must send “pressed” to the serial monitor only one time also send the LED states ”ON” or “OFF” 
components : 
1- arduino nano 
2- push button 
3- led 
4- resistance  220 ohm 
5- LM35dz  “ temperature sensor “ 
6- wires 
Steps : 
First : 
connect pin 2 digital to the the first leg of push button
 connect pin 3 digital to positive leg of led 
connect pin 7 analog to the second leg of temperature sensor 
second : 
connect the first pin of push button with the negative leg  of the led
connect first leg of  resistant with the second leg of push button 
connect second leg of resistant with the ground 
connect first leg of temperature sensor to ground
connect third  leg of temperature sensor to 5v 


process : 
when press the button , the led is on and printed “ press “ on screen 
every 3 seconds , temperature sensor will measure the temperature surround 
conclusion : 
we can control any key with small code and server “introduction to IOT System “ 
this is called “ embedded hardware and software system “
 
 


