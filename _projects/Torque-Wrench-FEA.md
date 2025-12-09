---
layout: project
title: Torque Wrench FEA
description: Doing Ansys FEA on a torque wrench
technologies: Ansys
image: /assets/images/Torque-Wrench-Total-Deformation.png
---

I did FEA on a 600 lbf-in torque wrench that I designed. I worked my classmate Abigail Miller on this project. Here is my analysis. <br> <br> <br>


1. Image(s) of CAD model, showing all key dimensions
![CAD Image]({{ "assets/images/Torque Wrench CAD Drive.png" | relative_url }}){: width="600px" }
![CAD Image]({{ "assets/images/Torque Wrench CAD fillets.png" | relative_url }}){: width="600px" }
![CAD Image]({{ "assets/images/Torque Wrench Cad Length.png" | relative_url }}){: width="600px" }
![CAD Image]({{ "assets/images/Torque Wrench Drive Heigh.png" | relative_url }}){: width="600px" }

2. Describe material used and its relevant mechanical properties. <br>
The material we used for the torque wrench was 7075-T6 Aluminum Alloy. The elastic modulus of this material is around 10,000 ksi. This is significantly less stiff than steel, which allows the torque wrench to reach its required strain of 1.0 mV/V. The tensile strength is 67 ksi and the fatigue strength is 22ksi. This created a strength factor of safety of 6.3 and a fatigue factor of safety of 2.1. The 7075-T6 Aluminum Alloy also has a fracture toughness of 25,000 psi-sqrt(in), which gives a factor of safety for crack growth of 5.9. 

3. Diagram communicating how loads and boundary conditions were applied to your FEM
model. 
![Diagram Image]({{ "assets/images/Torque Wrench Condition Boundaries.png" | relative_url }}){: width="600px" }
![Diagram Image]({{ "assets/images/Torque Wrench Drive BC.png" | relative_url }}){: width="600px" }
There is a fixed boundary condition at the drive. There is a 33.33 lbf load in the x-direction at the end of the handle (18 in. away from the drive) which corresponds to a 600 in-lbf torque at the drive. <br>

4. Normal strain contours (in the strain gauge direction) from FEM <br>
Normal Strain along Y-axis
![Strain Image]({{ "assets/images/Torque Wrench All Strain.png" | relative_url }}){: width="600px" }

5. Contour plot of maximum principal stress from FEM 
![Stress Image]({{ "assets/images/Torque Wrench Principal Stress.png" | relative_url }}){: width="600px" }
![Stress Image]({{ "assets/images/Torque Wrench Principal Stress Drive" | relative_url }}){: width="600px" }

6. Summarize results from FEM calculation showing maximum normal stress (anywhere), load point deflection, strains at the strain gauge locations <br>
![Stress Image]({{ "assets/images/Torque Wrench Normal Stress Drive.png" | relative_url }}){: width="600px" }
![Stress Image]({{ "assets/images/Torque Wrench Normal Stress Node.png" | relative_url }}){: width="600px" }
![Stress Image]({{ "assets/images/Torque-Wrench-Total-Deformation.png" | relative_url }}){: width="600px" }
![Strain Image]({{ "assets/images/Torque Wrench Strain Gauge.png" | relative_url }}){: width="600px" }
The maximum normal stress on the torque wrench in the FEM is 27255 psi. However, this is at a stress concentration at the base of the drive. Along the torque wrench handle, the largest normal stress is 10581 psi. This is very close to our hand calculation, which was 10666.7 psi. 
The load point deflection in the FEM was 0.46186 inches. Our hand calculation load point deflection was 0.3072. These are on the same order of magnitude, but just like in the baseline design, the FEM had a higher deflection due to fillets along the handle in the CAD file. 
The strain at the strain gauge location was 1022.8 microstrain according to Ansys and 1007.4 microstrain according to our hand calculations. This is about a 1.5% percent difference, which is very small. 

7. Torque wrench sensitivity in mV/V using strains from the FEM analysis
    ε<sub>1</sub> = 1022.8 microstrain<br>
    <i>change in gauge resistance</i> = k ε<sub>gauge</sub><br>
    <b>From half-bridge:</b>
    <sup>V<sub>out</sub></sup>/<sub>V<sub>in</sub></sub> = (k / 4)(ε<sub>1</sub> − ε<sub>2</sub>)<br>
    <b>With a gauge factor k = 2:</b>
    <sup>V<sub>out</sub></sup>/<sub>V<sub>in</sub></sub> = (2k / 4)(2ε<sub>1</sub>) = ε<sub>1</sub><br>
    Therefore the torque wrench sensitivity = <b>1.0228 mV/V</b>

8. Strain gauge selected (give type and dimensions). Note that design must physically have enough space to bond the gauges. <br>
The Omega 1-LM11-1.5/350GE strain gauge fits out design. It’s dimensions are 0.35 x 0.17 inches. It is a linear strain gauge measuring strain in one direction, so we can orient it along the handle to measure strain during bending. Also it has a gauge factor of about 2. It’s maximum elongation is 10,000 microstrain, and our torque wrench has a max strain of a little over 1,000 microstrain, so this gauge is appropriate. 