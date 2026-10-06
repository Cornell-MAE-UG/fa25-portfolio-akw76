---
layout: project
title: Boeing Loads and Dynamics Project
description: Developing CG acceleration thresholds for critical dynamic loads due to turbulence
technologies: 
image: "/assets/images/CG Lateral Accel[_Usigma] vs Frequency (MAX 9) Weight Band_ Heavy Trend_ Mach.png"
---

<div class="project-wide">

<h2>Severe Turbulence Inspection Threshold Development — Boeing 737 MAX</h2>

<p>
During my internship with Boeing's <strong>Loads and Dynamics</strong> group, I worked with
the Dynamic Flight Loads team to develop a method for reducing unnecessary aircraft
inspections after pilot-reported severe turbulence on the <strong>737 MAX 7, 9, and 10</strong>.
The goal was to compare the maximum CG acceleration measured during a turbulence event
against a model-derived threshold. If the measured response remained below the threshold,
the associated inspection could be waived; otherwise, inspection actions would be required.
</p>

<h3>Flight-Condition Modeling</h3>

<p>
I first built a representative set of flight conditions spanning the CG and gross-weight
envelopes of each MAX minor model. After evaluating hundreds of fuel vectors, I selected
approximately <strong>8–12 representative payload configurations per model</strong> and
varied altitude, gross weight, and airspeed across each configuration. This produced
approximately <strong>2,000 conditions per aircraft model</strong>.
</p>

<p>
I used Boeing's internal aeroelastic tools and Easy5 flight-control models to calculate
aircraft loads and CG responses for these conditions. I wrote <strong>MATLAB scripts to
generate model inputs, rewrite simulation input files, process results, and automate
analysis</strong> across vertical and lateral discrete and continuous gust cases.
Each condition contained more than <strong>600 response parameters</strong>, including
responses across approximately <strong>250 continuous-gust frequencies</strong> and
<strong>16 discrete-gust gradients</strong>.
</p>

<h3>Selecting the CG Response Metric</h3>

<p>
I analyzed the aircraft's low-frequency modes and frequency response to determine how CG
acceleration should be measured. The rigid-body aircraft response occurred below
<strong>2 Hz</strong>, while higher-frequency response increasingly contained structural
bending effects. I therefore used a 2 Hz cutoff, which also aligned with the available
flight-recorder sampling capability.
</p>

<div class="project-image-row">

  <figure>
    <img
      src="{{ '/assets/images/max10-lateral-frequency.png' | relative_url }}"
      alt="MAX 10 lateral CG acceleration versus frequency">
    <figcaption>
      <strong>MAX 10 lateral frequency response.</strong>
      Each curve represents a flight condition. The vertical line marks the 2 Hz cutoff
      used to capture rigid-body CG motion while excluding higher-frequency structural response.
    </figcaption>
  </figure>

  <figure>
    <img
      src="{{ '/assets/images/max9-lateral-frequency.png' | relative_url }}"
      alt="MAX 9 lateral CG acceleration versus frequency">
    <figcaption>
      <strong>MAX 9 lateral frequency response.</strong>
      The same analysis was repeated across aircraft weight, Mach, and flight-condition ranges
      to verify the cutoff across the operating envelope.
    </figcaption>
  </figure>

</div>

<h3>Reducing the Simulation Data</h3>

<p>
I wrote MATLAB analysis tooling to convert the Easy5 outputs into structured
<code>.mat</code> tables and evaluate trends across aircraft model, gross weight, CG,
Mach, altitude, impact pressure, and gust condition. The analysis showed that
<strong>CG acceleration provided a consistent metric for comparing gust severity</strong>,
with clear trends across impact pressure and gross weight.
</p>

<div class="project-image-row">

  <figure>
    <img
      src="{{ '/assets/images/max10-deltanz-qc.png' | relative_url }}"
      alt="MAX 10 change in vertical CG acceleration versus impact pressure">
    <figcaption>
      <strong>MAX 10 vertical response.</strong>
      Change in vertical CG acceleration versus impact pressure across representative
      gross-weight conditions.
    </figcaption>
  </figure>

  <figure>
    <img
      src="{{ '/assets/images/max9-deltanz-qc.png' | relative_url }}"
      alt="MAX 9 change in vertical CG acceleration versus impact pressure">
    <figcaption>
      <strong>MAX 9 vertical response.</strong>
      The response increases predictably with impact pressure while shifting with aircraft
      gross weight.
    </figcaption>
  </figure>

</div>

<h3>Deriving the Inspection Threshold</h3>

<p>
The final challenge was reducing both continuous and discrete gust cases to a single
inspection criterion. I compared the CG acceleration from the critical
<strong>Time Domain Gust (TDG)</strong> with the response from the critical
<strong>Power Spectral Density (PSD)</strong> continuous gust.
</p>

<p>
For the discrete case, I used the <strong>350-ft gust gradient</strong>, the largest
gradient analyzed and theoretically the strongest discrete gust. Across the analyzed
flight conditions, the critical TDG response remained greater than
<strong>80% of the corresponding critical PSD response</strong>. This allowed the
inspection logic to use one conservative threshold based only on the PSD response rather
than maintaining separate criteria for the two gust types.
</p>

<figure>
  <img
    src="{{ '/assets/images/max7-deltanz-ratio.png' | relative_url }}"
    alt="Ratio of TDG CG acceleration to PSD CG acceleration across impact pressure">

  <figcaption>
    <strong>TDG-to-PSD threshold validation for the MAX 7.</strong>
    Each point is the ratio of CG acceleration from the critical 350-ft TDG to the
    corresponding 2 Hz PSD response. All analyzed cases remain above the 0.80 threshold.
  </figcaption>
</figure>

<p>
I also used <strong>convex-hull analysis</strong> to consolidate the individual flight
conditions at each gross weight into conservative threshold lines, making the results
suitable for interpolation across the aircraft operating envelope.
</p>

<h3>Outcome</h3>

<p>
The project produced candidate severe-turbulence inspection thresholds for all three
737 MAX minor models and an analysis workflow spanning flight-condition selection,
aeroelastic simulation, MATLAB data processing, and threshold validation.
</p>

<p>
I presented the methodology and resulting thresholds in a
<strong>Technical Design Review (TDR)</strong> to Boeing managers and subject-matter
experts for technical review and potential implementation into aircraft software.
</p>

</div>