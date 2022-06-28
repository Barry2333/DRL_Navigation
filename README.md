# DRL_Navigation

Implementation of DRL robot navigation based on https://github.com/reiniscimurs/DRL-robot-navigation

Experiemnt videos can be view at: https://www.youtube.com/watch?v=HkqUZSsT5a0&t=1s

Clone the repository:
```shell
$ cd ~
### Clone this repo
$ git clone https://github.com/Barry2333/DRL_Navigation
```

Compile the workspace:
```shell
$ cd ~/DRL_Navigation/catkin_ws
### Compile
$ catkin_make_isolated
```

Open a terminal and set up sources:
```shell
export ROS_HOSTNAME=localhost
export ROS_MASTER_URI=http://localhost:11311
export ROS_PORT_SIM=11311
export GAZEBO_RESOURCE_PATH=~/DRL_Navigation/catkin_ws/src/multi_robot_scenario/launch
source ~/.bashrc
cd ~/DRL_Navigation/catkin_ws
source devel_isolated/setup.bash
### Run the training
cd ~/DRL_Navigation/TD3
python3 train.py

### Run the test with my trained models
python3 test_agent.py

### Change the simulation world
cd ~/catkin_ws/src/multi_robot_scenario/launch/empty_world.launch
check the "world_name"
```

To kill the training process:
```shell
$ killall -9 rosout roslaunch rosmaster gzserver nodelet robot_state_publisher gzclient python python3
```

