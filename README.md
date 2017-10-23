# widowx_wiki
readthedocs wiki for the [Trossen Robotics' WidowX](http://www.trossenrobotics.com/widowxrobotarm) arm


# Quickstart
Follow the instructions below after cloning this git repo.

### Clone github repo and install
```
cd ~/widowx_wiki
mkdir widowx_arm
cd widowx_arm/
wstool init src ~/widowx_wiki/widowx_arm/.rosinstall
catkin_make
```

### Launch simulation
```
source devel/setup.bash
roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=false
```

