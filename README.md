# Autonomous Navigation Readme File

### Network Configuration
Terminal 1:
```bash
ssh ubuntu@192.168.43.165
password : turtlebot
```

### Bringup Turtlebot
Terminal 2:

```bash
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
### Initiate camera node in the turtlebot
```bash
roslaunch raspicam_node camerav2_1280x960_10fps.launch enable_raw:=true
```
## Apriltag detection code for finding the pose of the simulated Apriltag

```bash
roslaunch turtlebot3_mr apriltag_gazebo.launch 
```

## Execute custom launch file to launch : Move base,slam : gMapping, and Frontier exploration
```bash
roslaunch turtlebot3_mr casey.launch
```

## Running the camera
```bash
rosrun tf static_transform_publisher 0.03 0 0.1 0 0 0 base_link raspicam 100
```

## Detect number of apriltags 
```bash
rosrun turtlebot aprilTags_detection.py
```

## License
[NEU](https://choosealicense.com/licenses/mit/)
