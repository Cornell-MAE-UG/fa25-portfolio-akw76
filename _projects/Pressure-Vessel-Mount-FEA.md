---
layout: project
title: Pressure Vessel Mount FEA
description: Designing and analyzing a mount for a 94-lb pressure vessel
technologies: Fusion 360, Ansys
image: "/assets/images/pv-rendering.png"
order: 4
---

<div class="project-wide">

<p>
As an undergraduate research assistant in Cornell University's
<strong>Symbolic Engineering and Analysis Lab</strong>, I independently designed,
analyzed, and fabricated a support structure for a <strong>94 lb pressure vessel</strong>
used in high-pressure saltwater filtration experiments.
</p>

<p>
The mount needed to elevate the vessel above the floor to provide clearance for pipes and
tubing underneath, while also allowing the vessel to be easily installed and removed between
experiments. I was given the suggestion to reuse the lab's available 80/20 aluminum extrusion,
but owned the mechanical design, structural analysis, and fabrication of the mount.
</p>

<h3>Mechanical Design</h3>

<p>
I designed the structure in <strong>Autodesk Fusion 360</strong> using 80/20 aluminum
extrusion and standard brackets. The vessel rests on four discrete support points without
being permanently attached to the frame, allowing it to be lifted on and off while keeping
the underside accessible for experimental plumbing.
</p>

<figure style="margin: 32px auto; max-width: 950px;">
  <img
    src="{{ '/assets/images/pv-rendering.png' | relative_url }}"
    alt="CAD rendering of the pressure vessel mount"
    style="width: 100%; height: auto; display: block;">

  <figcaption>
    <strong>Final pressure vessel mount CAD.</strong>
    The open-frame design supports the vessel at four discrete locations while maintaining
    clearance underneath for plumbing and allowing straightforward installation and removal.
  </figcaption>
</figure>

<h3>Structural Analysis</h3>

<p>
Before fabrication, I performed <strong>finite element analysis in Fusion 360</strong>
with the vessel's gravitational load distributed across the four contact points. I evaluated
both displacement and factor of safety to verify that the frame could support the 94 lb
vessel without excessive deformation or structural failure.
</p>

<div class="project-image-row">

  <figure>
    <img
      src="{{ '/assets/images/pv-displacement.png' | relative_url }}"
      alt="Finite element displacement analysis of the pressure vessel mount">

    <figcaption>
      <strong>Displacement FEA.</strong>
      Predicted deformation of the frame under the gravitational load of the pressure
      vessel applied through its four support points.
    </figcaption>
  </figure>

  <figure>
    <img
      src="{{ '/assets/images/pv-fos.png' | relative_url }}"
      alt="Finite element factor of safety analysis of the pressure vessel mount">

    <figcaption>
      <strong>Factor-of-safety FEA.</strong>
      Structural analysis used to verify that the frame remained within acceptable
      loading limits before fabrication.
    </figcaption>
  </figure>

</div>

<h3>Fabrication and Implementation</h3>

<p>
After validating the design, I fabricated the mount myself using the lab's existing
80/20 stock. I measured and cut the aluminum extrusion using a
<strong>table saw and band saw</strong>, hand-tapped holes where needed, and assembled
the structure using standard 80/20 brackets and hardware.
</p>

<figure style="margin: 32px auto; max-width: 950px;">
  <img
    src="{{ '/assets/images/pv-assembly.png' | relative_url }}"
    alt="Fabricated pressure vessel mount supporting the vessel in the laboratory"
    style="width: 100%; height: auto; display: block;">

  <figcaption>
    <strong>Completed mount in the experimental setup.</strong>
    The fabricated frame supports the 94 lb pressure vessel while preserving access to
    the plumbing connections below and allowing the vessel to be removed and reinstalled
    as needed.
  </figcaption>
</figure>

<h3>Outcome</h3>

<p>
The completed mount was installed in the laboratory and used as part of the
pressure-vessel experimental setup. I carried the project from functional requirements
through <strong>CAD, structural analysis, fabrication, assembly, and final implementation</strong>.
</p>

</div>