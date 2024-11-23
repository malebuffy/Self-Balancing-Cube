# Self-Balancing-Cube

USE ESP32 2.0.17 , not the latest one in Arduino IDE

**UPDATE (2024-11-19)**

PCB and Schematic that can be ordered directly though JLCPCB

https://oshwlab.com/malebuffy/self-balancing-cube
Copy Paste the link. Direct clicking is blocked.

Also added a Serial Command "V" which gives you the battery voltage.

**UPDATE (2024-07-14)**

New code is in **esp32_cube_enc** folder. I changed sensor orientation. So, if you make my cube before, to use this code, you need to reprint one part.

Or you can print redesigned cube https://www.thingiverse.com/thing:6695891

<img src="/pictures/cube2.jpg" alt="Cubli"/>

The red connections you see in the schematic must be connected!

If something doesn't work, try the motors test sketch. It tests all motors, rotation directions and encoders.

Folow this video https://youtu.be/ZU0oTBRDgOE

---

IF YOU HAVE BUILT THE OLD VERSION!!!

ESP32, MPU6050, Nidec 24H brushless motors, 500 mAh LiPo battery.

Balancing controllers can be tuned remotely over bluetooth.

Example:

Send p+ (or p+p+p+p+p+p+p+) for increase K1.

Send p- (or p-p-p-p-p-p-p-) for decrease K1.

The same for K2, K3. Send "i", "s".

<img src="/pictures/cube1.jpg" alt="Self-Balancing-Cube"/>

<img src="/pictures/schematic.png" alt="Self-Balancing-Cube-Schematic"/>

About schematic:

Battery: 3S1P LiPo (11.1V). 
Buzzer: any 5V active buzzer.
Voltage regulator: any 5V regulator (7805).
All red connections not nescesary for this project! But if you are designing a PCB I recommend making these connections. Maybe I use encoders in the future, you will be able to use the new firmware without any changes.
 
How to build:

https://youtu.be/AJQZFHJzwt4

If something doesn't work, try the motors test sketch. It tests all motors, rotation directions and speeds. This helps you understand the problem is in software or in hardware.

You can also make this balancing cube with Arduino nano controller. All other parts remain the same.

<img src="/pictures/arduino_schematic.png" alt="Self-Balancing-Cube-Schematic"/>

In this version I make offsets setting procedure more simple. First connect to controller over bluetooth. 
You will see a message that you need to calibrate the balancing points. Send c+ from serial monitor. This activate calibrating procedure. 
Set the cube to one of balancing points (edge or vertex). Hold still when the cube does not fall to either side. Send c- from serial monitor. 
This will write the offsets to the EEPROM. Repeat this procedure four times (3 edges and vertex). After calibrating all offsets, the cube will begin to balance.

ESP32 version also has an updated balancing point setting procedure. Important! In this video you can learn how to set the balancing points:

https://youtu.be/Nkm9PoihZOI


