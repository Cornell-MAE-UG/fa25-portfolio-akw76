---
layout: project
title: Boeing Loads and Dynamics Project
description: Developing CG acceleration thresholds for critical dynamic loads due to turbulence
technologies: 
image: "/assets/images/CG Lateral Accel[_Usigma] vs Frequency (MAX 9) Weight Band_ Heavy Trend_ Mach.png"
---

<h2>Severe Turbulence Inspection Threshold Development — Boeing 737 MAX</h2>

<p>
During my internship with Boeing's <strong>Loads and Dynamics</strong> group, I worked with
the Dynamic Flight Loads team on a method to reduce unnecessary post-flight inspections
following pilot-reported severe turbulence on the <strong>737 MAX 7, 9, and 10</strong>.
The goal was to predict the aircraft's expected center-of-gravity (CG) response to
FAA-defined design gusts and compare that response against the turbulence actually
experienced in flight. This provided a physics-based way to determine whether an
inspection could potentially be waived and the aircraft returned to service sooner.
</p>

<p>
The project combined <strong>flight-condition sampling, aeroelastic modeling,
controls simulation, structural dynamics, and large-scale MATLAB data processing</strong>.
Across the three MAX minor models, I constructed and analyzed thousands of aircraft
conditions and processed hundreds of response parameters over hundreds of gust inputs.
</p>

<h3>Building the Flight-Condition Envelope</h3>

<p>
I first developed a sampling strategy to cover the aircraft's operational CG and gross-weight
envelope without making the analysis computationally intractable. I evaluated hundreds of
candidate fuel vectors and selected approximately <strong>8–12 representative payload
configurations per minor model</strong> based on both operational frequency and envelope
coverage.
</p>

<p>
Each payload configuration was expanded into a set of aircraft conditions using:
</p>

<ul>
  <li><strong>Altitude:</strong> 0–40,000 ft in 5,000-ft increments</li>
  <li><strong>Gross weight:</strong> 10,000-lb increments along each configuration's fuel vector</li>
  <li><strong>Airspeed:</strong> 40-knot increments beginning near cruise, plus a case at maximum operating speed</li>
</ul>

<p>
These increments were chosen to balance interpolation accuracy against model runtime and
data volume. The resulting design space contained <strong>nearly 2,000 flight conditions
per MAX minor model</strong>.
</p>

<h3>Aeroelastic and Flight-Control Modeling</h3>

<p>
For each condition, I used Boeing internal analysis tools and <strong>Easy5 flight-control
models</strong> to calculate aircraft loads and CG responses. I wrote MATLAB scripts to
automatically generate input tapes for an internal structural and aeroelastic model of the
737 MAX. The resulting equations-of-motion matrices were then incorporated into the Easy5
control-system model.
</p>

<p>
I debugged and adapted the simulation workflow for the scope of the study, including
separate analyses for <strong>vertical and lateral gusts</strong> and for both
<strong>discrete and continuous gust inputs</strong>. Each simulation produced more than
<strong>600 aircraft response parameters</strong> evaluated over approximately
<strong>250 continuous-gust frequencies</strong> and <strong>16 discrete-gust gradients</strong>.
</p>

<p>
I also examined the aircraft's eigenvalues and eigenmodes to understand its low-frequency
structural bending behavior. Based on this analysis, I selected a <strong>2 Hz cutoff</strong>
for the loads comparison: low-frequency rigid-body aircraft response is retained while
higher-frequency structural bending response is conservatively excluded from the
inspection metric.
</p>

<div style="display: flex; flex-wrap: wrap; gap: 24px; margin: 30px 0; align-items: flex-start;">

  <figure style="flex: 1 1 460px; margin: 0;">
    <img
      src="{{ '/assets/images/CG Lateral Accel[_Usigma] vs Frequency (MAX 10) Weight Band_ Light Trend_ Mach.png' | relative_url }}"
      alt="737 MAX 10 lateral CG acceleration response versus frequency"
      style="width: 100%; height: auto; display: block;"
    >
    <figcaption style="font-size: 0.9em; line-height: 1.4; margin-top: 8px; color: #555;">
      <strong>MAX 10 lateral gust frequency response.</strong>
      CG acceleration response across hundreds of flight conditions, with the vertical
      line marking the 2 Hz cutoff used to separate the low-frequency aircraft response
      from higher-frequency structural dynamics. Curves are grouped by Mach regime.
    </figcaption>
  </figure>

  <figure style="flex: 1 1 460px; margin: 0;">
    <img
      src="{{ '/assets/images/CG Lateral Accel[_Usigma] vs Frequency (MAX 9) Weight Band_ Heavy Trend_ Mach.png' | relative_url }}"
      alt="737 MAX 9 lateral CG acceleration response versus frequency"
      style="width: 100%; height: auto; display: block;"
    >
    <figcaption style="font-size: 0.9em; line-height: 1.4; margin-top: 8px; color: #555;">
      <strong>MAX 9 lateral gust frequency response.</strong>
      A corresponding heavy-weight analysis used to verify that the selected frequency
      treatment remained conservative across aircraft weight and Mach conditions.
    </figcaption>
  </figure>

</div>

<h3>Processing and Reducing the Simulation Data</h3>

<p>
The largest technical challenge was reducing the volume of simulation output into a useful
inspection criterion. I wrote MATLAB tooling to ingest the Easy5 results, convert them into
structured <code>.mat</code> analysis tables, calculate derived metrics, and generate plots
across aircraft model, weight, CG, Mach, altitude, impact pressure, and gust condition.
</p>

<p>
I evaluated <strong>CG acceleration as the candidate inspection metric</strong> by studying
how the simulated vertical and lateral responses changed across impact pressure and gross
weight. The response showed a strong and predictable relationship with impact pressure,
while weight-dependent trends could be captured explicitly in the threshold analysis.
</p>

<figure style="margin: 32px auto; max-width: 1050px;">
  <img
    src="{{ '/assets/images/_DeltaNz [TDG] vs Q_c (MAX 10).png' | relative_url }}"
    alt="MAX 10 vertical CG acceleration response versus impact pressure"
    style="width: 100%; height: auto; display: block;"
  >
  <figcaption style="font-size: 0.9em; line-height: 1.4; margin-top: 8px; color: #555;">
    <strong>Vertical CG response versus impact pressure for the MAX 10.</strong>
    The discrete-gust response increases systematically with impact pressure, with the
    individual curves showing the effect of gross weight on the resulting acceleration.
    Establishing these trends was important for determining whether CG acceleration could
    serve as a stable inspection-threshold metric.
  </figcaption>
</figure>

<figure style="margin: 32px auto; max-width: 1050px;">
  <img
    src="{{ '/assets/images/_DeltaNz [TDG] vs Q_c (MAX 9).png' | relative_url }}"
    alt="MAX 9 vertical CG acceleration response versus impact pressure"
    style="width: 100%; height: auto; display: block;"
  >
  <figcaption style="font-size: 0.9em; line-height: 1.4; margin-top: 8px; color: #555;">
    <strong>MAX 9 response across gross-weight conditions.</strong>
    Thousands of simulation results were reduced into trend plots such as this one to
    identify consistent relationships between gust severity, aircraft condition, and CG
    response across the flight envelope.
  </figcaption>
</figure>

<h3>Deriving and Validating the Inspection Threshold</h3>

<p>
The final step was determining whether a continuous-gust CG response could provide a
conservative threshold for the discrete gust cases that drive structural loading. I compared
the two response types across the full condition set and used ratio analyses and convex-hull
visualizations to search for limiting cases.
</p>

<p>
The analysis showed that a threshold of <strong>80% of the CG acceleration produced by the
design continuous-gust input</strong> remained below the critical discrete-gust responses
across the analyzed conditions. This provided a conservative boundary that could be used
to distinguish turbulence events that warranted further structural inspection from events
whose measured response remained below the design-based criterion.
</p>

<figure style="margin: 32px auto; max-width: 1050px;">
  <img
    src="{{ '/assets/images/_DeltaNz Ratio [TDG (@350ft) _ PSD (@2Hz)] vs Q_c (MAX 7).png' | relative_url }}"
    alt="Ratio of discrete gust response to continuous gust response for the MAX 7"
    style="width: 100%; height: auto; display: block;"
  >
  <figcaption style="font-size: 0.9em; line-height: 1.4; margin-top: 8px; color: #555;">
    <strong>Threshold validation for the MAX 7.</strong>
    Each point compares a discrete-gust response with the corresponding 2 Hz continuous-gust
    response across impact pressure and weight conditions. The dashed line marks the proposed
    80% criterion; the analyzed cases remain above this boundary, supporting its use as a
    conservative inspection threshold.
  </figcaption>
</figure>

<h3>Outcome</h3>

<p>
By the end of the internship, I had developed an end-to-end workflow spanning
<strong>flight-condition selection, model generation, controls and aeroelastic simulation,
structural-dynamics verification, automated data reduction, and threshold validation</strong>.
The work provided the Dynamic Flight Loads team with a technical basis for evaluating
whether severe-turbulence events could be screened using measured CG response rather than
automatically requiring the same level of post-flight inspection.
</p>

<p>
I documented the methodology, assumptions, and results in a <strong>Technical Design Review
(TDR)</strong> and presented the work to Boeing technical fellows and subject-matter experts,
where I received feedback on the modeling approach, frequency cutoff, and threshold
selection.
</p>