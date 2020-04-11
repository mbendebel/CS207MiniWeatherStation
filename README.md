# Arduino-Based Mini Weather Station [v1]

This repository is intended for the CS207 - Winter 2020 Final Project.
This repository will display how to make your own Arduino-Based Mini Weather Station. The mini weather station will read data from two main sensors (a raindrops sensor and a BME280 sensor) and output the data neatly to an LCD screen.

Enjoy!


Repository Contents
============
* **/build** - Files that are compiled and ready to run / upload.
* **/img** - This is where the image files for this readme are.
* **/README.md** - File explaining what thsi project is.


Requirements and Materials
============
Bill of Materials:
* 1 x Arduino Uno R3
* 1 x breadboard
* 1 x BME-280 Pressure Sensor (Reads air temperature, humidity, atmospheric pressure, and altitude)
* 1 x 1.8" ST7735 LCD Display
* 1 x Enclosure
* 1 x Rain Sensor Kit


Build Instructions
==================

To start off with the project, we used two breadboards instead of one because we need a
decent amount of breadboard real-estate since the components for this project are fairly sizeable.
From here, we plot the 1.8” TFT ST7735 LCD display, the BME280 sensor, the raindrops
module and raindrops sensor , and one push-button on the breadboard. We connect these
components from the breadboard to the Arduino Uno R3 by using jumper wires. In total, there
were 22 connections being powered by the Arduino and because of the numerous amounts of
connections, it made quite a mess on the breadboard especially if without any proper cable
management.
For the rain sensor of this project there are two components, the raindrops sensor itself
and the raindrops module board. The raindrops module board has 4 pins, AO (analog output) pin,
DO (digital output) pin, GND (ground) pin, and VCC+ (5v power) pin. We will only use 3 pins,
these are VCC+, GND, and the AO pin which is connected to analog pin A3. There are two pins
from the raindrops module board which we will connect to the raindrops sensor. The raindrop
sensor’s board surface is coated with numerous lines of nickel. This sensor works on the
principle of resistance. The sensor has more resistance when it is dry, and less resistance when it
is wet. The Arduino can know if it is raining or not based on the amount of resistance being
detected by the raindrops module board. [1]
For the other weather sensor, we use the BME280 sensor. The BME280 can read air
temperature, air pressure, and air humidity. The BME280 has 4 pins which are the SDA (Serial
Data) pin, SCL (Serial Clock) pin, GND (ground) pin, and VIN/VCC+ (5v power) pin. The
sensor has to be soldered onto the seller’s provided pin male header otherwise there will not be a
decent soldered connection made and therefore the Arduino cannot read from the sensor. Added,
the sensor should not be touching the breadboard otherwise the readings from the sensor will not
be accurate.
We added a reset push-button to our weather station. Its purpose is so that we do not have
to rely on the Arduino Uno’s built-in reset button on the board. This makes it convenient for
resetting the weather station when there is an error or if we want an update on the imminent
weather forecast.
As for the sketch code, we had to add many libraries and were required to use different
library functions so that we could communicate with both the board and the sensor. Added, we
also had to tweak the forecast algorithm we used, the Zambretti Forecaster, to fit with our code.
As a result, we had to write numerous amounts of code, especially when writing code to print to
the LCD screen. Furthermore, the use of numerous libraries made our code use up a lot of
memory.



This is breadboard diagram of the build.

![alt text][pic1]

[pic1]: https://github.com/mbendebel/CS207MiniWeatherStation/blob/master/img/Breadboard_bb.png

This is a circuit schematic of the build.

![alt text][pic2]

[pic2]: https://github.com/mbendebel/CS207MiniWeatherStation/blob/master/img/Circuit_schem.png

This is the final product of the build.

![alt text][pic3]

[pic3]: https://github.com/mbendebel/CS207MiniWeatherStation/blob/master/img/Final%20Build.jpeg



Team
=====
The build team consists of: 
* Matthew Dylan Bendebel 
* Su Wai Tin


Credits
=======
* Fritzing software for breadboard and circuit making
* https://create.arduino.cc/projecthub/dnbakshi07/mini-weather-station-using-arduino-nano-b211fe?fbclid=IwAR2AyprrQPpumjUkTDI2wFdadUCjiJbLzPdgpT8ni-vu8mcJgtulg2zDT6Q
* https://circuitdigest.com/microcontroller-projects/rain-detector-using-arduino
* https://earthscience.stackexchange.com/questions/16366/weather-forecast-based-on-pressure-temperature-and-humidity-only-for-implement
