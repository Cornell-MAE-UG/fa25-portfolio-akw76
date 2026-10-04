---
layout: project
title: Custom GoPro Gimbal
description: Advanced CAD Project
technologies: SolidWorks, 3D Printing and Prototyping
image: /assets/images/Gimbal 9-28 4.PNG
---

Cornell University Unmanned Air Systems (CUAir) is a student-run engineering project team at Cornell University focused on developing a fully autonomous VTOL UAS for search and rescue missions. 

As part of the Structures and Payloads subteam, I am responsible for designing, fabricating, and testing the gimbal that will mount and rotate our GoPro. For our competition, the aircraft uses a GoPro to take images and map the ground beneath the plane, which a ML pipeline analyzes for targets in need of rescue supplies. The gimbal is necessary so that during fuselage rolls and pitches, the camera remains stable and oriented directly towards the ground. 

The gimbal I designed is mounted on the underside of the fuselage. The major parts are all designed on SolidWorks and 3D printed using ASA. It has a cage which houses the GoPro and also acts as a mount for the inertial measurement device (IMU). That cage can be rotated 100° in roll on a bearing and by a servo I selected which meets the torque requirements I calculated. That servo and bearing is mounted on another square that can be rotated 100° in pitch by a second servo. This design weighs 210 grams, which is 70% lighter than designs from past years (750g). It also requires 55% less torque (0.00107 N-m vs 0.0025 N-m) by minimizing the Moment of Inertia about each rotating axis (roll and pitch). 

Testing on the gimbal involved verifying stability of images through the required maneauvers. I also used a force probe to apply calculated G-force and drag loads onto the assembled gimbal with a factor of safety of 1.5, which required building a wooden test stand as well. Functionality of the gimbal during the aircraft's mission has been verified through multiple test flights. 

![CAD Image]({{ "assets/images/Gimbal 9-28 1.PNG" | relative_url }}){: width="600px" }
![CAD Image]({{ "assets/images/Just Cage.PNG" | relative_url }}){: width="600px" }

