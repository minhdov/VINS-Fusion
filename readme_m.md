https://github.com/HKUST-Aerial-Robotics/VINS-Fusion

source ~/catkin_ws/devel/setup.bash

roslaunch vins vins_rviz.launch

rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_imu_config.yaml 

rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_imu_config.yaml 

rosbag play MH_01_easy.bag

3.1 Monocualr camera + IMU
    roslaunch vins vins_rviz.launch
    rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_mono_imu_config.yaml 
    rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_mono_imu_config.yaml 
    rosbag play MH_01_easy.bag

3.2 Stereo cameras + IMU
    roslaunch vins vins_rviz.launch
    rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_imu_config.yaml 
    rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_imu_config.yaml 
    rosbag play MH_01_easy.bag -r 1.5

3.3 Stereo cameras
    roslaunch vins vins_rviz.launch
    rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_config.yaml 
    rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/euroc/euroc_stereo_config.yaml 
    rosbag play MH_01_easy.bag

***********************************************************
2. VINS-FUSION with realsense camera
source ~/catkin_ws/devel/setup.bash

roslaunch vins vins_rviz.launch
roslaunch realsense2_camera rs_camera_d435i.launch  


rosrun vins vins_node ~/catkin_ws/src/VINS-Fusion/config/realsense_d435i/realsense_stereo_imu_config.yaml 

rosrun loop_fusion loop_fusion_node ~/catkin_ws/src/VINS-Fusion/config/realsense_d435i/realsense_stereo_imu_config.yaml 

*****************************************************************************
Date: 20240319
https://github.com/Junking1/Fast-Planner-for-ubuntu20.04
- Copy Fast-Planner-for-ubuntu20.04 from hesl pc and build on Odroid N2+
- Build status: done
- Run status: 

source devel/setup.bash && roslaunch plan_manage rviz.launch
source devel/setup.bash && roslaunch plan_manage kino_replan.launch
*****************************************************************************
source devel/setup.bash && roslaunch plan_manage rviz.launch
source devel/setup.bash && roslaunch plan_manage topo_replan.launch

