System and Unit Testing Design
==============================

This section describes the approach taken with regard to system and unit
testing. This chapter does not describe the outcome of those tests. That
will be described in the prototypes chapter.

Overview
--------

For our project we will be able to leverage a realtime connection with
the robot via SSH. This allows us to preform tests on the system itself
in real time and get live debugging information back during execution.

Our approach is to write code on the moonrockers robot directly through
ssh when possible. Otherwise git souce control will be used to work on 
code off of the robot. This is possible becasue the robot runs Linux on
a Raspberry pi and an O-Droid XU4 with an internet connection. 

Various scripts, algorithms, and services can be edited and restarted in
real-time to allow quick and easy end to end testing of the systems.

Dependencies
------------

Below are a list of testing framework dependancies for this project:

* An Ubunutu 16.04 OS
* ROS Kinetic
* Python 2.7
* Access to the moonrockers code repository.
* A wifi network connection shared with the robot.
* SSH capabillity.

Test design and setup
---------------------

Test cases were though up during conception of the project requirements.
The test cases closely resemple the project requirements in that we have
the abillity to directly test the requirements of the project as 
described below.

Requirements given test cases:

* Localization
* Navigation algorithm
* Collection algorithm
* Deposition algorithm
* Contigency algorithms 

Localization is the most important requirement of the autonomous system.
Localization is being tested for accuracy and repeatabillity. Tests for
system redundancy with the multiple camera systems as well as resiliance
to dust and camera failures are preformed as well.

Navigation systems require tests for repeatabillity as well as system 
integration with the localization systems. A working navigation system 
opens up further testing for localization in that we can test the 
localization in the context of a moving robot in the final environment.

Collection and Deposition systems can be tested after the navigational 
systems are reliable enough to get the robot from one point to another.
These systems are tested for correcteness and resiliance to the tough
and rouged environment of dealing directly with the inconsistencies of
digging.  Repeatabillity is also important in these systems because the 
result of some actions need to be predicatable to the system in order to 
have the robot mine most effectively.

Contingency tests require some different testing strategies from the 
other systems. This testing strategy will focus on positive detection of 
the scenario required for a given contingency algorithm to activate.
Also important is the success rate of our contingency code to get the 
robot back to a usable state quickly.

System Testing
--------------

This section focuses on some of the methods we used to test the
requirements given above. It is important to note that many of these 
tests are manual in nature due to the nature of the systems being used.
The robotic systems are physical systems, therefore many of the tests 
require manual user operation outside of code. For example, simple 
unit tests or other code based testing techniques would not be able to 
provide a level of testing that we need for these systems. This is
because you cannot test the vallidity of a sensor reading from code, it
must be verified mamnually.

For tests relating to accuracy, particularly in relation to the
localization systems, we use manual measurement with tape measures to 
verify the correctness of a particular distance or position measurement.
Other accuracy tests may include chaning the state or conditions the 
system is operating in and then veryfying the accuracy manually again.

Like with accuracy tests, tests for resiliance to failure are done by 
changing the state of the system or the operating conditions to something
less desireable and noting the results and the abillity of the system to
cooperate with the challenge.

For a repeatabillity test, keeping the environment and state of the
system the same is important.  Having an SSH connection into the system
helps with resetting the state of the system after each test.  Values of
interest are recorded by hand or electronically and the results of several
runs are compared for consistency.

System Integration Analysis
---------------------------

Appart from testing of overall requirements for the project, there is a 
need for testing of other aspects of the systems.  These tests are more
of a benchmark for how well a specific requirement was fulfilled and not
on whether the requirement was met.

One such test is the system resources test. Since these algorithms are
being run on relatively small SOCs like a Raspberry Pi or an O-Droid,
the system needs to be efficient. Efficient code is important for
reliabillity of the system.  If a given algorithm uses too much resources
it may cause issues for the other systems trying to run the robot such as
the scheduler or other important operations.

This ensures that future expansions to the algorithms are easy and require
fewer large scale changes to the system due to an overrun of system
resources. 

Repository Testing
------------------

For the Gitlab repository, we ensure that things do not easily get broken
with simple gated checkins using continuous integration checking for basic
syntax validity checking. A master branch is kept clean of commits and is
only merged from a dev branch. Dev gets merged to from various feature
branches. 

This setup is easily extendable and unit-tests could be added in the
future, however, a need for unit testing hasnt been found. This is largely 
in part to the manual nature of many of the tests required. 

Risk Analysis
-------------

Figure 1 (below) shows a risk analysis table, with failure severity on 
the y-axis and failure likelyhood on the x-axis. Of most importantce are
the items listed in the upper right region of the table. These items
corespond to the most likely and most severe risks on our project.

.. figure:: ./risk.png
	:alt: Risk Analysis Chart [Figure 1]
	:width: 75.0%

	Risk Analysis Chart [Figure 1]

For the moonrockers project, our biggest risk concern is complexity
underestimation.  This is a fairly common risk among most larger projects
and this project is no exception. The risk is severe due to the delays 
complexity underestimation can bring into a project.

Risk Mitigation
~~~~~~~~~~~~~~~

In order to mitigate some of the risks analyzed in the previous section
we plan to stick closely to our schedule layed out by the gantt chart
shown in seciton 5.8. In order to combat complexity underestimation we
attempt to break down each section and requirement of the project into 
as small of parts as possible. This helps us to think through each part
of the project in more detail. 

For physical risks like sensor failures; we plan to integrate as much
redundancy as is feasable in our system. The system will have many
cameras incase one malfunctions or gets covered in dust. Additionally
the robot has an encoder on each wheel which also provides some
redundancy. 