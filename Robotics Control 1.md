up: [[Robotics]]

# On-Off Control (Piece-wise constant/Bang-Bang)
The simplest possible method of control, not limited to controlling a motor --> Refrigerator, heater... etc
Feedback control:
- We have a desired speed and we have the actual current speed measured by shaft encoders
- Measurements can be taken very frequently
- The action taken depends on the controller model

Power to the motor is either switched on (speed is too low) or switched off (speed is too high)

## On-Off Control with Hysteresis

> [!DEFINE] Hysteresis Band
> Consists of two desired values, one for switching on and one for switching off, which prevents a too high switching frequency to avoid excessive wear

# PID Controller

> [!DEFINE] PID Controller
It comprises a proportional, an integral, and a derivative control part

## Proportional Controller
Abrupt change between a fixed motor value and zero isn't smooth

We can improve this by using linear or proportional term is instead of an abrupt change

Formula for proportional controller: $$K_p(V_des(t)) - V_act(t)$$

The difference between desired and actual speed is called `error function`

The higher the `Kp` the faster the controller responds, too high leads to undesirable oscillating motion

Each proportional controller will keep a certain `steady-state error`

The higher the gain `Kp`, the lower the `steady-state error`

## Integral Controller
Integral controller is rarely used alone, mostly used in combination with proportional or PD controller

The idea is to reduce the `steady-state error` of the P controller

With additional integral term, error can be reduced to zero

Equilibrium is reached somewhat later than with pure P controller and steady-state error has been eliminated

> [!IMPORTANT]
> Limit the controller output to the correct value range, if the desired speed can't be reached both controller output and error values become very large

## Derivative Controller
Similar to I controller, rarely used alone

The idea is for adding a derivative term is to speed up the P controller's response to a change

A PD controller reached equilibrium faster than P but still has `steady-state error`

The full `PID` controller combines the advantages of both PI and PD, fast response and no steady-state error

The tuning of the three PID parameters Kp, Ki and Kd is important

# Velocity and Position Control
Maintaining a certain speed --> Velocity control
Reaching a specific point --> Position control

The position controller sets the desired velocities in all driving phases especially acceleration and deceleration

The control should take the current speed and the position into consideration

# Multiple Motors, Driving Straight
Synchronization of the two motors is required

