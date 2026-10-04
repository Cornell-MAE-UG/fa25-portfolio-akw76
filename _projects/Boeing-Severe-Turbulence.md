---
layout: project
title: Boeing Severe Turbulence Inspection Threshold Project
description: Developing CG acceleration thresholds for critical dynamic loads due to turbulence
technologies: 
image: "/assets/images/FMD-cover.png"
---

    During my internship with Boeing’s Loads and Dynamics group, I worked on a project
for the Dynamic Flight Loads team to reduce unnecessary inspections and aircraft out-
of-service time after pilot-reported severe turbulence on 737 MAX minor models (-7, -9,
-10). I helped develop a method to predict the expected CG response of each airplane
condition to FAA-defined design gusts. By comparing the predicted response to the
aircraft’s actual turbulence response, we could determine whether post-flight inspection
requirements could be waived and the airplane returned to service sooner.

    To ensure full flight-condition coverage, I selected payload configurations with fuel
vectors that covered the minor models’ CG/gross weight envelope. After analyzing
hundreds of fuel vectors, I chose 8–12 per minor model based on real-world frequency
and envelope coverage. For each payload configuration, I defined a “condition” with
three additional parameters: altitude in 5,000-foot increments from 0 to 40,000 feet,
gross weight in 10,000-lb increments along the configuration’s fuel vector, and airspeed
in 40-knot increments from cruise velocity plus one point at maximum operating velocity.
These increments balanced sample size and interpolation accuracy against data
volume and computing cost. In total, each minor model had close to 2,000 conditions.

    Next, I used Boeing’s internal tools and Easy5 models to calculate loads and CG
responses for each condition. I wrote MATLAB scripts to generate input tapes for an
internal tool that models the structural and aeroelastic properties of the 737 MAX, then
used the matrices from those equations of motion to complete the internal Easy5 control
system model. I debugged and adapted the models for this study’s scope, including
separate cases for lateral and vertical gusts as well as discrete and continuous gust
inputs. In addition to airplane response loads, I analyzed eigenvalues and eigenmodes
for the aircraft’s low-frequency bending behavior to verify the model response against
expected structural dynamics. During this analysis I decided that using loads at a 2 Hz
cutoff frequency would preserve rigid-body response while conservatively excluding
dynamic bending effects. The Easy5 outputs of this study included over 600 response
parameters across 250 continuous gust frequencies and 16 discrete gust gradients.

    The final and most challenging part of the project was processing the large volume of
model output data. I wrote MATLAB scripts to convert Easy5 outputs into .mat analysis
tables, then visualized the results to identify trends for deriving an inspection threshold. I verified that CG acceleration was a valid metric for threshold criteria by comparing vertical and lateral gust responses across impact pressures and gross weight bands. I also used convex hull plots and discrete-to-continuous gust response ratios to show that a threshold set at 80% of the CG acceleration from the design continuous gust input would capture all critical load cases across gust types. At the conclusion of the internship, I presented my findings in a TDR to technical fellows and subject matter experts for review and feedback on my processes and design decisions.