# 2wd

The two-wheeled robot with a low center of gravity.

![A high-quality, professional artist's conceptual rendering of 2wd.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd.png)

**This repository contains the Eagle files for 2wd and a running log of its development.**

I like [MiP](https://github.com/Tiogaplanet/MiP_ESP8266_Library).  There's no denying the mobile inverted pendulum, for which it gets its name, is an innovative design.  Unfortunately the innovation comes at the cost of increased battery consumption.  MiP cannot come to a resting position as long as it is powered on.  In order to remain upright it must constantly rebalance itself to prevent from toppling over.

Other consumer grade robots such as Anki's [Vector](https://anki.com/en-us/vector.html) or [Cozmo](https://anki.com/en-us/cozmo.html) use a tracked design.  The many four-wheeled Arduino kits for sale around the Internet use skid steering similar to Vector and Cozmo at the cost of decreased agility compared to MiP's differential steering.  I'm looking for a different approach that has the agility of MiP but without the skid steering or complexity of a tracked or four-wheel drive system.

My solution is a robot with two parallel wheels, side by side, a layout known as a dicycle.  Technically, MiP fits this definition however I picture a design with the center of gravity below the horizontal center line of the wheels.  Such a design would conserve battery power when the robot is at rest.

I have found only a couple notable examples of such a design online.  [Parrot's Sumo](https://www.parrot.com/us/minidrones/parrot-jumping-sumo) fits the description but it appears to be dragging a solid tail to counter torque and keep the robot upright.  The best example I've seen of a self-balancing dicycle comes from [Simon Winder](http://simonwinder.com/2015/06/two-wheeled-rolling-robot/).  Winder's robot uses an inertial measurement unit (IMU) to keep the body upright and it uses infrared to avoid obstacles.

I propose developing a robot similar to Winder's, built around the Arduino Nano 33 IoT, which has an integrated six-degree IMU along with WiFi and Bluetooth.  The robot will also include an on-board battery management system, IR detection, an OLED display and eventually a camera.

I'll update the bill of materials for prototyping as I develop the robot.  For now it looks like this:

| Description | Quantity |
|-------------|----------|
| [Arduino Nano 33 IoT](https://store.arduino.cc/usa/nano-33-iot) | 1 |
| 15 pin female headers for Nano | 2 |
| [90x10mm wheels](https://www.pololu.com/product/1435) | 2 |
| [Gear motors](https://www.pololu.com/product/1520) | 2 |
| [Gear motor bracket pair](https://www.pololu.com/product/2681) | 1 |
| [Magnetic encoder pair](https://www.pololu.com/product/1523) | 1 |
| [Motor driver](https://www.pololu.com/product/2135) | 1 |
| 7 pin female headers for driver | 2 |
| [IR sensors](https://www.pololu.com/product/2476) | 2 |
| [Battery management system (BMS)](https://www.amazon.com/gp/product/B07S7PKPH6/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1) | 1 |
| [Prototype board (7x9 cm) for motherboard and drive/power board](https://www.amazon.com/gp/product/B072Z7Y19F/ref=ppx_yo_dt_b_asin_title_o04_s01?ie=UTF8&psc=1) | 2 |
| 18650 batteries | 2 |
| [Voltage regulator](https://www.amazon.com/gp/product/B00IJYDJTS/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | 1 |
| 15mm PCB stand-offs, nuts and screws for regulator | 2 |
| [DC barrel jack](https://www.amazon.com/gp/product/B074LK7G86/ref=ppx_yo_dt_b_asin_title_o04_s00?ie=UTF8&psc=1) | 1 |
| [SPDT switch](https://www.ebay.com/itm/12-Breadboard-slide-switches-3-pin-50-volt-500-milliamp-SPDT-switch-Arduino/112891316956) | 1 |
| 26mm PCB stand-offs, nuts and screws for motherboard and drive/power board | 4 |
| [OLED display](https://www.amazon.com/gp/product/B072Q2X2LL/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | 1 |
| PCB stand-offs, nuts and screws for OLED display | 4 |

## 19 December 2019

No new work.  Just sharing some of my latest pictures.  Below is a picture of 2wd doing some bench testing.  It's sitting on the box for the Nano 33 IoT while I test code for operating the motors.  I'm using the Arduino Uno clone behind the breadboard to power the motors.  The motors still need more current than what the Uno clone provides.  However, I have received some 2.1mm DC barrel jacks in the mail so I will be able to connect a wall-wart power supply to the motors via the LM2596 module.

![2wd is bench tested. Here it is sitting on the box for the Nano 33 IoT so that the motors can spin freely while undergoing test.](https://github.com/Tiogaplanet/2wd/raw/master/images/benchtest01.JPG)

I soldered a few right-angle pins onto the BMS to make it fit onto the prototyping board that makes up 2wd's chassis.  I didn't use a lot of solder in case I needed to undo it.  Once everything tests out I'll do come back and re-solder the right-angle pins.

![A view of the underside of the battery management system shwoing right angle pins to make the BMS prototyping- and breadboard-friendly.](https://github.com/Tiogaplanet/2wd/raw/master/images/bms01.JPG)

![A view of the top of the battery management system.](https://github.com/Tiogaplanet/2wd/raw/master/images/bms02.JPG)

The LM2596 module doesn't plug into a prototyping board either but it has screw holes so I plan to drill holes in the prototyping board and mount the module using PCB stand-offs.

## 13 December 2019

The last several weeks I have tried organizing a place to work in my latest home.  Today I was finally able to assemble a few things.

![A view of the top side of 2wd. Motors and batteries are assembled on opposite sides of the center line to balance weight.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd_build02.jpg)

![A view of the front of 2wd.  The batteries are mounted near the front and rear edge of the main prototyping board.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd_build01.jpg)

Not shown in the pictures above is a "motherboard" mounted above the gear motors using PCB stand-offs in the pre-drilled holes of the prototyping board.  I realized quickly that I did not have enough space to mount the Nano, OLED display and pretty much anything else after securing the gear motors and batteries to the drive/power board.  While this will make the body of the robot taller, it will still be within the diameter of the wheels and won't come close to offsetting the weight of the batteries.  It should also reduce body flex between the two wheels.

I have breadboard-tested the motor driver using pulse-width modulation in a simple sketch.  The wheels turn forward together at a medium speed before momentarily stopping, then turning backward.  In the same sketch I also tested the use of an OLED display.  So far, so good.  Although, I still need to develop an [actual library](https://github.com/Tiogaplanet/2wd_library) to drive the robot.

Next, I plan to sort out the power and charging system.  I have soldered right-angle pins to the BMS to make it "breadboard friendly."  It will sit close to the prototype board so for now I plan to install it underneath the robot, between the batteries with the voltage regulator stacked below it using PCB stand-offs. Now I'm just waiting for the barrel jack and power switch to arrive in the mail before I assemble anything else.
