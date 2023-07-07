# Installation Guide of The ROS-NOETIC for UBUNTU 20.04 LTS

The tutorial described bellow can be found on the [ros.org](http://wiki.ros.org/noetic/Installation/Ubuntu). Therefore, I recommend you to enter the site if you look for a more detailed guide installation process.

<center>

![ROS NOETIC IMAGE](images/noetic.png)

</center>

## Installing the ROS noetic Ninjemys

First, you need to setup your computer to accept software from packages.ros.org. So, open a terminal and type the following:


```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

```
 Then, set up your keys:

```
sudo apt install curl # if you haven't already installed curl

curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

```

Now you've gotta make sure that your Debian package is up-to-date by executing the following:

```
sudo apt update

```

Once you've done all the commands above, you can proceed to download the Full version of the distro(recommend), including the simulators. 

```
sudo apt install ros-noetic-desktop-full

```

To automatically source this script every time a new shell is launched, type:

```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

```

Now, to install dependencies for building packages, create and manage your own ROS workspaces, etc, run:


```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

```

Finally, you need to initialize rosdep, so you can use many ROS tools.

```
sudo apt install python3-rosdep

```


```
sudo rosdep init
rosdep update

```