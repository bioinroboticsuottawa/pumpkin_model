Dr. Robot Hawk Robot (A.K.A Pumpkin) SolidWorks and ROS URDF description
==============================================================

This repository contains all SolidWorks part files and one assembly file (pumpkin) to generate URDF and ROS files using [this plugin](http://wiki.ros.org/sw_urdf_exporter).

The folder pumpkin_description already have one working URDF and ROS files ready to launch.

We used Windows 7 64bit with SolidWorks 2012 64bit as sugested in plugin page.

Joint Limits
------------

You need to add joint limits for `roslaunch pumpkin_description display.launch` and safety\_controller for moveit\_plugin

    <limit
        effort="30"
        velocity="1.0"
        lower="-2"
        upper="2" />
    <safety_controller
        k_velocity="10"
        k_position="15"
        soft_lower_limit="-1.9"
        soft_upper_limit="1.9" />

To remove `[ WARN]: The root link map has an inertia specified in the URDF, but KDL does not support a root link with an inertia.  As a workaround, you can add an extra dummy link to your URDF.` when launch moveit just remove link map inertia tag
