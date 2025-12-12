# lidar_slam-with-hybrid-icp


1. 

Overwrite ~/ws_lidar_slam/src/lidar_slam/src/slam_node.cpp with the above file.

Rebuild:

cd ~/ws_lidar_slam
colcon build --symlink-install
source install/setup.bash


Run (play bag first or start node then bag — node waits up to 5s and defaults to CustomMsg):

Terminal A (bag):

source ~/ws_livox/install/setup.bash
ros2 bag play ~/ws_livox/rosbag2/rosbag2_2025_12_03-19_11_40_0.mcap --clock


Terminal B (SLAM):

source ~/ws_lidar_slam/install/setup.bash
ros2 run lidar_slam slam_node --ros-args -p input_topic:=/livox/lidar


After you stop the node, files will be at:

~/ws_lidar_slam/trajectory.tum

~/ws_lidar_slam/trajectory.txt

~/ws_lidar_slam/map_final.pcd
