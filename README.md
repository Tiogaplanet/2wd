# 2wd

The two-wheeled robot with a low center of gravity.

![A high-quality, professional artist's conceptual rendering of 2wd.](https://github.com/Tiogaplanet/2wd/raw/master/images/2wd.png)

I'm just thinking out loud here and trying to organize my thoughts.  I haven't actually done anything yet.  

I like MiP.  There's no denying the mobile inverted pendulum, for which it gets its name, is an innovative design.  Unfortunately the innovation comes at the cost of increased battery consumption.  MiP cannot come to a resting position as long as it is powered on.  In order to remain upright it must constantly rebalance itself to prevent from toppling over.

Other consumer grade robots such as Anki's Vector or Cozmo use a tracked design.  The many four-wheeled Arduino kits for sale around the Internet use skid steering similar to Vector and Cozmo at the cost of decreased agility compared to MiP's differential steering.  I'm looking for a different approach that has the agility of MiP but without the skid steering or complexity of a tracked or four-wheel drive system.

My solution is a robot with two parallel wheels, side by side, a layout known as a dicycle.  Technically, MiP fits this definition however I picture a design with the center of gravity below the horizontal center line of the wheels.  Such a design would conserve battery power when the robot is at rest.

I have found only a couple notable examples of such a design online.  [Parrot's Sumo](https://www.parrot.com/us/minidrones/parrot-jumping-sumo) fits the description but it appears to be dragging a solid tail to counter torque and keep the robot upright.  The best example I've seen of a self-balancing dicycle comes from [Simon Winder](http://simonwinder.com/2015/06/two-wheeled-rolling-robot/).  It uses an inertial measurement unit (IMU) to keep the body upright and it uses infrared to avoid obstacles.

My proposal is to develop a robot similar to Winder's.  It would be built around the ESP8266, include an integrated battery charging circuit and a camera.

The goal is a single motherboard containing all of the circuitry with the exception of magnetic encoders mounted to the base of each wheel motor.  I predict the bill of materials for prototyping will look like this:

| Description | Quantity |
|-------------|----------|
| [Wemos D1 mini Pro](https://wiki.wemos.cc/products:d1:d1_mini_pro) | 1 |
| [90x10mm wheels](https://www.pololu.com/product/1435) | 2 |
| [Gear motors](https://www.pololu.com/product/1520) | 2 |
| [Gear motor brackets](https://www.pololu.com/product/2680) | 2 |
| [Magnetic encoder pair](https://www.pololu.com/product/1523) | 1 |
| [Motor driver](https://www.pololu.com/product/2135) | 1 |
| [IMU](https://www.pololu.com/product/2739) | 1 |
| [IR sensors](https://www.pololu.com/product/2464) | 2 |
| 18650 batteries | 4 |
| Battery box | 4 |
| TP4056 charging module | 4 |
| Perforated board | 1 |
