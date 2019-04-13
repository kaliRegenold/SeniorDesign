Sprint Results and Prototypes
=============================

Sprint 1 Report
---------------
2018.09.17

Sprint Backlog
~~~~~~~~~~~~~~
    - Read RMC rules and understand the challenge
    - Take apart the brain box and note what hardware we have to work with
    - Read old documentation
    - Access and read Moonrocker's repository
    - Research ROS

Deliverable
~~~~~~~~~~~
Knowledge

Results of testing
~~~~~~~~~~~~~~~~~~
N/A

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Robot works on startup
    - All code is present within the repository
Failures
    - Documentation is thin
    - We don't fully understand what all they have implemented

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was spent familiarizing ourselves with the team, the robot, and the
challenge at hand.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
We successfully familiarized ourselves with what we have to work with and the
challenge we need to complete. At this point, there's a lot a do and to research.


Sprint 2 Report
---------------
2018.09.24

Sprint Backlog
~~~~~~~~~~~~~~
    - Create ROS node network diagram
    - Decide on what tools to use (e.g., ROS2 vs ROS1)
    - Create rough algorithms
    - Research different sensors/tools

Deliverable
~~~~~~~~~~~
    - Research
    - ROS node network diagram

Results of testing
~~~~~~~~~~~~~~~~~~
N/A

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Created a rough Ros network node diagram
    - Decided on ROS1 (This is what the robot is already programmed in)
Failures
    - No decision on what sensors to use

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was spent determining what we need to complete this challenge.


Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
Previous teams have attacked localization with a couple different strategies:
AR tags, antenna, and encoders/IMU. At this moment, we're not sure what tools
we'll need to complete the challenge, but we have basic algorithms designed.


Sprint 3 Report
---------------
2018.10.01

Sprint Backlog
~~~~~~~~~~~~~~
    - Research tools
    - Decide on sensors

Deliverable
~~~~~~~~~~~
Decision on sensors: 2 ASTRA cameras, two antennas (from last year).

Results of testing
~~~~~~~~~~~~~~~~~~
N/A

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Decision made on sensors
Failures
    - (From the future) We didn't really take a look at all edge cases...

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Technical backlog created and preliminary design created.

Sprint Review
~~~~~~~~~~~~~
This sprint was a continuation of the last sprint.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
We were able to decide on the sensors we'd like to use.
The antennas aren't a main priority for us, and we're mostly pushing that over to the EEs.
The AR Tag system seems like a good start; the team has used them in the past.


Sprint 4 Report
---------------
2018.09.08

Sprint Backlog
~~~~~~~~~~~~~~
    - Interface with ASUS/ASTRA
    - Brush up on ROS

Deliverable
~~~~~~~~~~~
Environment in which to run ROS1 and the ASUS nodes.

Results of testing
~~~~~~~~~~~~~~~~~~
We are able to correctly interface with the ASUS and see video and depth map.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Interfacing with the ASUS
    - Tinkering with ROS and the ASUS together
Failures
    - Interfacing with the ASTRA

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was taking the time to understand the interfaces for the tools we
are going to be using.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
This sprint feels like it was unproductive, because there weren't any
deliverables directly related to the Moonrocker's robot.
We did gain technical knowledge, though, to use toward developing for the robot.



Sprint 5 Report
---------------
2018.10.15

Sprint Backlog
~~~~~~~~~~~~~~
    - Calibrate cameras
    - Detect AR tags

Deliverable
~~~~~~~~~~~
    - Preliminary AR tag detection code
    - Camera calibration files
    - AR tag

Results of testing
~~~~~~~~~~~~~~~~~~
AR tag code can correctly identify an AR tag.
ar_track_alvar node reports (x,y,z) data and quaternion data of AR tag.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Created code to detect AR tags
    - Created code and files for camera calibration
Failures
    - The understanding of the ar_track_alvar node is shaky.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was creating the preliminary code to detect AR tags.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
The code is not finalized, but it's an MVP for future AR tag code.
This is the beginning of the localization node.


Sprint 6 Report
---------------
2018.10.22

Sprint Backlog
~~~~~~~~~~~~~~
    - Detect AR tag bundles

Deliverable
~~~~~~~~~~~
    - 3' calibration board
    - Rough AR tag bundle
    - AR tag bundle measurements
    - AR tag bundle XML

Results of testing
~~~~~~~~~~~~~~~~~~
Camera calibration more accurate with larger calibration board.
AR tag data more accurate (and less "jumpy") using a bundle system.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - AR tag data is more accurate
Failures
    - We have no good system for measuring AR tag bundles, besides by hand, which is time consuming.
    - We have realized that we need WAY more cameras, and are bumping up to 4.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Rework the current design to include several more cameras.
This means we need a switching mechanism to pull data from only one (or two) cameras at a time).
The AR tags system seems reliable enough to kill the antenna work and just use the tags.

Sprint Review
~~~~~~~~~~~~~
This sprint was developing the AR tag nodes with better camera calibration and AR tag bundles.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
This sprint was incredible productive. We saw a flaw in our design though,
and will have to work with the team to create a system for more cameras.





Sprint 7 Report
---------------
2018.10.29

Sprint Backlog
~~~~~~~~~~~~~~
    - Localization node

Deliverable
~~~~~~~~~~~
Localization node to report robot location.

Results of testing
~~~~~~~~~~~~~~~~~~
Localization node reports accurate distance.
More testing needs to be done to find error of data, given several distances.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Localization node outputs distance from robot to AR tag.
Failures
    - Localization node output rotation of AR tag, not the robot.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was creating the MVP of the localization node.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
Localization node report accurate distances, but the rotation information is off.
We'll have to find the correct way to transform it.



Sprint 8 Report
---------------
2018.11.05

Sprint Backlog
~~~~~~~~~~~~~~
    - Create pseudocontroller node
    - Rework the file system

Deliverable
~~~~~~~~~~~
Pseudocontroller node

Results of testing
~~~~~~~~~~~~~~~~~~
The robot moves when told.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Created a pseudocontroller node to interface with the robot
    - Created a more coherent file system structure and linked ROS packages together
Failures
    - Part of the package linking doesn't work

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was spent creating the pseudocontroller node and reworking the autonomy file system.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
The pseudocontroller is a very critical part of the robot autonomy, as it
allows our code to interface with the robot's code.
The file system rework was standard house cleaning and needed to be done.


Sprint 9 Report
---------------
2018.11.12

Sprint Backlog
~~~~~~~~~~~~~~
    - Resolve Raspberry Pi network issues

Deliverable
~~~~~~~~~~~
N/A

Results of testing
~~~~~~~~~~~~~~~~~~
Raspberry Pi networking is finicky at best.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Understand the Raspberry Pi network
    - Understand what the previous team did to make it work like that
Failures
    - Spent a lot of time on it
    - Sometimes fails anyway

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add to backlog: Fix Pi network issues.

Sprint Review
~~~~~~~~~~~~~
This sprint was spent fixing pi troubles.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
We were almost entirely blocked by the Pi not connecting to wifi or ethernet.
Plugging in the pi to a monitor and running the robot at the time time is nearly
impossible, so this had to be fixed immediately.


Sprint 10 Report
----------------
2018.11.19

Sprint Backlog
~~~~~~~~~~~~~~

Deliverable
~~~~~~~~~~~

Results of testing
~~~~~~~~~~~~~~~~~~

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Sprint Review
~~~~~~~~~~~~~
Thanksgiving, no progress

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~


Sprint 11 Report
----------------
2018.11.26

Sprint Backlog
~~~~~~~~~~~~~~
    - Develop localization node to use two cameras

Deliverable
~~~~~~~~~~~
More developed localization node

Results of testing
~~~~~~~~~~~~~~~~~~
No tests ran, yet

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - Our code easily accepted more than one camera feed
    - Localization node successfully listens to two camera feeds
Failures
    - Not much testing done as far as data accuracy

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
N/A

Sprint Review
~~~~~~~~~~~~~
This sprint was integrating another camera into the localization code.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
We got the cameras in this week, so we wrote the second one into our code.
This was an extremely smooth process, which was nice.
We did not get to test the fidelity of the data coming form the two cameras, though.

Sprint 12 Report
----------------
2019.1.6

Sprint Backlog
~~~~~~~~~~~~~~
    -Tested the localization system operation with multiple cameras.

Deliverable
~~~~~~~~~~~
More progress made for the localization node.

Results of testing
~~~~~~~~~~~~~~~~~~
Up until now, only one or two cameras plugged directly into the odroid. This
worked fine, though the distance measurement jumped back and forth as the
cameras were both being looked at and were feeding data that was slightly off
because they were separated by a few inches. We had future plans to deal with
this by applying a transform to each camera giving information so each camera
knows where it is relative to the robot and can adjust its measurements. This
would make each camera give the same information as the others. Four cameras
were needed to see all around the robot and the odroid only has three USB ports
so a hub would be used to connect them. We plugged all four cameras into the USB
3.0 hub and into the odroid and realized nothing worked. The cameras are all USB
2.0 devices and even though there is theoretically enough throughput capacity to
run all the cameras at the same time, this could not be done. Even two cameras
running at the same time caused the node to crash. This was verified on multiple
other computers and online forums. No computer was capable of looking at the
camera feed of more than one camera at a time when connected to USB hub. 

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    -The localization still worked when the cameras were plugged in to the odroid directly.
Failures
    -The USB hub can not operate all the cameras at the same time. 

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
This problem was not accounted for and had to be fixed. We had to prevent ROS
from launching more than one camera node at a time. We decided to implement a
camera switching algorithm to handle it.

Sprint Review
~~~~~~~~~~~~~
We attempted to get all four cameras working for localization but ran in to
hardware limitations of USB. Which is ridiculous.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
We ran in to unforseen issue and brainstormed ways on how to fix them. We
expected this to just work as we had it working with two cameras plugged
directly into the odroid without a problem.

Sprint 13 Report
----------------
2019.1.13

Sprint Backlog
~~~~~~~~~~~~~~
    -Implemented a camera switching algorithm.

Deliverable
~~~~~~~~~~~
    -More progress was made on the localization system.

Results of testing
~~~~~~~~~~~~~~~~~~
Because of the issue last sprint, a camera switching algorithm was added to
start and stop camera nodes depending on if they could see the tags. Depending
on the orientation of the robot, either one or two cameras will be able to see
the AR tags. The algorithm cycles between the cameras, turning them on then off
if they dont pick up the AR tag bundle within a certain time frame. If the
cameras see the bundle, the camera stays on and the cycling pauses until the
camera looses the bundle for a certain period of time. This was tested by
plugging all four cameras in and moving them so they pointed at the tags one at
a time. 

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    -The camera switching algorithm seemed to work fine and the distance simply
    jumped once a new camera was selected. This would be addressed later.
Failures
    -Since ar_track_alvar takes a second to find the bundle, we had to pause on
    each camera when it was selected to give it a chance to find the bundle
    which slowed the switching down. If switching sequentially from camera 0 to
    3, if the tags were viewed from camera 3 then the robot rotated to camera 2,
    cameras 0 and 1 are checked first, causing a delay in the data.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
With the algorithm in place, the camera was working as we intended it to by just
plugging them in as planned.

Sprint Review
~~~~~~~~~~~~~
Camera switching was added and is functional.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
The cameras were tested by hand on a cardboard cutout since they were not
mounted to the robot yet which was not ideal but allowed us to test the
algorithm. Considering this was not planned for, this quick fix worked well.

Sprint Analytics
~~~~~~~~~~~~~~~~


Sprint 14 Report
----------------
2019.1.20

Sprint Backlog
~~~~~~~~~~~~~~
    -Added wheel encoder information to the localization system.

Deliverable
~~~~~~~~~~~
    -Improved the localization system.

Results of testing
~~~~~~~~~~~~~~~~~~
To get more accurate results for localizing the robot, we decided to combine the
data given by the camera system with the wheel encoder information to better
find the location of the robot. If the cameras lost sight of the tags for a few
seconds, the wheel encoder information would continue feeding location data
calculated from the robots kinematics and the wheel speed data. Even if the
cameras were giving location information, it could be verified with the wheel
speed data. We wasted some time because previously written code incorrectly
calculated the robots motion because one of the wheels was being ignored. This
initially caused confusion as we did not expect the bug to be in last years
code.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    -The encoder information from the wheels was verified to be correct be
    driving the robot around and comparing the distance driven to the calculated
    distance driven.

Failures
    -The robot velocities were initially off because of a bug in last years
    code. This caused unnecessary time to be spent looking for the problem.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The use of the encoders was intended from the beginning so no major modifications were necessary.

Sprint Review
~~~~~~~~~~~~~
This sprint focused on using the encoder information on the drive motors and the
kinematic data to estimate the robots position. This method does require a
starting position be known, which has to be provided by the cameras.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
The sensor fusion between the encoder data and the camera data still needs
refinement but progress was made.


Sprint 15 Report
----------------
2019.1.27

Sprint Backlog
~~~~~~~~~~~~~~
    -Revised collection and deposition algorithms.

Deliverable
~~~~~~~~~~~
    -Made modifications to the collection and deposition systems we thought
    would work initially.

Results of testing
~~~~~~~~~~~~~~~~~~
Concerns were brought up of the robot's capability to mine 30cm down to collect
the regolith after extending the actuators all the way down and back up when
testing the actuator movement. The actuators that lower the bucket chain into
the ground move very slow which caused concerns with our current method of
digging the bp-1 off the surface, retracting the buckets, turning the robot and
dumping out the useless bp-1 before turning back toward the hole and extending
the buckets all the way back down to dig the regolith. This would take a
considerable amount of time. The robot is required to make two excavation trips
and the whole run must be completed in ten minutes. In order to save time and
algorithm complexity, it was decided the robot would dig until it reached the
regolith, then deposit the bp-1 directly behind it to empty the collection bin
before continuing to dig. This saved time and complexity since we would not need
to relocate the hole. 

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    -Found a better solution for the collection and deposition algorithms.

Failures
    -Battery problems prevented further testing on the robot.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The requirements remain the same, the methods used for collection and deposition
were modified for simplicity and because of time constraints. Previous team
members confirmed the capabilities of the robot which should be able to drive
over the bp-1 deposited behind it.

Sprint Review
~~~~~~~~~~~~~
This sprint focused on revising algorithms and we came out with better solutions.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
Battery problems prevented the robot from driving. The CSC team seemed to be the only
people around so we began fixing the problems ourselves.



Sprint 16 Report
----------------
2019.2.3

Sprint Backlog
~~~~~~~~~~~~~~
    -Resolved hardware issues and rebuild brain box.

Deliverable
~~~~~~~~~~~
    -This sprint fixed hardware problems related to development.

Results of testing
~~~~~~~~~~~~~~~~~~
The USB 3.0 hub need for the cameras could not fit in the original brain box
enclosure which also blocked certain ports on the pi and odroid. We ended up
temporarily relocating the equipment into a new larger enclosure and wired it up
to the best of our ability because no EE members were present.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    -Made the robot operational again

Failures
    -Continuing battery problems
    -None of the hardware problems should have been an issue. Cameras should
    also have been mounted by now.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The brain box was redesigned and rebuilt to accommodate our added hardware. 

Sprint Review
~~~~~~~~~~~~~
The robot was fixed to make it operational again.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
Not enough got done and some of the hardware problems should be dealt with by
other team members which did not happen.


Sprint 17 Report
----------------
2019.2.10

Sprint Backlog
~~~~~~~~~~~~~~
    -Implemented an updated configuration file used for field and robot parameters.

Deliverable
~~~~~~~~~~~
    -This addition affected mainly localization and path planning.

Results of testing
~~~~~~~~~~~~~~~~~~
A configuration file to store the field dimension, robot dimensions, coordinate
offsets for AR tag bundle and camera placement, etc. was conceived early on but
existed in whiteboard form only. We added the configuration file to the robot
and moved parameters to it. This would centralize any dimensions that could
change in the future and make changes to the parameters simple and easy.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    -Configuration file added to code.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
No major modifications were made to the design.

Sprint Review
~~~~~~~~~~~~~
Progress was made even though we were still waiting for camera mounts and a
collection bin to begin testing on the actual robot.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
More could have been accomplished if the hardware were ready by this point.


Sprint 18 Report
----------------
2019.2.17

Sprint Backlog
~~~~~~~~~~~~~~
    -Discussed NASA Competition cancellation.

Deliverable
~~~~~~~~~~~
    -Deliverables were subject to change depending on if the competition would
    still be held.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Failures
    -We do not know what will be required of NASA's now virtual competition.
    -If the competition is held at a private location, rules may change.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Unknown modifications will have to be made to account for rule changes if a
third party decides to host their own competition.

Sprint Review
~~~~~~~~~~~~~
The team held an emergency meeting to discuss the course of action and look at
competition proposals from Alabama and Central Florida.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
This dealt a blow to the teams current plans and left a lot of unknowns as we
decided how to proceed.


Sprint 19 Report
----------------
2019.3.10

Sprint Backlog
~~~~~~~~~~~~~~
    - Develop contingency algorithm to allow the robot to find ar-tags when lost.
    - Continue developing on point to point path traversal.

Deliverable
~~~~~~~~~~~
    - A robot that is capable of relocating itself on the field if an AR-tag is lost.
    - A robot that does not provide completely false localization data if AR-tags are not visible.
    - A starting point for the simple path traversal algorithm with some configurable parameters.

Results of testing
~~~~~~~~~~~~~~~~~~
The robot was able to search for AR-tags when first placed on the playing field.  
If the Ar-tags are not found the robot successfully executed a 45 degree rotation to help align cameras.
After several tests placing the robot in different locations and angles, the Ar-tags were always found.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - The code remained modular and made extra use of the config file developed previously.
    - Localization is now more self sufficient.
    - The robot can locate it self on the field at startup or after a loss of Ar-tag visibility.
Failures
    - A new bug relating to robot angle with 2 of the 4 cameras became apparent.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
No changes needed to be made to this sprint.

Sprint Review
~~~~~~~~~~~~~
The appearance of the robot angle bug is a small setback but the robot is moving closer to complete autonomy.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
Because the cameras already cycle through automatically to find an AR-tag this algorithm was fairly easy
to write. Most of this sprint involved testing that resulted in another set of good verifiable test results
on the localization system. Also the bug that was revealed once fixed will improve accuracy of the robot's 
localization.


Sprint 20 Report
----------------
2019.3.17

Sprint Backlog
~~~~~~~~~~~~~~
    - Fix remaining localization bugs
    - Improve robot localization accuracy between AR-Tag updates (while moving over rough terrain)
    - Expose more low level hardware information to ROS nodes (such as motor current data)
    - Design new full hopper AR-Tag array
    - Continue work on point to point path traversal

Deliverable
~~~~~~~~~~~
	- Accurate localization with no angle errors for some cameras
	- Localization that interpolates using encoder data between Ar-tag updates.
	- A robot with necessary motor current sensor data available to start work on collection and deposition algorithms.
	- A full sized hopper Ar-Tag array to replace the small test Ar-tags.

Results of testing
~~~~~~~~~~~~~~~~~~
After fixing the camera angle bugs testing of the new interpolation begun, followed by testing of the new full sized 
AR-tag array.
	- At first the interpolation of encoder data seemed to be quite inaccurate
	- A small change was made to increase the encoder polling rate improved the accuracy at the cost of more system-resources on the pi.
	- Testing of the full AR-tag array resulted in completely inaccurate localization data.
	- Further investigation revealed the Ar-tag tracking library in use is incapable of properly dealing with Ar-tags of varying sizes.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - The code remained modular and made extra use of the config file developed previously.
    - After some tweaking the encoder data is being used in tandem with the Ar-Tag data successfully.
Failures
    - The unknown limitation of the Ar-Tracking library for varying Ar-tag size.
    - As a result the full size Ar-tag needs to be scrapped and redesigned.


Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Motor current sensing remains on the backlog until path new Ar-tag problems are resolved.

Sprint Review
~~~~~~~~~~~~~
	- This sprint is a bit larger than normal due to part of one of the weeks having a large snow storm.
	- The sprint was mostly successful baring the new found limitations of the Ar-tag tracking library.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
For this sprint there was not much more we could have done to prevent the limitation of a library that has little documentation.
Some design time and a small amount of funds for the professionally printed Ar-tag banner was wasted, however the fix remains quite simple.


Sprint 21 Report
----------------
2019.4.1

Sprint Backlog
~~~~~~~~~~~~~~
    - Redesign a new full sized Ar-tag array.
    - Test accuracy of full sized Ar-tag.
    - More work on path traversing
    - Prepare for Design fair.

Deliverable
~~~~~~~~~~~
	- A full sized hopper Ar-Tag array to replace the small test Ar-tags.
	- A robot capable of traveling between two points.
	- A design fair poster.

Results of testing
~~~~~~~~~~~~~~~~~~
The testing of the new Ar-tag array was a success.  The position data of the from the new full size array is much more stable and accurate.

Successes and Failures
~~~~~~~~~~~~~~~~~~~~~~
Successes
    - The code remained modular and made extra use of the config file developed previously.
    - With the new Ar-tags the added stability and accuracy of the localization is encouraging.
Failures
    - Time management, some inability to meet with team and, other events resulted in less getting done than originally planed.
    - Path traversal was not quite ready to be tested.
    - More battery issues cause the robot to remain immobile.

Modifications required (product backlog, design, requirements, etc)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Path traversal remains on backlog.

Sprint Review
~~~~~~~~~~~~~
- Again this sprint is a bit larger than normal due to part of the following week having a large snow storm.

Sprint Retrospective
~~~~~~~~~~~~~~~~~~~~
This sprint could had more done, however, the snowstorm and some electrical engineer members not able to attend workdays
caused less work to get done than originally planned.  The continued battery issues that plague the robot occasionally prevent 
testing from getting done.

The new Ar-Tag array is large enough to help us further test the camera's ocular calibration. The early results show that we
could do better but it may not be necessary.
