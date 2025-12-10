---
layout: project
title: Roomba Brush Speed Control Analysis
description: 
technologies: 
image: /assets/images/Speed Control Block Diagram.png
---

This was a group project for my MAE 3260: System Dynamics class. Our team analyzed control systems of a Roomba robotic vacuum. My portion of the project was to investigate the speed control of the brushes on the roomba, and to create a block diagram to describe the control system. <br><br><br><br>

A roomba’s main function is to clean up messes, so arguably its most important component is the speed control of its vacuum brushes. How does it spin its brushes at the right speed to pick up messes? How does it adapt to different amounts of dirt it picks up in different locations? Actually, a Roomba’s brush speed control system is open-loop, meaning there is no feedback control. It does not read the current brush speed and doesn’t use any feedback controller. 

Instead, it uses two sensors to set the brush speed depending on the conditions it is vacuuming in, according to [6]. A piezoelectric sensor on the front end of the bottom of the vacuum detects dirt levels. When bits of dirt, dust, or other debris hit the sensor, the Roomba receives tiny electric impulses and it knows to ramp up its speed. The other sensor in this system is an optical texture sensor. This sensor shines IR light onto the ground, and this helps it detect the surface type. If the Roomba is on carpet, it activates carpet boost to work harder to clean the mess. 

When the microcontroller in the Roomba receives data from the sensors, it uses Pulse-Width Modulation (PWM) to vary the voltage input to the motor for the brushes. This is because microcontrollers can only send a fixed voltage or 0 volts to the motor, so it uses a square wave signal with different lengths of 0V to send different voltages [7]. The exact PWM wavelengths used are dependent on the duty cycle, of which there are three, corresponding to three different voltages and power levels. The highest duty cycle is the carpet boost, when the most voltage is being sent to the motor. The lower duty cycle is the eco cleanup mode, with the least amount of voltage being sent to the motor. Here is an equation for voltage sent by the MCU to the motor drive as a function of time. Vbattery is the fixed voltage that can be sent, and T is the period of the square wave signal. dT is a length of time that changes depending on the duty cycle being used. Figure 2 is a Desmos graph for this function. 

![Image]({{ "assets/images/PWN graph.png" | relative_url }}){: width="600px" }

It’s also important to note that while there are two brushes in the cleanup system, they are both controlled by the same motor. The first brush loosens, lifts, and pulls debris under the Roomba, while the second brush accelerates the debris into the vacuum’s suction channel. The two brushes rotate at the same RPM, but in opposite directions. The speed the motor spins at is slowed by a gearbox to appropriate speeds for the brushes. Unfortunately, data telling us the exact RPM of the motor and brushes during each duty cycle is not publicly available online for us to find. 

One other factor in motor speeds is if there is a jam. If, for some reason, the brushes become obstructed and can no longer rotate, back-emf from the motor stop and this causes a current impulse. If that impulse is detected it tells the microcontroller unit to cut PWM to 0% and stop the cleaning cycle. An error message plays out loud, and a human must clean the brushes before the Roomba can resume cleaning. 

Figure 1 is a block diagram that summarizes the brush speed control system that has been discussed up to this point. 

![Image]({{ "assets/images/Speed Control Block Diagram.png" | relative_url }}){: width="600px" }

