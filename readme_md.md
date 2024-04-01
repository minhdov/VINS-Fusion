
* Reference: https://github.com/HKUST-Aerial-Robotics/VINS-Fusion

* Dataset: cd /media/do/data/workspace/dataset/project/AeroMaze/slam
* Run node: cd /home/do/catkin_ws

1. Stereo Camera and IMU

source ~/catkin_ws/devel/setup.bash
roslaunch vins vins_rviz.launch
rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_imu_config.yaml 
rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_imu_config.yaml 
rosbag play MH_01_easy.bag

***********************************************************
2. VINS-FUSION with realsense camera

source ~/catkin_ws/devel/setup.bash
roslaunch vins vins_rviz.launch
roslaunch realsense2_camera rs_camera_d435i.launch  
rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/realsense_d435i/realsense_stereo_imu_config.yaml 
rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/realsense_d435i/euroc_stereo_imu_config.yaml 


***********************************************************
Build planning and navigation
  source devel/setup.bash && roslaunch plan_manage rviz.launch
  source devel/setup.bash && roslaunch plan_manage kino_replan.launch
  ***********************************************************
  source devel/setup.bash && roslaunch plan_manage rviz.launch
  source devel/setup.bash && roslaunch plan_manage topo_replan.launch

***********************************************************
20240320: Combine VIN-Fusion and Fast planner
***********************************************************
20240401
Build vins-fusion on Jetson Xavier NX

Reference:
https://github.com/zinuok/Xavier_NX#1-opencv-ver-341-install
https://stackoverflow.com/questions/37274190/how-to-link-opencv-to-ros-indigo-catkin-with-cmake-ubuntu-14-04
- Fix opencv problem on jetson
https://blog.csdn.net/woodgril/article/details/109155073