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
  <div class="experience-journey__entries">
    <div class="about-experience" data-journey-stop="norman">
      <div class="about-experience__text">
        <p class="about-experience__label">Current lab</p>
        <h3><a href="https://andresdgonzalez.com/">NetSys Research Lab</a></h3>
        <p>The NetSys Research Lab at the University of Oklahoma focuses on modeling and optimizing the performance, robustness, and resilience of cyber-physical-social systems and interdependent networks.</p>
        <p>The group's work spans complex infrastructure and networked systems, with particular emphasis on how optimization and systems modeling can support more resilient decision-making.</p>
      </div>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/Net%20Sys%20Photo.JPG" alt="NetSys Research Lab group photo">
        <figcaption>NetSys Research Lab group photo (Dec. 2025)</figcaption>
      </figure>
      <aside class="journey-state-card" aria-label="Oklahoma research location">
        <p class="journey-state-card__eyebrow">Current stop</p>
        <h4 class="journey-state-card__title">Oklahoma</h4>
        <svg class="journey-state-card__map" viewBox="0 0 220 150">
          <path class="journey-state-card__outline" d="M23 44 L43 31 L87 31 L95 24 L164 24 L164 34 L195 34 L195 86 L170 86 L170 108 L134 108 L126 116 L90 116 L90 108 L23 108 Z"></path>
          <g class="journey-state-card__city">
            <circle cx="116" cy="74" r="7"></circle>
            <circle class="journey-state-card__pulse" cx="116" cy="74" r="12"></circle>
            <text x="128" y="79">Norman</text>
          </g>
        </svg>
      </aside>
    </div>

    <div class="experience-journey__connector" aria-hidden="true">
      <p class="experience-journey__connector-label">Research trail</p>
      <svg class="experience-journey__connector-map" viewBox="0 0 170 250">
        <path id="journey-connector-path" class="experience-journey__connector-path" d="M36 18 C118 52 126 102 86 152 C52 192 50 220 92 238"></path>
        <circle id="journey-connector-traveler" class="experience-journey__connector-traveler" cx="36" cy="18" r="8"></circle>
      </svg>
    </div>

    <div class="about-experience" data-journey-stop="clemson">
      <div class="about-experience__text">
        <p class="about-experience__label">Summer 2025 lab</p>
        <h3><a href="https://sites.google.com/view/emilyltucker/home?authuser=0">Tucker Research Group</a></h3>
        <p>The Tucker Research Group at Clemson University studies how operations research can improve access, social good, and decision-making in systems under strain.</p>
        <p>The lab develops optimization methods for problems with real public impact, especially where limited resources, uncertainty, and system-level tradeoffs shape the choices decision-makers can make.</p>
      </div>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/TRG%20Picture.jpg" alt="Tucker Research Group photo">
        <figcaption>Tucker Research Group photo (Jul. 2025)</figcaption>
      </figure>
      <aside class="journey-state-card" aria-label="South Carolina research location">
        <p class="journey-state-card__eyebrow">Summer stop</p>
        <h4 class="journey-state-card__title">South Carolina</h4>
        <svg class="journey-state-card__map" viewBox="0 0 220 170">
          <path class="journey-state-card__outline" d="M86 18 L110 30 L118 49 L129 56 L146 84 L141 101 L126 113 L123 130 L108 149 L91 146 L87 128 L77 118 L66 120 L58 110 L62 92 L54 78 L62 63 L71 60 L77 45 L86 39 Z"></path>
          <g class="journey-state-card__city">
            <circle cx="109" cy="93" r="7"></circle>
            <circle class="journey-state-card__pulse" cx="109" cy="93" r="12"></circle>
            <text x="121" y="98">Clemson</text>
          </g>
        </svg>
      </aside>
    </div>
  </div>
</div>

</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const section = document.getElementById("experience-journey");
    const path = document.getElementById("journey-connector-path");
    const traveler = document.getElementById("journey-connector-traveler");
    const stops = section ? Array.from(section.querySelectorAll("[data-journey-stop]")) : [];

    if (!section || !path || !traveler || stops.length < 2) {
      return;
    }

    const clamp = (value, min, max) => Math.min(max, Math.max(min, value));
    const pathLength = path.getTotalLength();
    path.style.strokeDasharray = pathLength;
    path.style.strokeDashoffset = pathLength;

    const setActiveStop = (activeIndex) => {
      stops.forEach((stop, index) => {
        stop.classList.toggle("is-active", index === activeIndex);
      });
    };

    const updateJourney = () => {
      const secondStop = stops[1];
      const secondRect = secondStop.getBoundingClientRect();
      const viewportHeight = window.innerHeight || document.documentElement.clientHeight;
      const focusLine = viewportHeight * 0.8;
      const startLine = viewportHeight * 0.94;
      const endLine = viewportHeight * 0.72;
      const progress = clamp((startLine - secondRect.top) / (startLine - endLine), 0, 1);
      const activeIndex = stops.reduce((currentIndex, stop, index) => {
        return stop.getBoundingClientRect().top <= focusLine ? index : currentIndex;
      }, 0);
      const drawnLength = pathLength * progress;
      const point = path.getPointAtLength(drawnLength);

      setActiveStop(activeIndex);
      path.style.strokeDashoffset = pathLength - drawnLength;
      traveler.setAttribute("cx", point.x);
      traveler.setAttribute("cy", point.y);
      traveler.style.opacity = progress > 0.02 ? "1" : "0";
      section.classList.toggle("is-traveling", progress > 0.04 && progress < 0.98);
    };

    updateJourney();
    window.addEventListener("scroll", updateJourney, { passive: true });
    window.addEventListener("resize", updateJourney);
  });
</script>
