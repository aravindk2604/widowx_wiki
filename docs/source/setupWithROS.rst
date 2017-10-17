.. _chapter_setupWithROS:

Setup With ROS
==============

The documentation assumes that ``ROS Kinetic`` is already installed on the host pc. If not, then you may visit `ROS Kinetic setup <http://wiki.ros.org/kinetic/Installation/Ubuntu>`_.

ROS control of the arm independent of the SR300 Sensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Open up a terminal window and enter the following commands.
::

    cd ~/widowx_arm
    source devel/setup.bash
    roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=false

.. image:: _static/commands.png

This should load RVIZ with the proper WidowX arm bringup. You can move the arm using the visual representation on screen, choosing one of the many "Planning Library" under the Context tab and then hitting "Plan and Execute" under the Planning Tab. There are also several presets you can choose from. Once you're done, you can close the program by returning to your terminal window and pressing CTRL + C.

.. image:: _static/rvizInitial.png

ROS control of the arm with the SR300 Sensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Open up a terminal window and enter the following commands
::

    cd ~/widowx_arm
    source devel/setup.bash
    roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=true


This should load RVIZ with the proper WidowX arm bringup, as well as load in the drivers for the SR300. You should see a 3D point map representation of your workspace on the right. You can still move the arm using the visual representation on screen, and hitting "Plan and Execute" under the Planning Tab. We need to move the arm so that we can adjust the camera angle and position.

.. image:: _static/sr300True.png

Arranging your SR300
~~~~~~~~~~~~~~~~~~~~
Keep the previous terminal open and change a few things in RVIZ. Under the Planning tab, in the Query options you will find the "Select Goal State" option.
Select the pulled_back_pose from the goal state. Press Update, then press Plan and Execute. Your arm should move back to a pulled back state, allowing the camera to see the base of the WidowX.
Change your view to a side view of the arm and camera representation. Move the SR300's angle so that the representation of the workspace is level to the base of the WidowX on-screen.
Change your view to an overhead view of the workspace. Move the Camera Stand so that the outline of the base of the WidowX matches to the cutout of the WidowX base on the SR300.

Open a second Terminal window. This will be a control window, so keep it visible when possible
::

    cd ~/widowx_arm
    source devel/setup.bash
    roslaunch widowx_block_manipulation block_sorting_demo.launch

This demo will allow us to do some new things that utilize the SR300's object detection abilities! Place blocks of different colors in the workspace (default are red and green), and in the terminal, type ``d`` for **detection of the blocks** and hit ``Enter``. Where the blocks were, there should be gray cubes shown on screen. At this point, you can either automatically sort all blocks detected by typing ``o`` (organize) in the terminal and hitting ``Enter`` or you can use the 3D representation of the object in RVIZ to pick and place the block wherever you like on the x and y axis. 

**Options**

.. image:: _static/options.png

**Detection of Blocks**

.. image:: _static/detection.png

**Organize/Sort the red and green blocks**

.. image:: _static/organize.png


