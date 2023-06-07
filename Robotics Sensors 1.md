# What Makes a Machine a Robot
- Sensing --> planning --> acting
- Localization
- Obstacle detection
- Sensing for specific tasks
- Face detection and tracking

# Sensors

> [!DEFINE] Sensor
> A device that measures a physical quantity and converts it to an electrical signal which can be read by an instrument

Job --> convert a parameter from one form and report it in another form of energy

Important aspects of a sensor:
- Measurement technique
- Size
- Weight
- Operating temperature range
- Power consumption
- Price range

Data transfer from sensor to CPU:
- CPU-initiated (polling)
- Sensor-initiated (interrupt)

## Sensor Categories
Local --> On board sensors
Global --> Around the environment of the robot and transmit signals back to the robot

Internal --> Monitor internal state of robot
External --> Monitor robot's environment

Passive --> Monitor the environment without disturbing it, digital camera, gyroscope
Active --> Stimulate the environment for measurement, sonar sensor, laser, infrared

### Binary Sensor
Return either 0 or 1
Tactile sensor

# Analog VS Digital Sensors
An A/D converter is required to connect a sensor to a microcontroller

Digital sensors are usually more complex and more accurate

Output of a digital sensor can have different forms:
- Parallel interface
- Serial interface

> [!DEFINE] Synchronous Serial
> Converted data value is read bit by bit from the sensor

TC72 --> Temperature sensor with synchronous serial digital output interface

# Detectors

> [!DEFINE] Detectors
> A device that receives a signal and responds to it in a distinctive manner

A detector contains a sensor and a decision circuit

# Shaft Encoders
Shaft encoders are required as feedback sensor for motor controller

## Incremental Encoder
Measure change in angular position
The most widely used encoders are either magnetic or optical

Standard optical encoders use a sector disk with black and white segments with an LED and a photo-diode which detects the reflected light during a white segment only

16 white + 16 black = 16 pulses

Encoders with only one sensor can count number of elements passing by but can't distinguish whether a motor shaft is moving clockwise or counter-clockwise

For this most encoders are equipped with two sensors and a small phase shift

Pulse Counting registers --> Can count incoming pulses up to a certain frequency, which means the CPU is not slowed down

## Absolute Shaft Encoders
Measure absolute or true angular position

Consists of gray-code disk with a set of sensors

Number of sensors determines the accuracy of the encoder, 3 sensors = resolution 2^3 = 8 sectors

# A/D Converter
Characteristics of an A/D converter:
- Speed --> Max conversion rate
- Accuracy --> Number of bits per value
- Measurement range --> expressed in volts

$$Digital = V_{in}*2^n/V_{REF}$$

May contain multiplexer which allows the connection of several sensors