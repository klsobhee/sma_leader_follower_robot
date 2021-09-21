# sma_leader_follower_robot
Pour lancer la simulation des robots, les étapes suivantes doivent être exécutés:</br>
roscore</br>
rosrun map_server map_server map.yaml</br>
roslaunch amclmulti launch_gazebo.launch(dans le workspace leader_follower_robot)</br>

**Pour une localization aléatoire:**</br>
./n_robot.sh</br>

**Pour une localization spécifique (dans le workspace sma_leader_follower_robot):**</br>
roslaunch amclmulti turtle_multiple.launch multi_robot_name:=tb3_0 x_pos:=2.0 y_pos:=1.0</br>
roslaunch amclmulti turtle_multiple.launch multi_robot_name:=tb3_1 x_pos:=2.0 y_pos:=0.0</br>
roslaunch amclmulti turtle_multiple.launch multi_robot_name:=tb3_2 x_pos:=2.0 y_pos:=-1.0</br>

**Dans un nouveau terminal**:</br>
rosrun amclmulti leader_follower_v2.py tb3_0 tb3_1 leader1</br>

**Dans un nouveau terminal:**</br>
rosrun amclmulti leader_follower_v2.py tb3_1 tb3_2 leader2</br>

**Dans un nouveau terminal:**</br>
ROS_NAMESPACE=tb3_0 rosrun turtlebot3_teleop turtlebot3_teleop_key</br>
