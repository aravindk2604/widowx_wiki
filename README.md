# widowx_wiki
readthedocs wiki for the Trossen Robotics' WidowX arm

# Quickstart

### Clone github repo and install
```
mkdir ~/widowx_arm
cd ~/widowx_arm/
wstool init src .rosinstall
catkin_make
```

### Launch simulation
```
source devel/setup.bash
roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=false
```

