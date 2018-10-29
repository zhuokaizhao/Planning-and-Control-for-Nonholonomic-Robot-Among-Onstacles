Planning and Control for Nonholonomic Car-like Robot Among Onstacles
========================================================================================
Contributers: Zhuokai Zhao, Mengdi Xu, Changxin Yan
.. begin_brief_description
The project proposes a modified RRT*-based trajectory planning algorithm with customized heuristic function. A feedback linearization controller is proposed to ensure EduMIP’s accurate trajectory tracking. Experiments have been performed in both MATLAB and ROS Gazebo simulation environment.

.. contents:: Contents
   :local:
   :backlinks: none


Matlab (folder)
----------------------------------------------------------------------------------------
.. begin_detailed_description	
Contains all the matlab codes for planning and simualtion in Matlab.

C_RRTStar_Final.m 

Reads an image type map (Images/Simple_Map.png), does the planning on this map and outputs a trajectory mat file in the following format:
[time; desired_x; desired_y; desired_velocity_x; desired_velocity_y; desired_acceleration_x; desired_acceleration; desired_theta;]

trajectory_tracking_with_video.m and trajectory_tracking_without_video.m

Simulates the trajectory tracking. Both files read the trajectory mat file (final_trajectory.m) generated previously by C_RRTStar_Final.m. The trajectory_tracking_with_video.m outputs a annimation of the whole tracking process and takes more time to run. The trajectory_tracking_without_video.m outputs basic inputs and tracking path result.
		

ROS Gazebo Simulation (package folder)
----------------------------------------------------------------------------------------
.. begin_detailed_description
This package reads the predesighed trajectory in a .txt file and simulates the trajectory tracking.

On Debian/Ubuntu, first you need to set_up_Gazebo_environment_

.. _set_up_Gazebo_environment: http://gazebosim.org/tutorials?tut=build_world

To launch the simulation, run
.. code-block:: bash
	
	$ roslaunch robot gazebo_launch.launch

To start the simulation, run
.. code-block:: bash

	$ roslaunch robot trajectory_tracking.launch

To visulize the odometry path of the robot in RVIZ
.. code-block:: bash

	$roslaunch robot rviz_launch.launch


Report (folder)
----------------------------------------------------------------------------------------
.. begin_detailed_description
PDF version of the report which includes all the details about the algorithm and code.


Result
----------------------------------------------------------------------------------------
The planning result from MATLAB with the given map (Images/Simple_Map.png) should look like
.. image:: https://github.com/zhuokaizhao/Planning-and-Control-for-Nonholonomic-Robot-Among-Onstacles/master/Images/final_trajectory.jpg
   :alt: Screenshot
   :align: center

.. image:: https://github.com/zhuokaizhao/Planning-and-Control-for-Nonholonomic-Robot-Among-Onstacles/master/Images/final_trajectory_with_quiver.jpg
   :alt: Screenshot
   :align: center

The Gazebo simulation video can be found at link_

.. _link: https://www.youtube.com/watch?v=cwlF7IM-nAs



