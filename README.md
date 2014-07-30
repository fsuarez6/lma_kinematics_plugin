lma_kinematics_plugin
=====================

ROS packages developed by the [Group of Robots and Intelligent Machines](http://www.romin.upm.es/) from the [Universidad Politécnica de Madrid](http://www.upm.es/internacional). This group is part of the [Centre for Automation and Robotics](http://www.car.upm-csic.es/) (CAR UPM-CSIC). On going development continues in the hydro-devel branch.

**Maintainer:** Francisco Suárez Ruiz, [http://www.romin.upm.es/fsuarez/](http://www.romin.upm.es/fsuarez/)

### Documentation

  * See the installation instructions below.
  * This repository.
  * Throughout the various files in the packages.
  * For questions, please use [http://answers.ros.org](http://answers.ros.org)

## Installation

### Repository Installation

Go to your ROS working directory. e.g.
```
cd ~/catkin_ws/src
``` 
Clone the repository
```
git clone https://github.com/fsuarez6/lma_kinematics_plugin.git
``` 
Install any missing dependencies using rosdep:
```
rosdep update
rosdep install --from-paths . --ignore-src --rosdistro hydro
``` 
Now compile your ROS workspace. e.g.
```
cd ~/catkin_ws && catkin_make
``` 

## Changelog

### 0.1.0 (2014-07-28)
* Initial Release
