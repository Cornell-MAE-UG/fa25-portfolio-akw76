---
layout: project
title: Custom Bay Door for UAS
description: Designed, manufactured, and tested a custom lightweight bay door for a search and rescue aircraft
technologies: 
image: "/assets/baydoorfullcad.png"
---

<div class="project-wide">

<h2>Lightweight Bay Door for Autonomous UAS Airdrop System</h2>

<p>
As a member of the <strong>Structures and Payloads</strong> subteam on Cornell University
Unmanned Air Systems (CUAir), I designed, fabricated, and tested the payload bay door for
our autonomous VTOL aircraft. During the competition mission, the aircraft releases an
<strong>antenna tracker and water bottle</strong> through the payload bay as part of an
automated airdrop sequence.
</p>

<p>
Because the aircraft flies at speeds up to <strong>100 mph</strong>, leaving the payload bay
open would expose a large cavity to the airflow and create unnecessary drag. My goal was to
design a door that completely covered the fixed bay opening, opened at least
<strong>90°</strong> for payload release, fit within the limited fuselage volume, and weighed
less than <strong>50 g</strong>.
</p>

<h3>Design and Material Trade Study</h3>

<p>
Weight drove most of the design decisions. I prototyped and compared three approaches:
a solid wooden door, a carbon-fiber layup, and a lightweight wooden frame covered with
Monokote film. The frame-and-film design provided the required coverage with the lowest
mass and became the final architecture.
</p>

<p>
The finished door weighs <strong>49 g</strong>. Its structure consists of a
<strong>0.25-inch laser-cut wooden frame</strong> covered with a thin Monokote membrane.
The frame carries the mechanical loads while the membrane closes the opening with
negligible added mass.
</p>

<figure style="margin: 32px auto; max-width: 950px;">
  <img
    src="{{ '/assets/baydoorfullcad.png' | relative_url }}"
    alt="CAD assembly of the CUAir payload bay door"
    style="width: 100%; height: auto; display: block;">

  <figcaption>
    <strong>Full bay-door CAD assembly.</strong>
    I designed the servo mount, bearing support, door frame, and connecting components in
    SolidWorks while packaging the mechanism within the available fuselage volume.
  </figcaption>
</figure>

<h3>Actuation and Mechanical Design</h3>

<p>
The door is actuated by an <strong>HS-5070MH digital micro servo</strong>. I designed a
connector between the servo horn and the door so that servo rotation directly drives the
door through its opening and closing motion.
</p>

<p>
On the opposite side of the door, I incorporated a bearing along the axis of rotation.
The bearing provides a reaction force at the far end of the door while allowing free
rotation, supporting the mechanism at both ends rather than cantilevering the entire door
from the servo shaft.
</p>

<p>
Before fabrication, I performed hand calculations to estimate the aerodynamic drag force
on the door and verify that the selected servo provided sufficient torque to operate the
mechanism under the expected load.
</p>

<h3>Fabrication and Testing</h3>

<p>
I manufactured and assembled the complete mechanical system myself. I CADed and
<strong>3D-printed the mounts and connectors</strong>, designed and
<strong>laser-cut the wooden frame</strong>, applied the Monokote covering, installed the
servo and bearing, and integrated the completed assembly into the aircraft.
</p>

<p>
To validate the actuation system, I used a <strong>force probe to apply load to the door</strong>
while commanding it to open. This verified that the servo retained sufficient torque to
operate the mechanism under applied force before the system was flown.
</p>

<figure style="margin: 32px auto; max-width: 900px;">
  <img
    src="{{ '/assets/images/baydoorfuselagepic.png' | relative_url }}"
    alt="CUAir payload bay door installed in the aircraft fuselage"
    style="width: 100%; height: auto; display: block;">

  <figcaption>
    <strong>Completed bay-door assembly installed in the aircraft.</strong>
    The servo, bearing-supported door, and lightweight frame were packaged within the
    available fuselage volume while maintaining the required payload-bay opening and
    90° deployment range.
  </figcaption>
</figure>

<h3>Competition Performance</h3>

<p>
The completed 49 g bay door was installed on CUAir's competition aircraft and
<strong>flown in competition in September 2026</strong>. The system performed as designed,
opening for the airdrop sequence and closing again after payload release.
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
      src="https://www.youtube.com/embed/s2JUJfQ5BJ8"
      title="Bay Door Test Flight Footage"
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
    <strong>Bay-door airdrop sequence.</strong>
    The completed mechanism opens approximately 90° to clear the payload bay for release,
    then closes to restore the aircraft's external surface for continued flight.
  </figcaption>

</figure>

</div>

