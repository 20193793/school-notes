up: [[Robotics]]

# DC Motor Speed Control
Ways to control the power delivered to motor:
- Using resistor as voltage divider 
- Pulse Width Modulation (PWM)

## Method 1: Using Resistor
Resistor used to reduce the voltage/current delivered to the motor

This method is not practical:
- Resistor will consume large power and decrease efficiency
- High power resistor is big and need large space

## Method 2: Using PWM
Can be used to control speed, brightness and power

Based on repeated power on/off with high frequency and varying the ratio between POWER ON/POWER OFF

Average power delivered is also varied proportionally

> [!DEFINE] Duty Cycle (Pulse-width ratio)
> Ratio between Ton/Tperiod

Relation between duty cycle and motor speed is not linear

# Actuator Control
Robots are classified into servo and non-servo robots

Non-servo --> Open-loop devices whose movement are limited to predetermined mechanical stops

Servo --> Closed-loop control

## Open Loop Controller

> [!DEFINE] Open Loop Controller (Non-feedback controller)
> Type of controller which computes its input using only the current state and its model of the system

Doesn't observe the output

## Closed Loop Controller
Uses feedback to control states or outputs of a dynamic system

Results are used as inputs to the process

# Servo Motor

> [!DEFINE] Servo Motor
> A mechanism based on feedback control (closed loop), used to control speed and position

Two types:
- Standard servo motor, from 0 to 180
- Continuous servo motor, from 0 to 360

Combines motor and simple feedback for position control

Applies PWM signal which determines the servo position

Have three wires

# Stepper Motor
A motor that moves in steps
Can perform position or speed control
Open-loop