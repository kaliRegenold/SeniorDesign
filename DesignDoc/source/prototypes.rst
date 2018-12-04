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

Sprint Analytics
~~~~~~~~~~~~~~~~
[insert pictures of brain box here]








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
ar tags, antenna, and encoders/IMU. At this moment, we're not sure what tools
we'll need to complete the challenge, but we have basic algorithms designed.

Sprint Analytics
~~~~~~~~~~~~~~~~
[Insert ROS diagram here]





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

Sprint Analytics
~~~~~~~~~~~~~~~~




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

Sprint Analytics
~~~~~~~~~~~~~~~~
[Put in pictures of cool ASUS stuff?]





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

Sprint Analytics
~~~~~~~~~~~~~~~~




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

Sprint Analytics
~~~~~~~~~~~~~~~~





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

Sprint Analytics
~~~~~~~~~~~~~~~~



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

Sprint Analytics
~~~~~~~~~~~~~~~~


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

Sprint Analytics
~~~~~~~~~~~~~~~~



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

Sprint Analytics
~~~~~~~~~~~~~~~~



Sprint 11 Report
----------------
2018.10.26

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


Sprint Analytics
~~~~~~~~~~~~~~~~
