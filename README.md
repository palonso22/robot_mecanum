# robot_mecanum

Learning SLAM with ROS 2 Humble and Gazebo Fortress on a Yahboom ROSMASTER X3 (mecanum) robot.

## Goals

1. Understand the inputs: TF tree, `/scan`, `/odom`, and odometry drift against `/ground_truth/odom`.
2. Better odometry: fuse wheels + IMU with `robot_localization` (EKF).
3. Mapping with `slam_toolbox` (online async), loop closure, saving maps, localization mode.
4. Evaluation: trajectory error (ATE/RPE) and map quality against ground truth.
5. Compare algorithms on the same bags: `slam_toolbox` vs Cartographer.
6. Navigation on a live map with Nav2 and frontier exploration.
7. From scratch: occupancy grid mapping, ICP scan matching, particle filter.

## Setup

The simulator runs in the `yahboom_rosmaster` Docker container (ROS 2 Humble + Gazebo Fortress).
This repo is a colcon workspace: packages go in `src/`.

```bash
source /opt/ros/humble/setup.bash
colcon build
source install/setup.bash
```

## Structure

- `src/` — ROS 2 packages
- `bags/` — recorded runs (not versioned)
- `notes/` — one note per experiment: parameters, results, map images
