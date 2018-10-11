Project Management
==================

This section provides some housekeeping type of information with regard
to the team, project, environment, etc.

Team Member’s Roles
-------------------

Describe who was involved and what role(s) were played.

Project Management Approach
---------------------------

This section will provide an explanation of the basic approach to
managing the project. Typically, this would detail how the project will
be managed through a given Agile methodology. The sprint length (i.e. 2
weeks) and product backlog ownership and location (ex. Trello) are
examples of what will be discussed. An overview of the system used to
track sprint tasks, bug or trouble tickets, and user stories would be
warranted.

Stakeholder Information
------------------------

This section would provide the basic description of all of the
stakeholders for the project. Who has an interest in the successful
and/or unsuccessful completion of this project?

Customer or End User (Product Owner)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Who? What role will they play in the project? Will this person or group
manage and prioritize the product backlog? Who will they interact with
on the team to drive product backlog priorities if not done directly?

Management or Instructor (Scrum Master)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Who? What role will they play in the project? Will the Scrum Master
drive the Sprint Meetings?

Investors
~~~~~~~~~

Are there any? Who? What role will they play?

Developers – Testers
~~~~~~~~~~~~~~~~~~~~

Who? Is there a defined project manager, developer, tester, designer,
architect, etc.?

Budget
------

Describe the budget for the project including gifted equipment and
salaries for people on the project.

Intellectual Property and Licensing
-----------------------------------

Describe the IP ownership and issues surrounding IP.

Sprint Overview
---------------

Sprint cycles run every week, ending at the usual Moonrockers meeting time.
While Trello is being used to manage tasks and timelines for completion.

Terminology and Acronyms
------------------------

ROS - Robot Operating System
OpenCV - Open Computer Vision
OpenNI - Open Natural Interaction
RViz - 3D visualization software for ROS
RGBD - Red, Green, Blue, Distance Camera (Distance from IR Throw)
IR - Infrared

Timeline
--------
.. image:: gantt.png

Development Environment
-----------------------

Primary environment is Linux on personal laptops.
Code from personal computers will be pushed to the GitLab repository where it
will then be pulled onto the on-board computers.
Setup information can be found below.

Development IDE and Tools
-------------------------

Since the development environment is on a linux machine and most of
the code is written in python, there is no required IDE and each
developer may use whatever text editor they are most comfortable 
with.

For tools/dependencies all of the following are required: 

* ROS Kinetic With the following packages:
	- Catkin
	- OpenNI
	- AR_Track_Alvar
	- OpenCV3
	- RVIZ
* Python
* C++
* AVR Tools
* OpenCV

Source Control
--------------

The Moonrockers team uses a Gitlab repository for source control of
the current systems on the robot. This is located on the global 
gitlab domain.

For our Sr. design project documentation we have a separate
repository on the SDSMT Gitlab domain.

Using Git for our souce control allows us to use a heirachical
structure for our branching system.  Master and Dev. branchs
is protected with gated checkins.  Each change made to dev has a
dedicated branch for that feature's development.

Build Environment
-----------------

The build and run environment is Ubuntu 16.04 64bit.  This is the 
only version of Ubuntu that will run ROS Kinetic easily. Most of 
the packages are to be written in python and do not need to be 
compiled. Any of the C/C++ code can be compiled with GCC or
Makefiles. 

Development Machine Setup
-------------------------

The following is general a list of the required steps to setup the
development environment.

* Install Ubuntu 16.04 64bit.
* Install ROS 1 Kinetic.
* Install and Compile OpenCV.
* Install all of the aforementioned ROS Packages.
* Install of the AVR Tools.