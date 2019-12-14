# 2wd

The two-wheeled robot with a low center of gravity.

![A high-quality, professional artist's conceptual rendering of 2wd.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd.png)

I like [MiP](https://github.com/Tiogaplanet/MiP_ESP8266_Library).  There's no denying the mobile inverted pendulum, for which it gets its name, is an innovative design.  Unfortunately the innovation comes at the cost of increased battery consumption.  MiP cannot come to a resting position as long as it is powered on.  In order to remain upright it must constantly rebalance itself to prevent from toppling over.

Other consumer grade robots such as Anki's Vector or Cozmo use a tracked design.  The many four-wheeled Arduino kits for sale around the Internet use skid steering similar to Vector and Cozmo at the cost of decreased agility compared to MiP's differential steering.  I'm looking for a different approach that has the agility of MiP but without the skid steering or complexity of a tracked or four-wheel drive system.

My solution is a robot with two parallel wheels, side by side, a layout known as a dicycle.  Technically, MiP fits this definition however I picture a design with the center of gravity below the horizontal center line of the wheels.  Such a design would conserve battery power when the robot is at rest.

I have found only a couple notable examples of such a design online.  [Parrot's Sumo](https://www.parrot.com/us/minidrones/parrot-jumping-sumo) fits the description but it appears to be dragging a solid tail to counter torque and keep the robot upright.  The best example I've seen of a self-balancing dicycle comes from [Simon Winder](http://simonwinder.com/2015/06/two-wheeled-rolling-robot/).  It uses an inertial measurement unit (IMU) to keep the body upright and it uses infrared to avoid obstacles.

My proposal is to develop a robot similar to Winder's.  It would be built around the ESP8266, include an integrated battery charging circuit and a camera.

The goal is a single motherboard containing all of the circuitry with the exception of magnetic encoders mounted to the base of each wheel motor.  I predict the bill of materials for prototyping will look like this:

| Description | Quantity |
|-------------|----------|
| [Arduino 33 IoT](https://store.arduino.cc/usa/nano-33-iot) | 1 |
| [90x10mm wheels](https://www.pololu.com/product/1435) | 2 |
| [Gear motors](https://www.pololu.com/product/1520) | 2 |
| [Gear motor brackets](https://www.pololu.com/product/2681) | 1 |
| [Magnetic encoder pair](https://www.pololu.com/product/1523) | 1 |
| [Motor driver](https://www.pololu.com/product/2135) | 1 |
| [IR sensors](https://www.pololu.com/product/2464) | 2 |
| 18650 batteries | 2 |
| Battery management system | 1 |
| Perforated board | 1 |

## 13 December 2019

The last several weeks I have tried organizing a place to work in my latest home.  Tonight I was finally able to assemble a few things.

![A view of the top side of 2wd. Motors and batteries are assembled on opposite sides of the center line to balance weight.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd_build02.jpg)

![A view of the front of 2wd.  The batteries are mounted near the front and rear edge of the main prototyping board.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd_build01.jpg)

I have breadboard-tested the motor driver and an OLED display.  Next, I plan to sort out the charging system and install it on 2wd.
