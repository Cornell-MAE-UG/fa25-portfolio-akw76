---
layout: project
title: Custom GoPro Gimbal
description: Advanced CAD Project
technologies: SolidWorks, 3D Printing and Prototyping
image: /assets/images/Gimbal 9-28 4.PNG
---

Cornell University Unmanned Air Systems (CUAir) is a student-run engineering project team at Cornell University focused on developing a ten-foot wide autonomous unmanned aircraft for the AUVSI SUAS competition. 

As part of the Structures and Payloads subteam, I am responsible for designing, fabricating, and testing the gimbal that will mount and rotate our GoPro. For our competition, the aircraft uses a GoPro to take pictures of the ground beneath the plane to look for targets to drop a payload (water bottles). The gimbal is necessary so that no matter how the fuselage is oriented during flight, the GoPro will always be able to point directly downwards. 

The gimbal I designed is mounted on the underside of the fuselage. It has a cage which houses the GoPro and also acts as a mount for the inertial measurement device (IMU). That cage can be rotated 100° in roll on a bearing and by a servo I selected which meets the torque requirements I calculated. That servo and bearing is mounted on another square that can be rotated 100° in pitch by a second servo. This design weighs 299 grams, which is 60% lighter than designs from past years (750g). It also requires 55% less torque (0.00107 N-m vs 0.0025 N-m) by minimizing the Moment of Inertia about each rotating axis (roll and pitch). 

Currently, I have 3D printed many iterations and have started the testing phase. I am working with our electrical subteam to test the servos in combination with the imu to ensure functionality. I’m also doing strength validation on the design on a test stand by simulating the forces the gimbal would experience during flight. I expect a final iteration to be wrapped up by the end of the semester. 

![CAD Image]({{ "assets/images/Gimbal 9-28 1.PNG" | relative_url }}){: width="600px" }
![CAD Image]({{ "assets/images/Just Cage.PNG" | relative_url }}){: width="600px" }

