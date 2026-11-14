# ROS learning workspaces

ROS 1 / Catkin learning archive from the original Ubuntu 20.04 + ROS Noetic workstation.

| Directory | Actual contents |
|---|---|
| [robot_project](robot_project/README.md) | Empty Catkin workspace skeleton; no robot package found in src |
| [demo04_ws](demo04_ws/README.md) | Static/dynamic TF, transform chains and turtlesim TF exercises |
| [demo05_ws](demo05_ws/README.md) | URDF/Xacro, RViz, Gazebo model/world and navigation configuration |

Source files, package manifests, launch files, robot descriptions, maps and mesh assets are preserved. Machine-generated build/devel folders, IDE histories, system symlinks and unrelated notebook material are not published. Each workspace remains separate; do not merge their src trees accidentally.

## Rebuild on a compatible ROS 1 machine

```bash
source /opt/ros/noetic/setup.bash
cd demo04_ws                    # or demo05_ws
cd src
catkin_init_workspace          # regenerates system-specific CMakeLists.txt
cd ..
rosdep install --from-paths src --ignore-src -r -y
catkin_make
source devel/setup.bash
```

Inspect launch files before running. Some configurations retain machine-specific paths and refer to externally installed Gazebo models. This archival upload did not re-run simulation, navigation or hardware tests. It is ROS 1, not ROS 2; the separate [SLAM demo](https://github.com/Joel-tao/SLAM) has its own scope.
