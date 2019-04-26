User Stories, Requirements, and Product Backlog
===============================================

Overview
--------

This section outlines the requirements for the autonomous systems being
developed for the Moonrockers team. The main tasks are split up into
the user stories below. The requirements in this section illustrate the
specifics of what the system needs to be capable of and what it needs to
handle. Some requirements are a result of the competition rules as set
forth by NASA.

User Stories
------------

User Story #1
~~~~~~~~~~~~~
As a robot, I need to be able to localize myself on the field without using the walls.


User Story #2
~~~~~~~~~~~~~
As a robot, I need to know how to traverse the obstacle section without getting stuck.

Breakdown
^^^^^^^^^^^^^^^^^^^^^^^
	- I'd like to be able to avoid obstacles.
	- If I can't avoid obstacles, I'd like to be able to run over them, or get myself un-stuck.


User Story #3
~~~~~~~~~~~~~
As a robot, I need to know where to dig.

Breakdown
^^^^^^^^^^^^^^^^^^^^^^^
	- I'd like to know when I'm in the digging section of the course.
	- I'd like to know when to start digging.


User Story #4
~~~~~~~~~~~~~
As a robot, I need to be able to collect icy regolith (gravel).

Breakdown
^^^^^^^^^^^^^^^^^^^^^^^
	- I'd like to collect as much icy regolith (gravel) as possible.
	- I'd like to collect as little dry regolith (BP-1) as possible.

User Story #5
~~~~~~~~~~~~~
As a robot, I need to deposit the regolith.

Breakdown
^^^^^^^^^^^^^^^^^^^^^^^
	- I'd like to know when the deposition belt is full.
	- I'd like to know where the hopper is and navigate to it.
	- I'd like to know when I have deposited all of the regolith.


User Story #6
~~~~~~~~~~~~~
As a robot, in general, I need to be able to recover from any problems that arise during the competition.

Breakdown
^^^^^^^^^^^^^^^^^^^^^^^
	- I'd like to be able to continue the run if sensors fail.
	- I'd like to be able to transfer manual control over if I cannot recover.


Requirements and Design Constraints
-----------------------------------

Autonomy system refers to all computers and sensor components relating to our project.
Robot system refers to the collection of all systems (including autonomy), physically, and digitally.

System Requirements
~~~~~~~~~~~~~~~~~~~

Below are a list of requirements built from information given in the official NASA RMC rule sheet.

- The Robot System cannot weigh more than 80 kg. The current robot design weighs nearly 80 kg, so our autonomy design must be as light as possible. We must work with the other engineers on the team to balance the weight of the robot.

- The Autonomy System must draw as little power as possible. The team is docked 1 point per watt-hour used in competition.

- The Autonomy system must manage localization of the robot on the playing field.

- The Autonomy system must manage navigation of the robot from one place to another.

- The Autonomy system must manage collection and deposition algorithms and know when to use them.

- The Autonomy system must be capable of executing contingency code to work around a problem.

Network Requirements
~~~~~~~~~~~~~~~~~~~~

The following are requirements on software communication put in place the the NASA RMC rules.

- The Autonomy system must have some form of wireless connection to the remote driver.

- The network should be used as little as possible due to a 1 point penalty per kilobit/sec (kb/s) of average data used.

- 200kb/s worth of data is charged for each pre-provided situational awareness camera that is used.

Development Environment Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following are requirements for the development environment put in place by existing software and the client's current setup.

- The Autonomy system must run under Linux.

- The Autonomy system must interact through ROS Kinetic.

- Scripts developed should use Python 2.7 unless libraries or performance demands use of C++

Operational Environment Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

These are the requirements specified by the NASA RMC specifically
related to the competition field of play and the environment that the
robot will be operating in.

- The playing field dimensions must be 5.756m by 3.691m.

- The depth of surface BP-1 is ~30cm

- The depth of the simulated icy regolith below the BP-1 is ~15cm


Project Management Methodology
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The project will be managed through a loose Agile method.
Tasks relating to user stories will be managed through a Trello board.
This team will meet with the Moonrockers team at designated meeting times and workdays weekly.

-  GitHub will be used to keep track of backlogs and sprint status

-  All parties will have access to the print and product backlogs

-  Approximately 20 Sprints will encompass this particular project

-  The sprints will last 1 week

-  Branches must be used for feature development and code is never pushed directly to master.

Product Backlog
---------------

The initial product backlog was essentially pulled from our requirements and eventually broken down into much smaller pieces.

- Pseudocontroller to integrate with existing systems.

- Localization of the robot on the playing field.

- Navigation of the robot from one place to another.

- Collection and deposition algorithms.

- Scheduler systems and state machines.

- Contingency code to work around problems.

Research or Proof of Concept Results
------------------------------------

Initial research focused on the best ways to localize the robot on the playing 
field. ROS packages for such requirements are plentiful but only a few are 
relevant and fit our requirements and existing hardware constraints.  The 
result of this research was to settle on using ar_track_alvar for ROS Kinetic 
and several cameras to detect AR tags and calculate the position of the robot.

Originally, several additional options existed, like the use of wideband radio 
antennas for localization. Eventually we settled on using just the AR tags with 
the possibility of fusing wheel encoder data to improve localization later.

Before further research was done, an MVP / proof of concept was created for the 
camera tracking system. This involved one camera and a group (bundle) of 
AR tags.  The result of this MVP was a success and proved that this was a viable
solution to tracking the position of the robot.

After determining the primary form of localization, research began on optimal
setups for the camera arrangement on the robot.  This research included determining the number
of cameras, field of view, types of cameras, lens types, and also how to
compensate for a distorting lens. First, the camera calibration was found to
be taken care of already with some ROS packages and some scripts to produce
a camera calibration file.

With the above knowledge the MVP was improved to a state where multiple cameras
could operate at the same time, and the location of the camera was being relayed 
instead of the orientation and position of the AR tags.

Supporting Material
-------------------

Supporting material includes:
	- Official NASA Robotic Mining Competition registration rules and rubric.
	- Pre-existing documentation for the previous systems.
