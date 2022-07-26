# InstallingAndOperating-ArmPackages-on-ROS

After installing ROS and all its dependencies for building packages and initializing rosdep which we just did in the previous repository (Installing ROS On Ubuntu_20.04) 

We have to write a few commands in the terminl to install these packages 

### 1- installing catkin 

First we have to install catkin to give us the ability to create a workspace 

```sudo apt-get install ros-noetic-catkin```

### 2- Creating a workpace 

Then we will create the workspace and give it the name ( catkin_ws ) you can change it as you like becuase it just the name of the workspace WS

```mkdir -p ~/catkin_ws/src```

we will create a folder named catkin_ws and put src into this folder

```cd ~/catkin_ws/```

Now we will install the packages into this folder 

```catkin_make```

This command will open src folder 

```cd ~/catkin_ws/src```

After this the next command will give us access to the packages of the robot arm of Smart Methods and install all packages 

```git clone https://github.com/smart-methods/arduino_robot_arm.git ```

Now we will write this command to open catkin folder 

```cd ~/catkin_ws```

### 3- installing all dependencies for the arm packages 

1- ```rosdep install --from-paths src --ignore-src -r -y```

2- ```sudo apt-get install ros-kinetic-moveit```

3- ```sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui```

4- ```sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher```

5- ```sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control```

### 4- Last step is to add the following line at the end of the (bashrc) file
(source /home/#### YOUR SYSTEM NAME ####/catkin_ws/devel/setup.bash)

To put the source of the file (setup.bash) into the file (bashrc)

by writing this command to open bashrc file 

```sudo nano ~/.bashrc```

And copy the line but be careful to put your system name and go to down below the file and copy the line with your SYSTEM NAME

then press (Ctrl + O)  to write out 
and 
then press (Ctrl + x) to get out 

Now write this command to update the source of the file (bashrc)

```source ~/.bashrc```

Then write this command to launch RVis program

```roslaunch robot_arm_pkg check_motors.launch```

### 5- The result after launching RViz
