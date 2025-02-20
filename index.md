# Autonomous RC Car 
## Bates Raspberry Pi Short Term Class 2017


### May 3 2017
This is the first day we have really begun to work on the project. The goal for today was to take apart the RC car we bought and begin to understand how it works. Because some of our parts were still in the mail we spent a good portion of the day reading tutorials and working with OpenCV. By the end of the session our Pi's camerea could recognize faces using OpenCv.
- Tutorial we used for OpenCv [Link](https://pythonprogramming.net/loading-images-python-opencv-tutorial/)


### May 8 2017
Since our last update we have ordered all the parts and successfully taken apart the car. We have taken apart the car so we can control both the motor that turns the front wheels, and the motor that controls forward and reverse.

Our Raspberry Pi
![Image1](/Images/IMG_3613.jpg?raw=true)

Our car taken apart...
![Image1](/Images/IMG_3620.jpg?raw=true)
Our next goal is to setup our Raspberry Pi to the Bates network. Once that is done we are following this tutotial to control our car using a blue tooth keyboard.

- Tutorial we are using for the seting up the car - [Link](http://www.instructables.com/id/Controlling-a-Raspberry-Pi-RC-Car-With-a-Keyboard/)
- Other Tutorial we are using for setting up the car - [Link](http://www.instructables.com/id/Raspberry-Pi-2-WiFi-RC-Car/)
- Tutorial with helpful diagrams - [Link](http://forums.parallax.com/discussion/156410/how-to-use-a-l298n-dual-h-bridge-with-a-microcontroller-quickstart-board)

Once we took apart the car we started to hookup the L298D chip to the motors and batteries from the car. This allowed us to control the motors with our keyboard

L298D Chip ~ $9
Good tutorial for understanding the Chip and a helpful diagram from [instructables.com](http://www.instructables.com/id/Arduino-Modules-L298N-Dual-H-Bridge-Motor-Controll/)

![Image1](/Images/L298D.jpg?raw=true)


Notes: We are being extremely careful to label and track all the screws we are using. Each RC car is different...to do this project we need to be careful with the car and its parts since there is no clear way to take it apart and put it back together. When playing with the batteries becareful with the livewires...if the batter isn't disconnected this could cause a spark'

### May 9, 2017

Today we had a breakthrough. We finally configured all the motors, pi and L298D chip. 


Once this was done we set up a python file to run each motor for a set period of time. Using this file we can get the car to run the motors using the pi.

- Tutorial we used for code [link](http://deepaksinghviblog.blogspot.com/2014/08/raspberrypi-to-run-dc-motor-using-l298n.html)
- This tutorial was helpful with the coding but we had to add extra lines for the second motor

The next step is to rebuild the car and set up the sensor.  


A video of the keyboard turn on each motor in each direction...we can now rebuild the car and control it with python programs 

[Video of Our Car Motors](https://www.youtube.com/watch?v=OJA07F00AuQ&feature=youtu.be)

### May 10, 2017
We rebuilt the car...this took a lot of troubleshooting and time, therefore we were limited by what we could accomplish today. The car is now ready to drive using our python script. We corrupted our first SD card so...we will need to buy a new one.


Everything hooked up before we rebuild the car

![Image1](/Images/pictures/IMG_8849.jpg?raw=true)

This is out GPIO MAP

GPIO pins:

2 red
4
6 gray
8
10
12
14
16
1
3
5
7 purple
9
11 blue
13 green
15 yellow

### May 11, 2017

We attached our first sensor to the car. This proved to be extremely challenging because we had to use the breadboard, wires, and resistors. This was new territory for me...Reed, Priyanka and Matt really took charge with this portion of the project.

This is our breadboard with everything attached 
![Image1](/Images/IMG_3652.jpg?raw=true)

A close up of our Pi with the wires attached 
![Image1](/Images/Pictures/IMG_8866.jpg?raw=true)

We are using an HC-SR04 sensor...we are using two main tutorials to hook up the sensor
- The first is [Link] (https://www.modmypi.com/blog/hc-sr04-ultrasonic-range-sensor-on-the-raspberry-pi)
- The second is [Link] (https://www.raspberrypi.org/learning/physical-computing-with-python/distance/)

### May 12, 2017 
                
We got the sensor working today using the code in following link. We disconnected the pi from the L298D chip, so that the sensor was the only thing connected to the pi. Once we got the sensor working, we connected the chip back to the pi and made sure that the sensor and motors were working. 
                
[Link](http://www.knight-of-pi.org/ultrasonic-range-detection-with-the-raspberry-pi/)

We are now working on combining both our functions to run them through one script. 

### May 15, 2017


Sensor now works while motor is running. However, we encountered some bugs when stopping the program (the wheel was still turning after the program was killed).

In our picar.py file we controlled the car as such.  If object detected using HC-Sr04 sensor within 10cm, the car will reverse.  If object detected within 10-20cm, the car will turn right.  If object detected at a greater than 20cm distance, continue straight.  This worked as anticipated, however we were unable to break out of the while loop.  

To fix this, matt implemented a function which starts/stops the program from running using the keyboard.  We will finalize the object detection tomorrow.  

### May 16 and 17, 2017
May 16th was tough because some of our wires started to melt. We spent most of the day rewiring and trouble shooting

May 17 was a much more successful day. We used the code file test1.py to get the car to run. Using the sensor which is now much more accurate and our newly re-wired motors we were able to get the car to move forward on its on and stop if it detected something infront of the car within 50cm it stops.



### May 18 and May 19

We started re-installing OpenCV. We have had Pi issues and SD card issues. Even though we had worked with Open CV before we had to reinstall it. Installing it took most of the day...we spent time desinging the car so everything is more secure 


## Conclusion 

In conclusion we had trouble getting openCV to work. Our car was able to use the sensor to stop if it sensed an object in front of it. This project still has a lot of fine tuning that needs to be done. Our group page has more documentation on how to do this your self, the prices of all the object and more photos and videos.

Here is a final video of our car stoping in front of a trash can

[A small clip of our car driving semi-autonomously](https://youtu.be/F5Y3YCBHOJU)



