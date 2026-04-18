---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

<div class="with-particles" markdown="1">

My research agenda centers on optimization and decision-making under imperfect information. I am especially interested in public and infrastructure systems where models must stay useful even when data are incomplete, objectives are simplified, and real decisions are shaped by operational constraints that are hard to encode perfectly.


<div class="research-projects">
  <section class="research-project">
    <div class="research-project__body">
      <p class="research-project__eyebrow">Flagship project</p>
      <h2>Optimization of Park Access with Imperfect Information</h2>
      <p class="research-project__meta">Tucker Research Group - Clemson Industrial Engineering</p>

      <p>This project studies how planners should make park-location decisions when measures of need disagree. Rather than treating a single accessibility index as ground truth, the work asks how optimization models can account for disagreement across indices and remain useful when the decision environment is only imperfectly represented.</p>

      <p><strong>Contribution:</strong> I took the main role in formulating and implementing the optimization model in <code>gurobipy</code>, with the technical work centered on how competing need formulations should shape public planning recommendations under imperfect information.</p>

      <p><strong>Method:</strong> modeled park siting as a comparison across alternative index-driven decision problems, using mixed-integer and bi-level optimization ideas to study how different need formulations change recommended facility investments in Greenville County, South Carolina.</p>

      <p><strong>Output:</strong> this work led to the accepted conference proceedings paper <em>Optimizing Park Locations with Imperfect Information</em> at the <em>IISE Annual Conference &amp; Expo</em>, along with posters and presentations on geospatial analysis and parameterization regret.</p>

      <p><strong>Why it matters:</strong> public planning models are most helpful when they stay honest about uncertainty instead of hiding it behind a single index or scoring rule.</p>

      <p>
        <a href="{{ base_path }}/files/Lenses_of_Park_Access__Optimization_with_Indices_.pdf" class="btn btn--primary">Conference Paper PDF</a>
        <a href="{{ base_path }}/publications/" class="btn btn--inverse">See All Outputs</a>
      </p>
    </div>
  </section>

  <section class="research-project">
    <div class="research-project__body">
      <p class="research-project__eyebrow">Current project</p>
      <h2>Airline Network Dynamic Recovery</h2>
      <p class="research-project__meta">NetSys Research Lab - University of Oklahoma</p>

      <p>This project examines how airline networks respond to disruption and how network structure shapes resilience. The core question is how large transportation systems absorb shocks, where they are most vulnerable, and what kinds of dynamic models best capture recovery behavior over time.</p>

      <p><strong>Contribution:</strong> developing a systems-level view of disruption and recovery that connects transportation resilience questions to my broader interest in decision-making under uncertainty.</p>

      <p><strong>Method:</strong> using Dynamic Mode Decomposition and network-based analysis to study how system behavior evolves over time and to identify patterns that static summaries can miss.</p>

      <p><strong>Current direction:</strong> using airline networks as a public-facing infrastructure setting where better resilience models can support stronger planning decisions when disruptions are unavoidable.</p>

      <p><strong>Why it matters:</strong> transportation networks are visible public systems, and better models of resilience can improve how disruptions are understood, anticipated, and managed.</p>
    </div>
  </section>
</div>

## Research Trajectory

- `Coursework foundation:` deterministic system modeling, data-driven decision making, network optimization, and probabilistic systems modeling.
- `REU research:` public-sector optimization under imperfect information through park-access modeling at Clemson.
- `Research outputs:` accepted IISE conference proceedings paper plus multiple posters and presentations.
- `Current extension:` resilience analysis for large transportation networks in the NetSys Research Lab.

## Methods & Tools

- Mixed-integer optimization in `gurobipy`
- Bi-level optimization and regret-aware decision modeling
- Network optimization and systems modeling
- Dynamic Mode Decomposition for temporal network behavior
- Statistical and computational analysis in `Python`, `R`, `SAS`, `Excel`, and `Minitab`

## Project Themes

- Optimization under uncertainty and imperfect information
- Public systems, infrastructure, and access
- Resilience in large-scale networked systems
- Decision support that stays connected to real decision contexts

## Research Outputs

For publications, posters, and research-in-progress entries, visit the full research outputs archive.

[View Research Outputs]({{ base_path }}/publications/){: .btn .btn--primary}

</div>
