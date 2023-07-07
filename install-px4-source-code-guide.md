# This is a tutorial to run the Simulation on Gazebo Classic with ROS NOETIC 

## Download and install the PX$ Source Code

1. Run the following to download the and install the PX4 source code without the simulator toolchain:

    ```
    git clone https://github.com/PX4/PX4-Autopilot.git --recursive

    ```
2. Now run the ubuntu.sh to acknowledge any prompts as the script progress:

    ```
    bash ./PX4-Autopilot/Tools/setup/ubuntu.sh --no-sim-tools --no-nuttx

    ```

3. Restart the computer on completion.

4. You may need to install the following additional dependencies:


    ```
    sudo apt-get install protobuf-compiler libeigen3-dev libopencv-dev -y

    ```
5. Now, install the ROS-NOETIC by going to [installation ros-noetic-link](link)


