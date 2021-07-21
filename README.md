# Multi_Agent_System 
**Spanning multiple robots in the environment**    
I have spawned multiple turtlebots robots in ROS in a given world. Spawning of world
requires you to know the exact namespace
Once done we can create a chain of multiple turtlebot to import just by modifying the
launch file by changing the argument of the namespace..In our case we have implemented
3 turtlebot for now.For the world file we have used house .world.After implementing the
world looks as follows.      
**Mapping for multiple robots**           
In our case we have used gmapping as it is the most widely used pkg,We have compiled the
yaml file into the launch inorder to simplify things.Gmapping uses base_footprint , odom
and map nodes off an robots to map the surrounding so we need to modify those
parameter based upon the namespaces we provided in the above mentioned launch file.
An examples a single robot launch file is provided below    
**Combining Map from multiple robots**
Here we used an open source package known as multi_robot_merge. Source: git
https://github.com/hrnr/m-explore.git (branch: melodic-devel).          
**Giving motion to each robot**    
For navigation in a tough environment we may teleop operator with a single namespace in
order to move across the house.
Below is the command line argument for the same.
rosrun teleop_twist_keyboard teleop_twist_keyboard.py /cmd_vel:=/tb3_0/cmd_vel
Below contains the screen of the same working while mapping a house .      
