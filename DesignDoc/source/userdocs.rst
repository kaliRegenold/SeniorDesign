User Documentation
==================

The robot can be driven in two different ways. Either the controller can be
plugged in directly to the Raspberry Pi or the controller can be plugged in to a
laptop and driven over a network. 

In order to operate the robot with the controller plugged in to the Raspberry
Pi, the computers should be turned on as done in previous years. The controller
can be disconnected and reconnected at any time without reboot however the last
command is remembered. If the controller becomes unplugged while driving, the
robot will continue driving until the controller is plugged back in to give a
different command or the emergency stop is pressed. On boot, the necessary ROS
nodes will be launched automatically so the user is not required to interact
with an external computer. The Xbox controller will operate the robot in a tank
drive format. The left joystick controls the speed and direction of the left two
wheels and the right joystick controls the right wheels. The deposition system
speed is controlled with the right trigger and the collection system speed is
controlled with the left trigger. Both of these systems operate in only one
direction. The X and Y buttons control the collection system in and out and the
A and B buttons control the collection system angle in and angle out. The left
and right bumper no longer actuate one actuator because that only led to
problems.

In order to operate the robot through a network such as in the competition, an
ubuntu laptop connected to a router will be needed. The Xbox controller will
need to be plugged in to the laptop. The user will have to launch the given ROS
file on the laptop. This will run the Xbox node on the laptop and send the Xbox
controller output through the router to the WiFi on the Pi which will drive the
robot in the same manner as plugging the controller directly in to the Pi. 

Autonomy is started and stopped by pressing the start button on the controller.
Once the button is pressed, all controller commands (except the start button)
are ignored. However the controller is still required to stop autonomy. Autonomy
has one start state, the start of a competition run. If autonomy is stopped at
any point, all progress is lost and the autonomy upon restart autonomy will
restart from the starting position. Meaning without temporarily changing the
code, you can not tell the robot to start in its collection state. It only ever
starts in the initial localization state. 

In order for autonomy to run, the provided AR tag banner must be attached to the
hopper and the robot must be placed in a way such that it can view the AR banner
with a camera or rotate so it can see the banner. This is required to get an
initial position for the robot on the field.
