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

Our approach is to write code on the Moonrockers robot directly through
ssh when possible. Otherwise git source control will be used to work on 
code off of the robot. This is possible because the robot runs Linux on
a Raspberry pi and an O-Droid XU4 with an internet connection. 

Various scripts, algorithms, and services can be edited and restarted in
real-time to allow quick and easy end to end testing of the systems.

Dependencies
------------

There are several dependencies for the projects testing design. For the
purposes of this testing document we will divide the dependencies into
software and hardware catagories.

Below are a list of testing software/framework dependencies for this 
project:

* An Ubunutu 16.04 OS
* Python 2.7
* ROS Kinetic setup in as described in the project development environment section.
* Access to the Moonrockers code repository.
* A wifi network connection shared with the robot.
* SSH capability (for comunication with robot's systems)

Below are a list of testing hardware dependencies for this project:

* Test competition arena (to scale)
* Test deposition hopper (to scale)
* Hopper AR-Tag Bundle (exact layout described in the repository documentation)
* The Moonrockers competition robot
* Xbox 360 Controller (manual robot control)
* Development computer (with aforementioned software)

Test design and setup
---------------------

Additional resources are available to do physical testing of the robot in a mock
competition environment. There is a taped full-scale outline of the competition field
indoors in the Moonrockers workspace. The hopper location is also taped out. This 
field is used for location testing as well as some navigation testing. The robot can
see the AR tags on a fake hopper and determine its location on the field. This setup
is used for basic navigation testing only since the excavation system cannot operate
on concrete and the robot moves differently on concrete than it does on a sandy surface.
There will be a full sized practice arena with gravel and dust simulating the conditions
that will exist in the competition, however this is still being constructed. There is
also a volleyball court which is used to test the behavior of the robot while driving
on sand as well as testing the excavation system by digging in the sand.

Localization
~~~~~~~~~~~~

Testing of the localization system will consist of physical tests as well as unit
testing of the individual components. Since cameras are not yet mounted on the robot,
a cardboard cutout is used to hold the cameras in at similar locations and angles relative
to each other as they will be mounted on the robot. This cardboard cutout is placed at
various locations marked out on the taped outline of the field. The localization algorithm
computes the x and y coordinates of the center of the robot or center of the cameras (
The corner with the hopper is (0,0)). The computed coordinates are compared to the actual
measured coordinates of the cardboard cutout and verified for accuracy. Testing the actual
algorithm without physicals moving the cameras is done by mocking the data being sent by
the cameras, but since the data is complex to mock, the camera data is recorded so the same
data can be fed in to the localization node consistently and the results should not vary.
Though the data is filtered so exact matching of results is no expected. Once the cameras 
are mounted to the robot, moving tests will be conducted to ensure the coordinates of the 
robot are being correctly recomputed as the robot moves as well as ensuring the cameras can 
maintain view of the AR tags while shaking.

Environmental tests will be conducted once the practice field is built. This will ensure 
the cameras can maintain sight of the AR tags while moving within a dusty environment and
uneven terrain. A similar testing method will be used in this environment. 


The majority of the testing is done via physical tests. These consist of actually 
placing the robot with the cameras attached on the practice field and observing the
location given by the localization algorithm. 

Test cases were though up during conception of the project requirements.
The test cases closely resemble the project requirements in that we have
the ability to directly test the requirements of the project as 
described below.

Requirements given test cases:

* Localization
* Navigation algorithm
* Collection algorithm
* Deposition algorithm
* Contingency algorithms 

Localization is the most important requirement of the autonomous system.
Localization is being tested for accuracy and repeatability. Tests for
system redundancy with the multiple camera systems as well as resilience
to dust and camera failures are preformed as well.

Navigation systems require tests for repeatability as well as system 
integration with the localization systems. A working navigation system 
opens up further testing for localization in that we can test the 
localization in the context of a moving robot in the final environment.

Collection and Deposition systems can be tested after the navigational 
systems are reliable enough to get the robot from one point to another.
These systems are tested for correctness and resilience to the tough
and rouged environment of dealing directly with the inconsistencies of
digging.  Repeatability is also important in these systems because the 
result of some actions need to be predictable to the system in order to 
have the robot mine most effectively.

Contingency tests require some different testing strategies from the 
other systems. This testing strategy will focus on positive detection of 
the scenario required for a given contingency algorithm to activate.
Also important is the success rate of our contingency code to get the 
robot back to a usable state quickly.

System Testing
--------------

This section focuses on the system testing or the methods that could be
used to fully end to end test the robotic systems in a competition like
environment. It should be noted that fully automated end to end testing 
of the robot is out of the scope of 2018/2019 autonomy project. For this
project we are preforming manual system testing using verificaiton of 
realworld results. The automated end to end testing can be preformed with
a ros simulation package called gazebo.  However, automated testing with
gazebo requires a lot of time to setup and extensive 3d modeling of the 
physical robot and environment.

For system tests relating to accuracy, particularly in relation to the
localization systems, we use manual measurement with tape measures to 
verify the correctness of a particular distance or position measurement.
Other accuracy tests may include changing the state or conditions the 
system is operating in and then verifying the accuracy manually again.

Like with accuracy system tests, tests for resilience to failure are done by 
changing the state of the system or the operating conditions to something
less desirable and noting the results and the ability of the system to
cooperate with the challenge. In addition to changing the operating
conditions we also can spoof sensor data using ROS's built in 
publisher/subscriber framework. With the abillity to spoof sensor data,
false sensor readings can be sent to various other parts of the system
to see how they respond.

For a repeatability system tests, keeping the environment and state of the
system the same is important. If this portion of the system testing was
performed on an automated simulation environment, this would be trivial.
Without simulations, however, careful attention must be given to the state
of the system, the starting state of the robot, and the envrionment it is 
in. Keeping these variables the same (within reason) helps to repeatedly
test and manually measure the results to very repeatabillity of a given
system. Having an active SSH connection into the system helps with 
resetting the state of the system after each test iteration.  Values of
interest are recorded by hand or electronically and the results of several
runs can be compared for consistency.

System Integration Analysis
---------------------------

Apart from testing of overall requirements for the project, there is a 
need for testing of other aspects of the systems.  These tests are more
of a benchmark for how well a specific requirement was fulfilled and not
on whether the requirement was met.

One such test is the system resources test. Since these algorithms are
being run on relatively small SOCs like a Raspberry Pi or an O-Droid,
the system needs to be efficient. Efficient code is important for
reliability of the system.  If a given algorithm uses too much resources
it may cause issues for the other systems trying to run the robot such as
the scheduler or other important operations.

This ensures that future expansions to the algorithms are easy and require
fewer large scale changes to the system due to an overrun of system
resources. 

Repository Testing
------------------

For the GitLab repository, we ensure that things do not easily get broken
with simple gated check-ins using continuous integration checking for basic
syntax validity checking. A master branch is kept clean of commits and is
only merged from a dev branch. Dev gets merged to from various feature
branches. 

This setup is easily expendable and unit-tests could be added in the
future, however, a need for unit testing hasn't been found. This is largely 
in part to the manual nature of many of the tests required. 

Risk Analysis
-------------

Figure 1 (below) shows a risk analysis table, with failure severity on 
the y-axis and failure likelihood on the x-axis. Of most importance are
the items listed in the upper right region of the table. These items
correspond to the most likely and most severe risks on our project.

.. figure:: ./risk.png
	:alt: Risk Analysis Chart [Figure 1]
	:width: 75.0%

	Risk Analysis Chart [Figure 1]

For the Moonrockers project, our biggest risk concern is complexity
underestimation.  This is a fairly common risk among most larger projects
and this project is no exception. The risk is severe due to the delays 
complexity underestimation can bring into a project.

Risk Mitigation
~~~~~~~~~~~~~~~

In order to mitigate some of the risks analyzed in the previous section
we plan to stick closely to our schedule laid out by the Gantt chart
shown in section 5.8. In order to combat complexity underestimation we
attempt to break down each section and requirement of the project into 
as small of parts as possible. This helps us to think through each part
of the project in more detail. 

For physical risks like sensor failures; we plan to integrate as much
redundancy as is feasible in our system. The system will have many
cameras in case one malfunctions or gets covered in dust. Additionally
the robot has an encoder on each wheel which also provides some
redundancy. 