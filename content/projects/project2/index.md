+++
title = "Fast Robots"
description = "This webpage documents the work I've done in ECE4160: Fast Robots. This course focused on systems level design and implementation of dynamic autonomous robots.  We designed a fast autonomous car and explored dynamic behaviors, acting forces, sensors, and reactive control on an embedded processor, as well as the benefit of partial off-board computation, low latency software, and noise tolerant implementation."
weight = 2
[taxonomies]
tags = ["Embedded Software", "PID Controller", "Robotics", "C++", "Microcontroller"]
+++



This course focused on systems level design and implementation of dynamic autonomous robots. We designed a fast autonomous car and explored dynamic behaviors, acting forces, sensors, and reactive control on an embedded processor, as well as the benefit of partial off-board computation, low latency software, and noise tolerant implementation.

To check out more in depth documentation of developing this car, check out my  <a class="external" href="https://pages.github.coecis.cornell.edu/dak267/dak267.github.io/#contact">Fast Robots Webpage</a>

## Highlights from each Lab
In this course, we designed and built a robot car from the ground up, starting with the microcontroller and electronics. The project involved implementing linear and orientation PID controllers, enabling the robot to accurately localize its position and execute path planning. This end-to-end process required integrating hardware, firmware, and software, providing hands-on experience in robotics and control systems.

### Lab 1: Setting up the Artemis
#### Lessons Learned:
- Successfully Installed and Configured Artemis
- Established a communication link between the Artemis (peripherl) and my computer (client)
- Customized UUIDs to prevent conflicts with other devices
Wrote and ran Python scripts to send nd process commans via BLE.
- Devloped methods for real-time and batch data collection, enabling comparison of responsiveness versus accuracy in data sampling. 

### Lab 2: Setting up the IMU
#### Lessons Learned:
- Successfully connected and configured the IMU with Artemis board
- Calculated pitch and roll using acceleration data
- Performed frequency spectrum analysis to determine a 10Hz cutoff for low-pass filtering, reducing noise in accelerometer data
- Derived pitch, roll, and yaw from gyroscope data
- Applied complementary filter to combine gyroscope and acceleromater data to acheive stability and accuracy in data
- Designed a loop to collect and process IMU data efficiently
<img src="/files/project2 media/unfiltered pitch.png" alt="Alt text" style="display:block;">
<figcaption>Unfiltered gyroscope pitch data</figcaption>
<img src="/files/project2 media/filteredpitch.png" alt="Alt text" style="display:block;">
<figcaption>Filtered gyroscope pitch data</figcaption>


### Lab 3: Setting up TOF Sensors
#### Lessons Learned:
- Advanced skills in I2C communication, including dynamic address assignment and multi-sensor integration.
- Improved understanding of the trade-offs between sensor range, accuracy, and performance under real-world constraints.
- Developed a robust framework for processing and transmitting data from multiple sensors in real-time.
<img src="/files/project2 media/comparingrangingtimes.png" alt="Alt text" style="display:block;">
<figcaption>To check which ranging time worked best for my application I kept the sensor statinary relative to a wall and changed the ranging times to see which interval worked best for my application.</figcaption>
<img src="/files/project2 media/measured vs Actual.png" alt="Alt text" style="display:block;">
<figcaption>The measure the repeatability of the sensor I took the average of 1000 readings 5 times at each 10 in distance interval.</figcaption>

### Lab 4: Motors and Open Loop Control
- Gained practical experience with PWM signal generation and motor control.
- Integrated motors, drivers, and battery into the car chassis.
- Recognized the need for closed-loop feedback to improve the car's reliability and consistency.

 <iframe width="450" height="315" src="https://youtube.com/embed/_JmtScWr9uc?si=qRy77x2T7GZyh-j0"></iframe>
<figcaption>Watch the car drive a straight 6ft line after motor calibration.</figcaption>
<iframe width="450" height="315" src="https://youtube.com/embed/XSJ2d5U-zUU?si=BaSZAPno4EvR15RW"></iframe>
<figcaption>Watch the car complete a on axis turn</figcaption>

### Lab 5: Linear PID control and Linear Interpolation
#### Lessons Learned:
- Practical understanding of PID tuning and challenges such as integrator wind-up and derivative kick.
- Importance of efficient data handling and sampling rates for high-speed controllers.
- Effectiveness of interpolation in managing sensor lag during high-speed robot motion.
<img src="/files/project2 media/interpolation.png" alt="Alt text" style="display:block;">
<iframe width="450" height="315" src="https://youtube.com/embed/wGHOYf62dlc?si=ahK3L9ayjIDD_rwC"></iframe>
<figcaption>Linear PID controller using non-interpolated TOF data</figcaption>
<iframe width="450" height="315" src="https://youtube.com/embed/ky4L3CFollU?si=FzGXRpgXw2YhN8RP"></iframe>
<figcaption>Linear PID controller using interpolated TOF data</figcaption>

### Lab 6: Orientation PID controller
#### Lessons Learned:
- Understanding and mitigating gyroscope limitations like drift and maximum rotational velocity is critical for orientation control.
- The importance of real-time data handling and interactive tuning for flexible, responsive robot behavior.
- Combining proportional, integral, and derivative terms effectively to balance stability, accuracy, and speed of response.
{{ youtube(id="U6diJDlVK2Y") }}

### Lab 7: Kalman Filter
#### Lessons Learned:
- The importance of proper initialization and calibration of uncertainty parameters in a Kalman filter to achieve accurate state estimates.
- Effective handling of sensor noise and duplicate data is crucial for maintaining the reliability of the Kalman filter in real-world applications.
- Real-time data processing and adaptive tuning are necessary for the Kalman filter to operate effectively in dynamic environments.
<img src="/files/project2 media/KF_graph.png" alt="Alt text" style="display:block;">

### Lab 8: Stunts!!
#### Objective:
Implement a stunt where the robot would start at a designated point less than 4 meters from a wall, drive forward, and initiate a 180-degree turn when it is within 3 feet from the wall.
<iframe width="450" height="315" src="https://www.youtube.com/embed/5PvHhJGmBcw?si=ZLuehw3d81goYAGe"></iframe>
{{ youtube(id="1hhHzvJ0WBs") }}

### Lab 9: Mapping
#### Objective: 
To collect accurate distance readings from the TOF (Time-of-Flight) sensor at multiple orientations around the robot to build a map of its environment.

#### Method: 
The robot was turned in 18-degree increments to collect TOF readings at 20 different orientations. At each orientation, the robot stopped to take the average of 10 TOF readings.

<iframe width="450" height="315" src="https://youtube.com/embed/H_JDipdOXG0?si=NB-rcMWuIBvuYlqt"></iframe>
 <img src="/files/project2 media/Data Collection.png" alt="Alt text" style="display:block;">
 <figcaption>Data Collected</figcaption>
  <img src="/files/project2 media/5-3.png" alt="Alt text" style="display:block;">
 <figcaption>Data points collected in the polar plane</figcaption>
  <img src="/files/project2 media/polar5-3.png" alt="Alt text" style="display:block;">
 <figcaption>Data points collected in the global frame</figcaption>
   <img src="/files/project2 media/Globals with lines.png" alt="Alt text" style="display:block;">
 <figcaption>Data points collected in multiple locations in the map combined in the global frame</figcaption>

### Lab 10: Grid Localization using Bayes Filter
#### Objective: 
To implement a Bayes Filter for grid localization, enabling the robot to estimate its position in the map based on sensor measurements, control inputs, and a belief of its location.
<iframe width="450" height="315" src="https://www.youtube.com/embed/tr-1j5KCegw?si=QkvnsaHRJjjd12RU"></iframe>
 <figcaption>Here are videos of the robot’s localization with and without the Bayes Filter. In the first video the odometry model is plotted in red and the actual trajectory of the robot is plotted in green. From the video we can see that the odometry model is really bad at predicting the robots position.</figcaption>
 <iframe width="450" height="315" src="https://www.youtube.com/embed/VDPltPzvhHM?si=Yai2VqkXf_Md6EH7"></iframe>
 <figcaption>The second video shows how localization with a Bayes Filter produces much better estimates of the robot’s trajectory. Here again the odometry model is plotted in red and the actual trajectory is plotted in green. The estimated trajectory using the Bayes filter is plotted in blue, and is much better at predicting the robots trajectory. The Bayes Filter seems to perform better when the robot is near walls, most likely due to the sensors being more accurate at sensing closer distances.</figcaption>

### Lab 11: Localization on The Real Robot
#### Objective: 
 Perform localization using the Bayes Filter on the actual robot without relying on the prediction step based on an odometry model due to its inaccuracies. The focus was entirely on the update step, which utilizes a 360-degree scan from the ToF sensor to refine the robot’s position estimate.
<iframe width="450" height="315" src="https://youtube.com/embed/wHQxoGKdlz8?si=8wD2iKQ5g2n4YLxl"></iframe>
<figcaption>Video of the robot performing the observation loop</figcaption>
 <img src="/files/project2 media/pt5-3.png" alt="Alt text" style="display:block;">
 <figcaption>Results of the localization results (blue points) taken in four points in the map (green points).</figcaption>

 ### Lab 12: Path Planning
 #### Objective: 
Navigate the robot through a set of waypoints in the map as quickly and accurately as possible using previous lab implementations of localization and orientation control.

{{ youtube(id="jDAT1IzhXlI") }}
 <figcaption>Shows the robot navigating through waypoints and semi-successfully localizing and moving throught the map.</figcaption>





 