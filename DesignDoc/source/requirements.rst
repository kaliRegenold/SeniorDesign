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

- The Robot System cannot weigh more than 80 kg. The current robot design weighs nearly 80 kg, so our autonomy design must be as light as possible. We must work with the other engineers on the team to balance the weight of the robot.

- The Autonomy System should draw as little power as possible. The team is docked points in competition for power consumption.

- The Autonomy System will run under Linux.

Network Requirements
~~~~~~~~~~~~~~~~~~~~

- The Autonomy system must have some form of wireless connection to the remote driver.

- The network should be used as little as possible.

Development Environment Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- The Autonomy system must run under Linux.

- The Autonomy system must interact through ROS Kinetic.

- The Autonomy system will manage localization/

Project Management Methodology
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The project will be managed through a loose Agile method.
Tasks relating to user stories will be managed through a Trello board.
This team will meet with the Moonrockers team at designated meeting times and workdays weekly.

Product Backlog
---------------

The full initial product backlog should go here. The sprint backlogs are
located in the prototypes chapter.

-  Github will be used to keep track of backlogs and sprint status

-  All parties will have access to the Sprint and Product Backlogs

-  Approximately 20 Sprints will encompass this particular project

-  The Sprints will last 1 week

-  Branches must be used for feature development and code is never pushed directly to master.

Research or Proof of Concept Results
------------------------------------

This section is reserved for the discussion centered on any research
that needed to take place before full system design. The research
efforts may have led to the need to actually provide a proof of concept
for approval by the stakeholders. The proof of concept might even go to
the extent of a user interface design or mockups.

Supporting Material
-------------------

Supporting material includes:
	- Official NASA Robotic Mining Competition registration rules.
	- Pre-existing documentation for the previous systems.
