# Neobotix-Simulation

## Pre Install
```bash
sudo apt-get install -y ros-$ROS_DISTRO-ros-controllers \
ros-$ROS_DISTRO-gazebo-ros-control ros-$ROS_DISTRO-navigation \
ros-$ROS_DISTRO-eband-local-planner ros-$ROS_DISTRO-teb-local-planner \
ros-$ROS_DISTRO-dwa-local-planner ros-$ROS_DISTRO-openslam-gmapping \
ros-$ROS_DISTRO-amcl ros-$ROS_DISTRO-joy ros-$ROS_DISTRO-teleop-twist-keyboard \
ros-$ROS_DISTRO-tf2-sensor-msgs
```

## Build workspace
```bash
cd ~
git clone 
cd ~/Neobotix-Simulation/neobotix_ws
wstool update -t src
catkin_make
```

## Sourcing the workspace
```bash
echo "source ~/Neobotix-Simulation/neobotix_ws/devel/setup.bash" >> ~/.bashrc
```


Add path to custom gazebo models into .bashrc

    echo "export GAZEBO_MODEL_PATH=~/Neobotix-Simulation/neobotix_ws/src/neo_simulation/models:$GAZEBO_MODEL_PATH" >> ~/.bashrc

Add locale path into .bashrc

    echo "export LC_NUMERIC="en_US.UTF-8" " >> ~/.bashrc

Additional step to melodic

    cd ~/.ignition/fuel
    gedit config.yaml 

Change

    url: https://api.ignitionfuel.org

To

    url: https://api.ignitionrobotics.org

roslaunch neo_simulation simulation.launch


    export MAP_NAME="neo_workshop"
    roslaunch neo_simulation mmo_500_autonomous_navigation.launch

roslaunch neo_simulation mmo_500_autonomous_navigation.launch
