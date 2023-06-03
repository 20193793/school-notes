up: [[Robotics]]

# Mobile Robots

> [!DEFINE] Mobile Robots
> An automatic machine that is capable of movements in any given environment

Activities of mobile robots:
- Moving around --> Moving forward, reverse and turn left and right, variable speed is less important
- Detecting and responding to light --> Maybe confused by room lighting or sunlight so use pulsed light sources
- Proximity --> Another use for light, tell robot when it's near something but not touching it and can be used to measure distances
- Contact
- Communication
- Navigation

## How Light Sensors Detect a Nearby Object
1. Detect the light reflected from the object
2. If the intensity of the reflected light exceeds a certain limit, robot knows that something is there
3. A light detector aimed sideways can be used to keep a robot at a fixed distance from a wall

## How a Robot Can Contact With an Obstacle
1. A robot has bumpers or wiry "antennae" arranged in a way that they're touched when the robot runs into anything
2. The usual response is to reverse a short distance, turn left or right then move forward to try again
3. If a robot has a pair of bumpers, it's possible to work out which is the best direction to turn

## Navigation of Mobile Robots
- Wall following --> Used by maze solvers
- Line following --> Special form of contact behavior, the robot stays in contact with a lined painted on the surface its moving on
- Homing to light source

# Gantry Robots
- Operates over a clearly defined rectangular area
- The tool is suspended from a small trolley-like frame
- The frame has wheels and runs on a pair of rails
- Can be programmed
- Gantry robots can never lose its bearings because the frame is precisely positioned by keeping track of the x and y coordinates

# Feedback
- When a robot veers toward a wall, the amount of reflected IR increases
- The sensor detects this increase
- The program responds to this by steering the robot to the right and veer away from the wall

Three types of feedback:
- Negative Feedback
- Positive Feedback
- Based on limit switches

## Negative Feedback
- Keeps things constant and provides stability

## Positive Feedback
- Results in instablity

# Subsumption
Follow light an avoid any obstacles between you and light till you see the light by entering a phase of avoidance behavior

# Distributed Processing
- Programming simultaneous activities on a single controller is possible but difficult
- One solution is to split the task to multiple controllers

> [!DEFINE] Distributed Processing
> Splitting a task to multiple controllers and each run is independent except for the occasional handshaking
