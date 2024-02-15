
# SLAM Assignment
The Repo containes the results and explanantion of the 3D SLAM assignment.

# Algorithm Details <br>
<h3>Algorithm Name</h3>RTAB Map ( ROS 2 Version)

## Algorithm installation
`sudo apt install ros-humble-rtabmap*`

to run the algorithm with icpodometry and stereo camera input:<br>
`ros2 launch rtabmap_launch rtabmap.launch.py stereo:=true left_image_topic:=/hawk_0_left_rgb_image right_image_topic:=/hawk_0_right_rgb_image  left_camera_info_topic:=/hawk_0_left_rgb_camera_info right_camera_info_topic:=/hawk_0_right_rgb_camera_info rtabmap_args:="-d" subscribe_scan_cloud:=True scan_cloud_topic:=/pandar_xt_32_0_lidar icp_odometry:=true approx_sync:=true
`

To play the rosbag file:<br>
`ros2 bag play ../r2b_lounge --qos-profile-overrides-path reliability_override.yaml  -r 0.25
`
<br>An additional QoS profile is provided in playing the bag filr to solve the QoS issue of the original bag file.
<h3>Dataset Used </h3>The r2b dataset 2023 is a collection of sequences stored in rosbags, a ROS 2 native format used for message data including time synchronized sensor captures from a robot. The data is collected from an Nvidia Iassac Simulator.

Link : [r2b dataset 2023](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/isaac/resources/r2bdataset2023)

# Algorithm Explanation <br>
A short decription about the algorithm and its working is added in the documentation folder.
Link: Link : [Documentation](docmentation/RTAB_MAP.pdf)


# Algorithm Results <br>
![Result IMage](data/Screenshot%20from%202024-02-14%2018-54-25.png)


# Algorithm Result Video <br>
[![Video](https://img.youtube.com/vi/Or3I5H5vSzQ/0.jpg)](https://www.youtube.com/watch?v=Or3I5H5vSzQ)
#
### Issues faced <br>
There were not enough ROS2 datasets with 3d Lidar and Stero camera. ( Either too large to download an process or only ROS 1 version is available)
