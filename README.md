# ros-kinetic-roslaunch-patch
This patch backports an update to the roslaunch API from ROS Lunar to ROS Kinetic to allow passing arguments. Specifically, it backports this [commit](https://github.com/ros/ros_comm/commit/9fcf216ac652ce19428bde0507c238aff3c49615) from this [pull request](https://github.com/ros/ros_comm/pull/1115). The only affected file is /opt/ros/kinetic/lib/python2.7/dist-packages/roslaunch/config.py. A backup file is created as /opt/ros/kinetic/lib/python2.7/dist-packages/roslaunch/config.py.original and it is restored when the package is uninstalled. If ros-kinetic-roslaunch were to receive an update, it should update this backup file directly instead of overwriting this patch.

## Installation
Note that you can delete the ros-kinetic-roslaunch-patch folder after installation, as it is not needed afterwards. Alternatively, clone it while you are in /tmp.

To install, run the following commands:
```sh
git clone https://github.com/stateSpaceRobotics/ros-kinetic-roslaunch-patch.git
cd ros-kinetic-roslaunch-patch
sudo dpkg -i ros-kinetic-roslaunch-patched_1.0.0_amd64.deb
```

## Uninstallation
To uninstall, simply run:
```sh
sudo dpkg --remove ros-kinetic-roslaunch-patched_1.0.0_amd64.deb
```
