Release – Setup – Deployment
============================


Dependencies
---------------------------------------

This system is not meant to be deployed on any system other than the one it was
built on.
So, this documentation of setup and deployment will pertain to the Moonrockers'
current hardware setup.
This includes the robot itself, the O-Droid, Raspberry Pi, and the four cameras.

Setup Information
-----------------

All code should already exist on the Odroid and Raspberry Pi.
Should this not be the case, there are two repositories (autonomy-odroid and
autonomy-pi) on the Moonrockers' GitLab that can be cloned onto the O-Droid and
Pi respectively.
There is software (hardware pertaining) set up on the Pi from previous years
that is not documented here.
This document will assume that is in working order.
The O-Droid and the Pi must be connected via Ethernet for autonomy to function.
If running only manual control, then only the Pi is necessary.
The hardware of the robot must be connected via the CAN bus for any control to
work.
For manual control, the Xbox controller needs to be plugged into the Pi.


Each computer has a launch script in the root directory of the repository
(found at `~/catkin/src/`) which will spin up ROS and any nodes needed to run
the robot.
The system can be launched in parts by navigating to the launch directories
pertaining to each node in the ROS flow diagram, and running `ros launch` from
there.
Rviz can be used to view the camera's status, the AR tag bundle location, and
the robot's current position.



System Versioning Information
-----------------------------

A new version of the software is created each year by the new software team.
The new version is set up on the Moonrockers' system and can be deployed from
there.
