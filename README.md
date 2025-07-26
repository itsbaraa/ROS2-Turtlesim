# ROS2 Introduction
This repo is an introduction to ROS2 using trutlesim, a lightweight simulator for beginners to learn how to use ROS2.
  
Before we get started we need to make sure that ROS2 is properly installed, follow the official [docs](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html) to install ROS2.

# Installing Turtlesim
Now that we have ROS2 installed, let's install turtlesim using the following command: 
```
sudo apt install ros-humble-turtlesim
```

To verify that turtlesim was installed properly run the following command: 
```
ros2 pkg executables turtlesim
```
  
# Starting Turtlesim
Use the following command on a new terminal window to start a new turtlesim node:
```
ros2 run turtlesim turtlesim_node
```
Now a window with a turtle in the middle will appear, you can also see information from this node in the terminal like the name and coordinates of the turtle.
  
<img width="486" height="524" alt="image" src="https://github.com/user-attachments/assets/c90ae512-a79c-4432-a613-7e7957fa83e1" />

# Controlling The Turtle
Use the following command on a new terminal window to create a new node that controls the turtle from the first node. 
```
ros2 run turtlesim turtle_teleop_key
```
Now you can use the Arrow keys to move the turtle around.
  
<img width="488" height="521" alt="image" src="https://github.com/user-attachments/assets/44b89c2d-c850-4c0c-84c5-e83d13d20f1d" />
  
# Installing and Using rqt
rqt is a GUI (Graphical User Interface) for ROS2.
Run the following command to install rqt:
```
sudo apt install '~nros-humble-rqt*'
```
After installing rqt run:
```
rqt
```
Then navigate to `Plugins > Services > Service Caller`.
  
From the services dropdown menu you can try to use `/spawn`, it's going to spawn a new turtle to the turtlesim window.
  
<img width="654" height="288" alt="image" src="https://github.com/user-attachments/assets/44da5268-b235-4b64-8a35-670b40cded05" />
  
> Note: You cannot spawn 2 turtles with the same name. 
   
You can also use `/kill` service to remove a turtle from the turtlesim window using the turtle's name.

You can use `/set_pen` to modify the color of the line drawn under the turtle when it moves.

To control your new turtle you can use the following command on a new terminal:
  
```
ros2 run turtlesim turtle_teleop_key --ros-args --remap turtle1/cmd_vel:=turtle2/cmd_vel
```

Replace `turtle2` in the command above with your turtle's name.

<img width="1892" height="908" alt="image" src="https://github.com/user-attachments/assets/b7e355cf-ef47-4e92-b5a4-0c198752e387" />



