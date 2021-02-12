# Robotics Technology (254774)
# Assignment-01: Ros Robot Navigation. 

1. Custom environments in Gazebo:
   - floor size at least 500 square meters
   - at least 5 rooms
   - at least 20 furniture items (table, chair, plant pots, etc.)
   - other things as you can imagine
   
2. A mobile robot:
   - Differential drive (or omnidirectional drive-- extra points)
   - about 0.5m (length) x 0.5m (width) x 1.0 (height) (Examples)
   
3. Map from Lidar sensor

4. Autonomous navigation capability

This repository contains a Robot Operating System (ROS) implementation of a skid-steer robot model for uses with the ROS navigation stack.
The model uses the Adaptive Monte Carlo Localisation (AMCL) method for localisation with the Elastic band planner method to navigate to goal locations.

![skid-steer robot model](images/skid-steer-bot.png)

## Prerequisites

1. [Ubuntu (melodic)](http://wiki.ros.org/melodic/Installation/Ubuntu) 

2. Robot Operating System (ROS). can be found [here](http://wiki.ros.org/ROS/Installation).

3. Install ROS nodes required for the local and global planners, amcl, maps and motor control for the navigation stack.

```sh
$ sudo apt-get update
$ sudo apt-get install ros-kinetic-move-base
$ sudo apt-get install ros-kinetic-map-server
$ sudo apt-get install ros-kinetic-amcl
$ sudo apt-get install ros-kinetic-eband-local-planner
$ sudo apt-get install ros-kinetic-global-planner
```

## Installing

Clone this repository in your catkin workspace 'src/' folder.

```sh
$ cd ~/workspace_name/src/
$ git clone https://github.com/Heych88/skid_steer_bot.git
```

Build the project:
```sh
$ cd ~/workspace_name
$ catkin_make
```

The following line can be added to your .bashrc to auto-source all new terminals
```
source ~/workspace_name/devel/setup.bash
```

## Run the Code

In a terminal window, type the following, for diff_robot
```sh
$ cd ~/catkin_ws
$ roslaunch skid_steer_bot udacity_world.launch
```

In a new terminal, run the '' file.
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ roslaunch skid_steer_bot amcl.launch
```

Gazebo and Rviz will load and you should arrive at a result similar to the below.

![Gazebo & RViz with costmap](images/RvizGazebo.png)

###### Testing 

1. In Rviz, click on the 2D Nav Goal in the top menu. 
2. Click on the Rviz map where you want the robot to navigate too. 

You should arrive at a result similar to the below.

![navigation to a goal location](images/nav_goal.png)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
