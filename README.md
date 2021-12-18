# Autonomous Exploration and Detection of Apriltags

## Network Configuration
Terminal 1:
```bash
ssh ubuntu@192.168.43.165
password : turtlebot
```

## Bringup Turtlebot
Terminal 2:
```bash
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
## Initiate camera node in the turtlebot
Terminal 3:
```bash
roslaunch raspicam_node camerav2_1280x960_10fps.launch enable_raw:=true
```
## Apriltag detection code for finding the pose of the Apriltag
Terminal 4:
```bash
roslaunch turtlebot3_mr apriltag_gazebo.launch 
```

## Execute custom launch file to launch : Move base,slam : gMapping, and Frontier exploration
Terminal 5:
```bash
roslaunch turtlebot3_mr casey.launch
```

## Start recording the bag.file
Terminal 6:
```bash
rosbag record -a
```

## Running the camera
Terminal 7:
```bash
rosrun tf static_transform_publisher 0.03 0 0.1 0 0 0 base_link raspicam 100
```

## Detect number of Apriltags
Terminal 8:
```bash
rosrun turtlebot aprilTags_detection.py
```
## Finish Trajectory
Terminal 9:
```bash
rosservice call /finish_trajectory 0
```

## Save Map 
Terminal 10:
```bash
rosrun map_server map_saver -f ~/casey_map
```

## License
[NEU](https://brand.northeastern.edu/guide/policies/licensing/)
