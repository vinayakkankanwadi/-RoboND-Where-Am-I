[![Udacity - Robotics NanoDegree Program](https://s3-us-west-1.amazonaws.com/udacity-robotics/Extra+Images/RoboND_flag.png)](https://www.udacity.com/robotics)

# RoboND-Where-Am-I
The **Go-Chase-It** is part of RoboND ROS Essentials. The purpose is to Design and build a mobile robot, and house it in a world.
Then, program a robot with C++ nodes in ROS to chase white colored ball.

# Result
<img src="images/result.gif"/>

### Directory Structure
```
.RoboND-Where-Am-I
├── ball_chaser
│   ├── CMakeLists.txt
│   ├── launch
│   │   └── ball_chaser.launch
│   ├── package.xml
│   ├── src
│   │   ├── drive_bot.cpp
│   │   └── process_image.cpp
│   └── srv
│       └── DriveToTarget.srv
├── images
│   ├── output.png
│   └── result.gif
├── model
│   ├── Building
│   │   ├── model.config
│   │   └── model.sdf
│   ├── my_ball
│   │   ├── model.config
│   │   └── model.sdf
│   └── table
│       ├── model-1_2.sdf
│       ├── model-1_3.sdf
│       ├── model-1_4.sdf
│       ├── model.config
│       └── model.sdf
├── my_robot
│   ├── CMakeLists.txt
│   ├── config
│   │   ├── base_local_planner_params.yaml
│   │   ├── costmap_common_params.yaml
│   │   ├── global_costmap_params.yaml
│   │   └── local_costmap_params.yaml
│   ├── launch
│   │   ├── amcl.launch
│   │   ├── robot_description.launch
│   │   └── world.launch
│   ├── maps
│   │   ├── map.pgm
│   │   └── map.yaml
│   ├── meshes
│   │   ├── hokuyo.dae
│   │   ├── realsense.dae
│   │   └── wheel.dae
│   ├── package.xml
│   ├── rviz
│   │   └── my_robot.rviz
│   ├── urdf
│   │   ├── my_robot.gazebo
│   │   └── my_robot.xacro
│   └── worlds
│       ├── empty.world
│       └── my_world.world
├── README.md
└── teleop_twist_keyboard
    ├── CHANGELOG.rst
    ├── CMakeLists.txt
    ├── package.xml
    ├── README.md
    └── teleop_twist_keyboard.py
    
```
### Steps to launch the simulation

#### Step 1 Update and upgrade the Workspace image
```sh
$ sudo apt-get update
$ sudo apt-get upgrade -y
```

#### Step 2 Create the catkin workspace
```sh
$ mkdir -p $HOME/catkin_ws/src
$ cd $HOME/catkin_ws/src
$ catkin_init_workspace
$ git clone https://github.com/vinayakkankanwadi/RoboND-Go-Chase-It.git
```

#### Step 3 add Model Library and custom models
```sh
$ cd $HOME
$ git clone https://github.com/osrf/gazebo_models
$ export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:$HOME/gazebo_models:$HOME/catkin_ws/src/RoboND-Go-Chase-It/model

```

#### Step 4 Compile the code
```sh
$ cd $HOME/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

#### Step 5 Run the Simulation 
##### in terminal 1:

```sh
$ source $HOME/catkin_ws/devel/setup.bash
$ roslaunch my_robot world.launch

```

##### in terminal 2:

```sh
$ source $HOME/catkin_ws/devel/setup.bash
$ roslaunch ball_chaser ball_chaser.launch

```

##### in Gazebo:

move the white ball in front of the robot and have fun.


# License
MIT license
