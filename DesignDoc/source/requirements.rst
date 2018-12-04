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

Upgrade embedded system.

User Story #1 Breakdown
^^^^^^^^^^^^^^^^^^^^^^^

In order to better handle the computational tasks required for autonomy,
newer more powerful SoCs and embedded systems will be required. The
the current use of a rasberry pi 2 and an ODroid will not suffice. 

This userstory will need to be broken down into research and 
implementation phases. 

User Story #2
~~~~~~~~~~~~~

Camera integration.

User Story #2 Breakdown
^^^^^^^^^^^^^^^^^^^^^^^

Various cameras will be required for the mining robot to be able to see
its environment and gather the required information needed estimate 
the robot's position and orientation.

User Story #3
~~~~~~~~~~~~~

Wideband Antenna Integration.

User Story #3 Breakdown
^^^^^^^^^^^^^^^^^^^^^^^

The wideband antenna system will also be used to estimate the robot's
position and orientation.

User Story #4
~~~~~~~~~~~~~

Localization Algorithm integration.

User Story #4 Breakdown
^^^^^^^^^^^^^^^^^^^^^^^

The localization algorithms will run on the upgraded embedded systems
and utilize the new camera/antenna systems.

User Story #5
~~~~~~~~~~~~~

Integrate motion to goal algorithms.

User Story #5 Breakdown
^^^^^^^^^^^^^^^^^^^^^^^

The motion to goal algorithms will utilize the localization algorithms
and pathfinding algorithms in order to provide the best route to a
destination.  These algorithms will physically move the robot from
one location to another as accurately as possible.

User Story #6
~~~~~~~~~~~~~

Deposition/Mining algorithm integration.

User Story #6 Breakdown
^^^^^^^^^^^^^^^^^^^^^^^

The Deposition/Mining algorithms will use the various sensors on the
rover to effectively mine and deposite regolith on the competition
field. Mining will need to be monitored carefully to ensure enough
material is being mined while ensuring we have not mined too much. 
The deposition algorithm must also ensure that all of the regolith has
been offloaded.

Requirements and Design Constraints
-----------------------------------

Autonomy system refers to all computers and sensor components relating to our project.
Robot system refers to the collection of all systems (including autonomy), physically and digitally.

System Requirements
~~~~~~~~~~~~~~~~~~~

Below are a list of requirements built from information given in the official NASA RMC Rules sheet.

- The Robot System cannot weigh more than 80 kg. The current robot design weighs nearly 80 kg, so our autonomy design must be as light as possible. We must work with the other engineers on the team to balance the weight of the robot.

- The Autonomy System must draw as little power as possible. The team is docked 1 point per watt-hour used in competition.

- The Autonomy system must manage localization of the robot on the playing field.

- The Autonomy system must manage navigation of the robot from one place to another.

- The Autonomy system must manage collection and deposition algorithms and know when to use them.

- The Autonomy system must be capable of executing contingency code to work around a problem. 

Network Requirements
~~~~~~~~~~~~~~~~~~~~

The following are requirements on software communication put in place the the NASA RMC Rules.

- The Autonomy system must have some form of wireless connection to the remote driver.

- The network should be used as little as possible. Due to a 1 penalty point per kilobit/sec (kb/s) of average data used.

- 200kb/s worth of data is charged for each pre-provided situational awareness camera that is used.

Development Environment Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following are requirements for the development environment put in place by existing software and the clients current setup. 

- The Autonomy system must run under Linux.

- The Autonomy system must interact through ROS Kinetic.

- Scripts developed should use Python 2.7 unless libraries or performance demands use of C++

Operational Environment Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

These are the requirements specified by the NASA RMC specifically
related to the competition field of play and the environment that the
robot will be operating in.

- The playing field dimentions must be 5.756m by 3.691m.

- The depth of surface BP-1 is ~30cm

- The depth of the simulated icy regolith below the BP-1 is ~15cm


Project Management Methodology
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The project will be managed through a loose Agile method.
Tasks relating to user stories will be managed through a Trello board.
This team will meet with the Moonrockers team at designated meeting times and workdays weekly.

-  Github will be used to keep track of backlogs and sprint status

-  All parties will have access to the Sprint and Product Backlogs

-  Approximately 20 Sprints will encompass this particular project

-  The Sprints will last 1 week

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

Initial research focused on the best ways to localize the robot on the playing field. ROS Packages for such requirements are plentiful but only a few are relevant and fit our requirements and existing hardware constraints.  The result of this reasearch was to settle on useing AR-Track-Alvar for ROS Kinetic and several cameras to detect AR-Tags and calculate the position of the robot.

Originally several adtitional options existed, like the use of wideband radio antennas for localization eventually we settled on using just the AR-tags with the possibillity of fusing wheel encoder data to improve localization later.

Before further research was done, an MVP / proof of concept was created for the camera tracking system. This involved one camera and a group (bundle) of AR-Tags.  The result of this MVP was a success and proved that this was a viable solution to tracking the position of the robot.

After determining the primary form of localization, research began on optimal setups for the camera arrangement on the robot.  This research included number of cameras, field of view, types of cameras, lens types, and also how to compensate for a distorting lens. First, the camera calibration was found to be taken care of already with some ROS packages and some scripts to produce a camera calibration file. 

With the above knowledge the MVP was improved to a state where multiple cameras could operate at the same time, and the location of the camera was being relayed instead of the orientation and position of the AR-Tags.

Supporting Material
-------------------

Supporting material includes:
	- Official NASA Robotic Mining Competition registration rules and rubric.
	- Pre-existing documentation for the previous systems.
