# Plume simulator

This repository contains ROS nodes and messages necessary to simulate a turbulent
plume, which is an implementation of the algorithm described in [1]. This repository
is complementary to the [Unmanned Underwater Vehicle Simulator (UUV Simulator)](https://github.com/uuvsimulator/uuv_simulator),
an open-source project extending the simulation capabilities of the robotics
simulator Gazebo to underwater vehicles and environments. For installation and
usage instructions, please refer to the [documentation pages](https://uuvsimulator.github.io/).

![Visualization in RViz](plume.png)

[[1] Yu Tian and Aiqun Zhang, "Simulation environment and guidance system for
    AUV tracing chemical plume in 3-dimensions," 2010 2nd International
    Asia Conference on Informatics in Control, Automation and Robotics
    (CAR 2010), Mar. 2010.](http://ieeexplore.ieee.org/document/5456812/)

## Purpose of the project

This software is a research prototype, originally developed for the EU ECSEL
Project 662107 [SWARMs](http://swarms.eu/).

The software is not ready for production use. However, the license conditions of the
applicable Open Source licenses allow you to adapt the software to your needs.
Before using it in a safety relevant setting, make sure that the software
fulfills your requirements and adjust it according to any applicable safety
standards (e.g. ISO 26262).

## Requirements

To simulate the plume, please refer to the [UUV Simulator](https://github.com/uuvsimulator/uuv_simulator)
repository and follow the installation instructions of the package. Then you can clone
this package in the `src` folder of you catkin workspace

```
cd ~/catkin_ws/src
git clone https://github.com/uuvsimulator/uuv_plume_simulator.git
```

and then build your catkin workspace

```bash
cd ~/catkin_ws
catkin_make # or <catkin build>, if you are using catkin_tools
```

## Example of usage

Once both the [UUV Simulator](https://github.com/uuvsimulator/uuv_simulator) and
this plume simulator package are installed, one demonstration can be run to
visualize the plume particles in RViz. To start it, run

```
roslaunch uuv_plume_simulator start_plume_example.launch
```

To start an example of a turbulent plume model, run the script

```
rosrun uuv_plume_simulator set_demo_turbulent_plume
```

If no current is active in the Gazebo world, the particles will accumulate
around the plume source. To start a current velocity model, run the script

```
rosrun uuv_plume_simulator set_current_vel
```

## License

UUV Simulator is open-sourced under the Apache-2.0 license. See the
[LICENSE](LICENSE) file for details.