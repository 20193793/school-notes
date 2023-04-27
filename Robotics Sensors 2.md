up: [[Robotics]]

# Position Sensitive Device

> [!DEFINE] Distance Measurements
> Measure distances to the nearest obstacle around the robot for navigation purposes

In the past most robots where equipped with sonar sensors

A typical configuration requires 24 sensors because of the relatively narrow cone of these sensors (about 15 degrees each)

## Sonar Sensors Principles
- A short acoustic signal of 1ms at an ultrasonic frequency of 50kHz to 250kHz is emitted and time = emission signal transmission till the echo returns to the sensor
- Time-of-flight proportional to 2 * distance of the nearest obstacle in the sensor cone
- No signal is received, then there is no obstacle detected
- Measurements are repeated about 20 times per second which gives the sensor its clicking sound

# Sonar Sensor
Most significant problem of sonar sensor is it's 
- Narrow range
- Reflections 
- Interference

Reflections causes obstacles to appear further than they actually are

Interference occurs when several sensors operate at once, coded sonar is used to solve this problem

# Infrared Sensors
Sonars have been replaced by infrared or laser sensors

The current standard is laser sensors that return a perfect 2D or 3D distance map 

These sensors are still too large, heavy and expensive for small robots

IR sensors don't follow the same principles as sonar because the time-to-flight might be too short to measure, instead these systems use a pulsed infrared LED at about 40kHz with a detection array

Angle changes accoding to the distance to the object

Wavelength = 880nm and can be transformed to visible light by IR detector card or IR-sensitive camera

## IR Sensor Interface to Arduino
Two variations:
- Sharp GP2D12 --> analog output, returns voltage level in relation to the distance
- Sharp GP2D02 --> Digital serial output, has a digital serial interface

The relation between digital sensor read-out and actual distance information is non-linear

## IR Proximity Sensor
IR proximity switches are of a much simpler nature than IR PSDs, are the electronic equivalent of the tactile binary sensors

These sensors only return 0 or 1, free space or not

IR Proximity sensors can be used instead of tactile sensors for most applications that involve obstacles with reflective surfaces

No moving parts are involved

# Compass Sensor
Used in self-localization

An autonomous robot has to rely on sensors to keep track of its current position and orientation

Standard method is using shaft encoders on each wheel then apply dead reckoning

> [!DEFINE] Dead Reckoning
> Starts with a known initial position and orientation, then adds all driving and turning actions to find the robots position and orientation

Dead reckoning error will grow by time because of wheel spillage and other factors

A further step is to use receiver module for satellite-based GPS, which only works outdoors

Simplest modules are analog that can distinguish only 8 directions represented by voltage levels

Digital compasses are more complex and provide a much higher directional resolution

# Gyroscope, Accelerometer
Orientation sensors are required by tracked robots, balancing robots, walking robots and autonomous robots

Inertial sensors/trackers:
- Accelerometer --> a in x-y-z
- Gyroscope --> ω velocity around x-y-z

Modern inertial trackers use solid-state structures that use micro-electro-mechanical systems (MEMS) Technology

Three gyroscopes measure yaw, pitch and roll angular velocities

The orientation angle are determined through integration over time
Digitally integration is done through summing

Three accelerometers with three gyroscopes are needed to measure body referenced accelerations

Accelerations in world coordinates = Tracked object orientation - gravitaional acceleration
Tracked object position = double integration over time

# MPU6050

> [!DEFINE] MPU6050
> A sensor module that is a complete 6-axis Motion Tracking Device that combines 3-axis gyroscope, 3-axis Accelerometer and Digital Motion Processor in a small package

It also has on-chip Temperature sensor, I2C bus interface to communicate with microcontrollers, Auxillary I2C bus to communicate with other sensors

Has 3-axis Magnetometer --> 9-axis Motion Fusion Output

# Inclinometer (Tilt Sensor)
> [!DEFINE] Inclinometer
> Measure the absolute orientation angle within a specified range depending on the sensor model

The sensor is either analog or PWM

They are better in measuring orientation than a gyroscope because they measure absolute angle about an axis and not the derivative 

However they suffer:
- Time lag
- Oscillation when subjected to positional noise (servo jitter)

Systems that require immediate response like balancing robots, gyroscopes have an advantage

The ideal solution is a combination

# Digital Camera
Most complex sensors in robotics

Not implemented until recently due to the processor speed and memory capacity required

In mobile robots, high frame rate is important and not concerned with resolution

## Camera Interface
The camera clock is linked to a CPU interrupt, while the parallel data output is connected to the data bus

Every image causes an interrupt at the CPU which will enable the camera output and read one image data byte

Every interrupt causes considerable overhead

A buffer is a better solution to interrupt the CPU much less frequently

The advantage of FIFO that is supports asynchronous read and write in parallel