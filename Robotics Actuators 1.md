up: [[Robotics]]

> [!DEFINE] Actuators
> Used in order to produce mechanical movement in robots

Types:
- Electrical
- Hydraulic
- Pneumatic
- Others

# Types of Actuators 
## Electric motors:
- Most Common
- Converts electrical energy into mechanical energy

Electrical actuator types:
- DC-motors
- AC-motors
- Stepper motors
- Servos

Electric motors are the most common source of torque for mobility and/or manipulation robots

When an electric current is passed through a conductor placed within a magnetic field, a force is exerted on the wire causing it to move

### Electric DC Motors
Components:
- North and south magnetic poles
	- Provide a strong magnetic field
	- Made up of  bulky ferrous material
	- Outer casing is called stator
- An armature (Rotor), a cylindrical ferrous core rotating within the stator and carries large number of windings made of one or more conductors
- Commutator, which rotates with the armature and consists of copper contacts attached to the end of the windings
- Brushes, in fixed position and in contact with rotating commutator, carry direct current to the coils

### How DC Motor Works
- Has rotating armature in the form of electromagnet
- Rotary switch called commutator reverses the direction of the electric current twice every cycle, to flow the armature and the poles push and pull
- The commutator reverses polarity of the armature electromagnet
- Inertia keeps the motor going in the proper direction

### Geared DC-Motors
The speed of DC motor ranges from 1000 to 5000 rpm, this speed is very high to be used in mobile robots

Reduce this speed by:
- Using gearbox, gears are used to reduce/increase the speed depending on gear ratio
- Reducing Deriving power (voltage/current), if motor shaft is coupled to the smaller gear speed is reduced, else if coupled to the bigger gear speed increases (N1/N2)

To produce high reduction, multiple gears are used, called gearbox, Torque/Force is increased if speed is reduced by gearbox

### Encapsulated DC-Motors

> [!DEFINE] Encapsulated DC-Motors
> A single package that includes dc-motor, gearbox, and shaft encoder

### Advantages of DC-motors
- Cheap
- Simple
- Easy to control

## Pneumatic and hydraulic:
- Used in industry for large manipulation tasks but not for mobile robots
- Use compressed air/oil to produce motion
- Used for lower cost and lower precision applications

## H-Bridge

> [!DEFINE] H-Bridge
> An electronic circuit that allows a motor to be driven in both directions

Consists of 4-electronic switches in a bridge configuration

### L293D Two Full H-Bridge & L293D Four Half H-Bridge

> [!DEFINE] L293D
> An integrated circuit for DC Motor Drive

Used with microcontroller to run DC motor forward and backward, clockwise, anti-clockwise

It needs 3 singles from microcontroller to control one to enable it and two others for inputs