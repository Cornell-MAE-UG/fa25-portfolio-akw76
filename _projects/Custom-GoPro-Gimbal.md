---
layout: project
title: Custom GoPro Gimbal for UAS
description: Advanced CAD Project
technologies: SolidWorks, 3D Printing and Prototyping
image: /assets/images/Gimbal 9-28 4.PNG
order: 2
---

<div class="project-wide">

<p>
As a member of the <strong>Structures and Payloads</strong> subteam on Cornell University
Unmanned Air Systems (CUAir), I designed, fabricated, and tested the two-axis GoPro gimbal
for our autonomous VTOL aircraft. During competition, the aircraft uses the GoPro to image
the ground and identify targets for a payload airdrop. The gimbal keeps the camera pointed
downward as the aircraft rolls and pitches in flight.
</p>

<p>
My final design weighed <strong>210 g</strong>, compared with approximately
<strong>750 g for the previous design</strong> — a 72% reduction in mass. By reducing
rotating mass and concentrating it near each axis of rotation, I also reduced the calculated
servo torque requirement from <strong>0.0025 N·m to 0.00107 N·m</strong>.
</p>

<h3>Mechanical Design</h3>

<p>
I designed a nested two-axis mechanism with <strong>100° of total travel in both roll and
pitch</strong> (±50° about each axis). The inner cage houses the GoPro and IMU and rotates
about the roll axis. That assembly is supported by a bearing on one side and driven by an
<strong>HS-5070MH digital micro servo</strong> on the other. The outer frame uses the same
servo-and-bearing arrangement to provide pitch rotation.
</p>

<p>
A major design objective was minimizing moment of inertia about both axes. I positioned
the center of mass of each rotating assembly as close to its rotation axis as possible,
kept components near the axes, and removed unnecessary material. I also replaced the
previous aluminum cage and gimbal arms with <strong>six custom ASA 3D-printed components</strong>,
using off-the-shelf bearings and hardware where appropriate.
</p>

<div class="project-image-row">

  <figure>
    <img
      src="{{ '/assets/images/gimbal-cad-assembly.png' | relative_url }}"
      alt="CAD assembly of the CUAir two-axis GoPro gimbal">

    <figcaption>
      <strong>Final gimbal CAD assembly.</strong>
      The nested roll and pitch frames place the GoPro and supporting hardware close to
      their respective rotation axes to reduce mass and rotational inertia.
    </figcaption>
  </figure>

  <figure>
    <img
      src="{{ '/assets/images/gimbal-installed.png' | relative_url }}"
      alt="CUAir GoPro gimbal installed beneath the aircraft fuselage">

    <figcaption>
      <strong>Completed gimbal installed beneath the aircraft.</strong>
      The final 210 g assembly packages the camera, IMU, two servos, bearings, and mounting
      structure within a compact underside installation.
    </figcaption>
  </figure>

</div>

<h3>Servo Selection and Load Validation</h3>

<p>
I estimated the required actuator torque from the rotational inertia of the moving
components and the required gimbal acceleration, then selected the HS-5070MH servos with
approximately <strong>3–4× the calculated torque requirement</strong>. This provided
substantial operating margin even as servo performance degraded with use.
</p>

<p>
Rather than relying on FEA for the printed ASA structure, I validated the assembly
physically. I built a test stand and used a <strong>force probe to apply hand-calculated
loads</strong> to the mechanism while operating the servos, verifying that the gimbal
could move correctly under the expected loading.
</p>

<h3>Iterative Prototyping</h3>

<p>
I 3D printed and assembled multiple iterations before reaching the final design. Between
prototypes, I reduced wall thicknesses, added material-removal cutouts, improved bearing
and fastener fits, refined tolerances for smoother rotation, and redesigned the camera
retention geometry to make the GoPro easier to access.
</p>

<p>
The final design allows the GoPro to be removed and reinstalled in
<strong>under 30 seconds</strong>, simplifying charging, data retrieval, and maintenance
between flights.
</p>

<figure style="margin: 32px auto; max-width: 900px;">

  <video
    controls
    playsinline
    preload="metadata"
    style="width: 100%; height: auto; display: block;">
    <source
      src="{{ '/assets/GimbalTesting.mp4' | relative_url }}"
      type="video/mp4">
    Your browser does not support the video tag.
  </video>

  <figcaption>
    <strong>Prototype controls-integration test.</strong>
    An early gimbal prototype mounted on the test stand I built. The IMU detects changes in
    orientation and the servos compensate in roll and pitch. This testing was done with an electrical subteam member who designed a custom PCB for imu-servo integration. 
  </figcaption>

</figure>

<h3>Flight Validation</h3>

<p>
The completed gimbal flew successfully in competition in <strong>September 2026</strong>.
During flight, the attitude-sensing system detected aircraft banking and commanded the
gimbal servos to compensate, allowing the GoPro to maintain its downward-facing orientation.
The mechanism achieved its full ±50° travel in both axes and performed as intended throughout
the mission.
</p>

<p>
The final assembly also withstood the actual flight environment, including
<strong>banking maneuvers up to 3 g and airspeeds up to 100 mph</strong>, while remaining
fully functional.
</p>

<figure style="margin: 32px auto; max-width: 900px;">

  <div style="
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
    width: 100%;
  ">
    <iframe
      src="https://www.youtube.com/embed/Ya-VY9S9qcU"
      title="CUAir GoPro gimbal flight test"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen
      style="
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
      ">
    </iframe>
  </div>

  <figcaption>
    <strong>Gimbal operating during flight testing.</strong>
    The completed two-axis mechanism actively compensates for aircraft attitude changes
    while mounted beneath the fuselage.
  </figcaption>

</figure>

<h3>Outcome</h3>

<p>
The project took the gimbal from concept through <strong>CAD, actuator sizing, additive
manufacturing, iterative prototyping, mechanical load testing, aircraft integration, and
competition flight</strong>. Compared with the previous system, the final design reduced
mass from 750 g to 210 g while lowering rotational inertia, reducing actuator demand, and
improving camera serviceability.
</p>

</div>

