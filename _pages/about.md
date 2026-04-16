---
permalink: /
title: "Research Overview"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<div class="with-particles" markdown="1">

I am an undergraduate researcher in Industrial and Systems Engineering at the University of Oklahoma studying optimization under imperfect information, especially in public and infrastructure systems. My work asks how decision-makers should act when models are simplified, data are incomplete, and resources are constrained.

I am building that agenda through two connected streams of work: regret-aware optimization for public planning and resilience analysis for large transportation networks. Across both, I am interested in how mathematical models can remain useful when the information available to the decision-maker is incomplete, imperfect, or changing over time.

Recent outputs include an accepted conference proceedings paper at the *IISE Annual Conference & Expo*, poster presentations on park-access modeling and parameterization regret, and current research in the NetSys Research Lab on airline network disruption and recovery.

That perspective shapes the kinds of questions I want to pursue in a PhD in Industrial Engineering or Operations Research: optimization frameworks that better reflect the informational limits and modeling tradeoffs faced by real decision-makers, especially in public-good settings.

[Research]({{ base_path }}/research/){: .btn .btn--primary}
[Research Outputs]({{ base_path }}/publications/){: .btn .btn--inverse}
[CV]({{ base_path }}/cv/){: .btn .btn--inverse}

## Start Here

- `Research:` research agenda, flagship projects, methods, and current directions.
- `Research Outputs:` conference proceedings, posters, and research-in-progress entries.
- `CV:` education, coursework, honors, and a full record of experience and presentations.

## Research At a Glance

- `Research agenda:` optimization and decision support under uncertainty in public and infrastructure systems.
- `Current work:` airline network resilience and dynamic recovery using Dynamic Mode Decomposition and network-based analysis.
- `Flagship output:` accepted IISE conference proceedings paper on park-location optimization under imperfect information.
- `Methods:` mixed-integer optimization, bi-level and regret-aware modeling, network optimization, and data-driven analysis.

## Research Direction

Each project on this site is evidence for the same broader research direction: decision support is only as strong as the assumptions behind it. I am especially interested in models that stay informative even when data are incomplete, objectives are imperfect proxies, or the real system is more complex than the optimization model can fully represent.

## Research Journey

<div id="experience-journey" class="experience-journey">
  <svg class="experience-journey__overlay" aria-hidden="true">
    <path id="journey-connector-path" class="experience-journey__connector-path" d=""></path>
    <circle id="journey-traveler-dot" class="experience-journey__traveler-dot" cx="0" cy="0" r="6"></circle>
  </svg>
  <div class="experience-journey__entries">
    <div class="about-experience" data-journey-stop="norman">
      <div class="about-experience__text">
        <h3><a href="https://andresdgonzalez.com/">NetSys Research Lab</a></h3>
        <p>The NetSys Research Lab at the University of Oklahoma studies the performance, robustness, and resilience of cyber-physical-social systems and interdependent networks.</p>
        <p>My current work examines airline network resilience through Dynamic Mode Decomposition and network-based analysis, with the goal of understanding how disruptions propagate and how large transportation systems recover over time.</p>
      </div>
      <aside class="journey-state-card" aria-label="Oklahoma research location">
        <p class="journey-state-card__eyebrow">2025-2026</p>
        <div class="journey-state-card__map">
          <div class="journey-state-card__map-shape journey-state-card__map-shape--oklahoma" aria-hidden="true"></div>
          <div class="journey-state-card__marker" data-city-marker style="--marker-x: 64.0058%; --marker-y: 52.0377%;">
            <span class="journey-state-card__pulse"></span>
            <span class="journey-state-card__dot"></span>
          </div>
        </div>
      </aside>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/Net%20Sys%20Photo.JPG" alt="NetSys Research Lab group photo">
        <figcaption>NetSys Research Lab group photo (Dec. 2025)</figcaption>
      </figure>
    </div>

    <div class="about-experience" data-journey-stop="clemson">
      <div class="about-experience__text">
        <h3><a href="https://sites.google.com/view/emilyltucker/home?authuser=0">Tucker Research Group</a></h3>
        <p>The Tucker Research Group at Clemson University studies how operations research can improve access, social good, and decision-making in systems under strain.</p>
        <p>During the Human-Centered Operations Research and Engineering (<a href="https://cecas.clemson.edu/hcore/">H-CORE</a>) REU, I worked on park-access optimization in Greenville County, South Carolina, studying how different need indices and modeling assumptions change recommended investment decisions.</p>
        <p>That project led to an accepted IISE conference paper, multiple poster presentations, and my continuing interest in regret-aware optimization for public planning.</p>
      </div>
      <aside class="journey-state-card" aria-label="South Carolina research location">
        <p class="journey-state-card__eyebrow">2025</p>
        <div class="journey-state-card__map">
          <div class="journey-state-card__map-shape journey-state-card__map-shape--south-carolina" aria-hidden="true"></div>
          <div class="journey-state-card__marker" data-city-marker style="--marker-x: 16.2761%; --marker-y: 15.6534%;">
            <span class="journey-state-card__pulse"></span>
            <span class="journey-state-card__dot"></span>
          </div>
        </div>
      </aside>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/TRG%20Picture.jpg" alt="Tucker Research Group photo">
        <figcaption>Tucker Research Group photo (Jul. 2025)</figcaption>
      </figure>
    </div>
  </div>
</div>

</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const section = document.getElementById("experience-journey");
    const path = document.getElementById("journey-connector-path");
    const traveler = document.getElementById("journey-traveler-dot");
    const stops = section ? Array.from(section.querySelectorAll("[data-journey-stop]")) : [];
    const markers = section ? Array.from(section.querySelectorAll("[data-city-marker]")) : [];

    if (!section || !path || !traveler || stops.length < 2 || markers.length < 2) {
      return;
    }

    const clamp = (value, min, max) => Math.min(max, Math.max(min, value));

    const setActiveStop = (activeIndex) => {
      stops.forEach((stop, index) => {
        stop.classList.toggle("is-active", index === activeIndex);
      });
    };

    const updatePathGeometry = () => {
      const sectionRect = section.getBoundingClientRect();
      const startRect = markers[0].getBoundingClientRect();
      const endRect = markers[1].getBoundingClientRect();
      const startX = startRect.left + startRect.width / 2 - sectionRect.left;
      const startY = startRect.top + startRect.height / 2 - sectionRect.top;
      const endX = endRect.left + endRect.width / 2 - sectionRect.left;
      const endY = endRect.top + endRect.height / 2 - sectionRect.top;
      const outerX = Math.max(startX, endX) + 34;
      const controlY = startY + (endY - startY) * 0.5;
      const pathData = [
        "M", startX.toFixed(2), startY.toFixed(2),
        "C",
        outerX.toFixed(2), controlY.toFixed(2),
        outerX.toFixed(2), controlY.toFixed(2),
        endX.toFixed(2), endY.toFixed(2)
      ].join(" ");

      path.setAttribute("d", pathData);
    };

    const updateJourney = () => {
      const secondStop = stops[1];
      const secondRect = secondStop.getBoundingClientRect();
      const viewportHeight = window.innerHeight || document.documentElement.clientHeight;
      const focusLine = viewportHeight * 0.8;
      updatePathGeometry();
      const startLine = viewportHeight * 0.9;
      const endLine = viewportHeight * 0.55;
      const progress = clamp((startLine - secondRect.top) / (startLine - endLine), 0, 1);
      const pathLength = path.getTotalLength();
      const point = path.getPointAtLength(pathLength * progress);
      const activeIndex = stops.reduce((currentIndex, stop, index) => {
        return stop.getBoundingClientRect().top <= focusLine ? index : currentIndex;
      }, 0);

      setActiveStop(activeIndex);
      traveler.setAttribute("cx", point.x.toFixed(2));
      traveler.setAttribute("cy", point.y.toFixed(2));
    };

    updateJourney();
    window.addEventListener("scroll", updateJourney, { passive: true });
    window.addEventListener("resize", updateJourney);
  });
</script>
