# bash-commands

Start connection - ros2 launch mavros apm.launch fcu_url:=///dev/ttyUSB0:57600 

Set mode - ros2 service call /mavros/set_mode mavros_msgs/srv/SetMode "{base_mode: 0, custom_mode: 'STABILIZE'}"

Arm - ros2 service call /mavros/cmd/arming mavros_msgs/srv/CommandBool "{value: true}" 

Temporary sensor publish - 

ros2 topic pub /mavros/obstacle/scan sensor_msgs/msg/LaserScan "{
  header: { frame_id: 'laser' },
  angle_min: 0.0,
  angle_max: 0.0,
  angle_increment: 0.0,
  time_increment: 0.0,
  scan_time: 0.0,
  range_min: 0.1,
  range_max: 10.0,
  ranges: [10.0],
  intensities: []
}"

Recieve sensor data - ros2 topic echo /mavros/obstacle/scan

-----------------------------------------

Mavros, Mavros-extras and Mavros-msgs

sudo apt install ros-humble-mavros-extras ros-humble-mavros-msgs
source /opt/ros/humble/setup.bash

-----------------------------------------
