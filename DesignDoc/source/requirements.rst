User Stories, Requirements, and Product Backlog
===============================================

Overview
--------

The overview should take the form of an executive summary. Give the
reader a feel for the purpose of the document, what is contained in the
document, and an idea of the purpose for the system or product.

The user stories are provided by the stakeholders. You will create he
backlogs and the requirements, and document here. This chapter should
contain details about each of the requirements and how the requirements
are or will be satisfied in the design and implementation of the system.

Below: list, describe, and define the requirements in this chapter.
There could be any number of sub-sections to help provide the necessary
level of detail.

User Stories
------------

This section can really be seen as the guts of the document. This
section should be the result of discussions with the stakeholders with
regard to the actual functional requirements of the software. It is the
user stories that will be used in the work breakdown structure to build
tasks to fill the product backlog for implementation through the
sprints.

This section should contain sub-sections to define and potentially
provide a breakdown of larger user stories into smaller user stories.
Each component must have a test identified, meaning you need to know how
you plan to test it. If a requirement is not testable, then some
justification needs to be made on why the requirement has been included.
The results of the tests should go in the testing chapter.

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

Specifications
--------------

Any specifications that need to be understood? Put it here.

Product Backlog
---------------

The full initial product backlog should go here. The sprint backlogs are
located in the prototypes chapter.

-  What system will be used to keep track of the backlogs and sprint
   status?

-  Will all parties have access to the Sprint and Product Backlogs?

-  How many Sprints will encompass this particular project?

-  How long are the Sprint Cycles?

-  Are there restrictions on source control?

Research or Proof of Concept Results
------------------------------------

This section is reserved for the discussion centered on any research
that needed to take place before full system design. The research
efforts may have led to the need to actually provide a proof of concept
for approval by the stakeholders. The proof of concept might even go to
the extent of a user interface design or mockups.

Supporting Material
-------------------

This document might contain references or supporting material which
should be documented and discussed either here if appropriate or more
often in the appendices at the end. This material may have been provided
by the stakeholders or it may be material garnered from research tasks.
