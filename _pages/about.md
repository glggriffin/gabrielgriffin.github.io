---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<div class="with-particles" markdown="1">

I am an undergraduate student in Industrial and Systems Engineering at the University of Oklahoma with interests in optimization, decision-making, and public-sector systems. I study how to make better decisions when information is incomplete and resources are constrained, especially in systems that shape public outcomes.

My work focuses on applying optimization methods to problems that directly affect the public good, including infrastructure planning, resource allocation, and policy-driven decision systems. I am particularly interested in settings where decision-makers must act using simplified models or limited information, and in how those limitations influence outcomes.

That perspective shapes the kinds of research questions I want to pursue and the environments where I do my best work. I am drawn to research groups that use mathematical modeling to study difficult real-world systems while staying grounded in the public consequences of those decisions.

I plan to pursue a PhD in Industrial Engineering, with the goal of developing optimization frameworks that better reflect the constraints and informational limits faced by real decision-makers. I am especially interested in applications in public policy and nonprofit operations, where better decision tools can have meaningful societal impact.

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
        <p>The NetSys Research Lab at the University of Oklahoma focuses on modeling and optimizing the performance, robustness, and resilience of cyber-physical-social systems and interdependent networks.</p>
        <p>The group's work spans complex infrastructure and networked systems, with particular emphasis on how optimization and systems modeling can support more resilient decision-making.</p>
      </div>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/Net%20Sys%20Photo.JPG" alt="NetSys Research Lab group photo">
        <figcaption>NetSys Research Lab group photo (Dec. 2025)</figcaption>
      </figure>
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
    </div>

    <div class="about-experience" data-journey-stop="clemson">
      <div class="about-experience__text">
        <h3><a href="https://sites.google.com/view/emilyltucker/home?authuser=0">Tucker Research Group</a></h3>
        <p>The Tucker Research Group at Clemson University studies how operations research can improve access, social good, and decision-making in systems under strain.</p>
        <p>The lab develops optimization methods for problems with real public impact, especially where limited resources, uncertainty, and system-level tradeoffs shape the choices decision-makers can make.</p>
      </div>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/TRG%20Picture.jpg" alt="Tucker Research Group photo">
        <figcaption>Tucker Research Group photo (Jul. 2025)</figcaption>
      </figure>
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
