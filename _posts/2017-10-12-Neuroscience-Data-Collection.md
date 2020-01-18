---
layout: post
title:  "Automated Movement Data Collection with Magnets"
categories: [research]
tags: [brain sciences, embedded systems]
comments: true
---
Meant to collect limb data from small magnets attached to mice that are placed above four QMC5883L magnetometers. The Arduino also features a TCA9548A I2C multiplexer to manage the four identical magnetometers. This also communicates with the Tucker Davis Technologies RZ2 to display when the data collection is active.

<!--more-->
I constructed a automated data collection tool for the Blumberg Lab of Psychological and Brain Sciences to remove the need for manual limb position tracking. The code, as well as a system diagram, can be viewed at the Github repository [here](https://github.com/zainakh/magnetometer-data).

A general overview of the project is as follows: 
* The Arduino collects magnetometer data and prints all axis data to the serial monitor
* A Python file acts as a master and coordinates the start of data collection and the end of data collection
* At the end of data collection, the Python file will save the data to a file using the PySerial library to interact with the Arduino Serial port

The most challenging part of this project was using the Wire.h Arduino library to collect data from four magnetometers at once. I initially thought it was impossible without four Arduinos as each of the magnetometers had identical addresses that the Arduino would somehow need to distinguish between. With a little searching around, an I2C mutliplexer allowed me to use all four and was capable of addressing them all with one Arduino. The next issue that stemmed from this was the initialization of each, but throwing a for loop that initialized all of the magnetometers where there was only one magnetometer did the trick (at the time I had no idea how to initialize them all at once, but I was overcomplicating the problem). 

This project was my first solo project as part of the lab and had me explore responsibility for what I was making without routine supervision. There were certainly times when I could have improved my efficiency (learning wire stripping tricks and soldering techniques constituted most of these troubles, actually). I can happily say that with time, I felt that considerably improved in my ability to do things quickly wihout that feeling of wasting time. 

A schematic for the circuit and its communication with other systems is pictured below: 
<div class="post-image-feature">
  <img class="feature-image" src="{{ site.url }}/img/circuit_schematic.png" alt="Circuit Schematic">
</div><!-- /.image-wrap -->
