.. role:: math(raw)
   :format: html latex
..

.. role:: raw-latex(raw)
   :format: latex
..

Design and Implementation
=========================

Systems Goals
-------------

The purpose of this system is to operate the robot autonomously for the
full length of the competition.  

System Overview and Description
-------------------------------

The system consists of three major components: localization, navigation, and
collection-deposition. The localization system is labeled as Localizer in
figure 1. The navigation system is labeled as path planner, and the
collection-deposition system is labeled as Col-Dep Planner. The localization
system is responsible for keeping track of where the robot is on the field.
The navigation system controls the path the robot will take to a different
location. The collection-deposition system will control the collection components
of the robot.

.. figure:: ./diagram.png
   :alt: ROS Network Diagram [Figure 1]
   :width: 75.0%

   ROS Network Diagram [Figure 1]

localization System
~~~~~~~~~~~~~~~~~~~

The localization system is in charge of finding the location of the robot on the
field at any given time. This will mainly involve looking at an AR tag bundle, which
will be placed on the deposition hopper, with four cameras mounted at different 
locations on the robot. If at any time no cameras see the AR tag, the wheel encoder
information will be used in combination with the robots last known position to make
a guess on where the robot is while its moving until one of the cameras gets a visual
of the AR bundle to correct the location.

Navigation System
~~~~~~~~~~~~~~~~~

The navigation system is used to plot a path from the known location of the robot
to where it wants to be. This system will work with the localization system to monitor
how well the robot is following the computed path and adjust as needed. 

Collection-Deposition system
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The collection-deposition system controls the bucket system and deposition belt as
well as the two sets of actuators needed to move the collection arm. When the robot
arrives at a mining site, the collection-deposition system will take over and monitor
the depth of the buckets while digging as well as load sensors to know when the robot
is full. Once back at the hopper, the system will run the deposition belt until the 
load sensors indicate the collection bin is empty.

Technologies Overview
---------------------

The system is being developed using ROS 1 kinetic to control inter process
communication between systems. To track the AR tags on the hopper the library
ar_track_alvar is used along with the tf library to transform the data. The
python library inputs is used to take manual input from the xbox controller in
manual mode. The ROS package robot_localization is also being used for sensor
fusion and filtering of input.

Links for further reading of libraries:

    - ROS kinetic: http://wiki.ros.org/kinetic
    - ar_track_alvar: http://wiki.ros.org/ar_track_alvar
    - tf: http://wiki.ros.org/tf
    - robot_localization: http://wiki.ros.org/robot_localization
    - inputs.py: https://pypi.org/project/inputs/

Architecture and System Design
------------------------------

This is where you will place the overall system design and the
architecture. This section will be very detailed and should be image
rich. There is the old phrase *a picture is worth a thousand words*, in
this class it could be worth hundreds of points (well if you sum up over
the entire team). One needs to enter the design and why a particular
design has been done. THIS IS THE CORE OF THE COURSE.

*It is important for you to say why as much as what.*

Design Selection
~~~~~~~~~~~~~~~~

Failed designs, design ideas, rejected designs here.

Data Structures and Algorithms
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Describe the special data structures and any special algorithms.

Data Flow
~~~~~~~~~

Communications
~~~~~~~~~~~~~~

Classes
~~~~~~~

UML
~~~

UX
~~

UI
~~

MVVM, etc
~~~~~~~~~

Localization System
-------------------

**If the following makes sense, use this outline, if not then modify the
outline**

This section is used to describe the design details for each of the
major components in the system. Note that this chapter is critical for
all tracks. Research tracks would do experimental design here where
other tracks would include the engineering design aspects. This section
is not brief and requires the necessary detail that can be used by the
reader to truly understand the architecture and implementation details
without having to dig into the code.



Technologies Used
~~~~~~~~~~~~~~~~~

The ar_track_alvar library along with the tf library are used by this system. ar_track_alvar
is used to get data about the ar tag bundle such as distance, and angles of rotation using
the cameras. This was developed with a logitech webcam. Recently the cameras being used in the
competition arrived and will be used for this system.

Component Overview
~~~~~~~~~~~~~~~~~~

The localization ROS node will spit out x and y coordinates of the center of the robot.
The coordinate origin is still being determined. Right now the corner of the field with the
hopper will be treated as (0,0) for the field. All the localization system will do is monitor which
camera on the robot is seeing the ar tags, and use the position information about the camera relative to
the robot as well as distance and rotation of the camera relative to the ar tag bundle to determine
where the center of the robot it on the field and possibly return angle of rotation of the robot also.

Architecture Diagram
~~~~~~~~~~~~~~~~~~~~~

.. figure:: ./Localization.png
   :alt: Localization Diagram [Figure 2]
   :width: 20.0%

   Localization Diagram [Figure 2]

Design Details
~~~~~~~~~~~~~~

The localization system takes information from the AR Tag Transform library which is used to
observe the ar tag bundle on the hopper and converts it into x y coordinates. An AR tag bundle
is simple a collection of AR tags. Currently three are being used on the hopper. 

Major Component #2
-------------------

Technologies Used
~~~~~~~~~~~~~~~~~

This section provides a list of technologies used for this component.
The details for the technologies have already been provided in the
Overview section.

Component Overview
~~~~~~~~~~~~~~~~~~

This section can take the form of a list of features.

Phase Overview
~~~~~~~~~~~~~~

This is an extension of the Phase Overview above, but specific to this
component. It is meant to be basically a brief list with space for
marking the phase status.

Architecture Diagram
~~~~~~~~~~~~~~~~~~~~~

It is important to build and maintain an architecture diagram. However,
it may be that a component is best described visually with a data flow
diagram.

Data Flow Diagram
~~~~~~~~~~~~~~~~~

It is important to build and maintain a data flow diagram. However, it
may be that a component is best described visually with an architecture
diagram.

Design Details
~~~~~~~~~~~~~~

This is where the details are presented and may contain subsections.

Major Component #3
-------------------

Technologies Used
~~~~~~~~~~~~~~~~~

This section provides a list of technologies used for this component.
The details for the technologies have already been provided in the
Overview section.

Component Overview
~~~~~~~~~~~~~~~~~~

This section can take the form of a list of features.

Phase Overview
~~~~~~~~~~~~~~

This is an extension of the Phase Overview above, but specific to this
component. It is meant to be basically a brief list with space for
marking the phase status.

Architecture Diagram
~~~~~~~~~~~~~~~~~~~~~

It is important to build and maintain an architecture diagram. However,
it may be that a component is best described visually with a data flow
diagram.

Data Flow Diagram
~~~~~~~~~~~~~~~~~

It is important to build and maintain a data flow diagram. However, it
may be that a component is best described visually with an architecture
diagram.

Design Details
~~~~~~~~~~~~~~

This is where the details are presented and may contain subsections.
