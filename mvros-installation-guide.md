# This is a Installation Guide for ROS with MAVROS

MAVROS is a ROS 1 package that enables MAVLink extendable communication between computers running ROS 1 for any MAVLink enabled autopilot, ground station, or peripheral. MAVROS is the "official" supported bridge between ROS 1 and the MAVLink protocol.

A more detailed installation guide can be found on [mavros github repository](https://github.com/mavlink/mavros/blob/master/mavros/README.md#installation)


## Binary Installation (Debian/ Ubuntu)

1. Use apt-get for installation of the noetic-mavros:

    ```
    sudo apt-get install ros-noetic-mavros ros-noetic-mavros-extras ros-noetic-mavros-msgs


    ```
2. Then install GeographicLib (opens new window) datasets by running the install_geographiclib_datasets.sh script:

    ```
    wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh

    sudo bash ./install_geographiclib_datasets.sh   

    ```
## Source Installation

Always run first:

```
sudo apt-get update

```

1. Install ROS Python tools: wstool, rosinstall and catkin_tools, once they'll be used foor installation/building process:

```
    sudo apt install python3-catkin-tools python3-rosinstall-generator python3-osrf-pycommon -y

```

2. If you don't have a catkin workspace located at ~/catkin_ws/, create on by running the following:

    ```
    mkdir -p ~/catkin_ws/src
    cd ~/catkin_ws
    catkin init
    wstool init src

    ```
3. Install MAVLink

    ```
    rosinstall_generator --rosdistro noetic mavlink --deps | tee /tmp/mavros.rosinstall

    ```

4. Install the latest source version of MAVROS:

    ```
    rosinstall_generator --upstream-development mavros --deps | tee -a /tmp/mavros.rosinstall

    ```

5. Update the rosdep and the system:

    ```
    sudo rosdep update

    sudo apt-get update

    ```

6. Create workspace & deps

    ```
    wstool merge -t src /tmp/mavros.rosinstall

    wstool update -t src -j4

    rosdep install --from-paths src --ignore-src -y

    ```
7. Install GeographicLib datasets:


    ```
    sudo ./src/mavros/mavros/scripts/install_geographiclib_datasets.sh

    ```
8. Build source


    ```
    catkin build

    ```

9. Make sure that you use setup.bash or setup.zsh from workspace, or else rosrun can't find nodes from this workspace:


    ```
    source devel/setup.bash

    ```
