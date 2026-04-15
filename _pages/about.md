---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<div class="with-particles" markdown="1">

Hello World! I'm currently an Undergraduate student in the School of Industrial and Systems Engineering at the University of Oklahoma with a minor in Mathematics. My academic interests include optimization, decision-making, and networked systems, and I use this site to document my research, experience, and professional development.

I have worked as an undergraduate researcher at both the University of Oklahoma and Clemson University, with projects focused on airline network resiliency and optimization for park planning under imperfect information.

## Education

**University of Oklahoma**, Norman, OK  
*B.S. in Industrial and Systems Engineering (Honors)*  
Minor in Mathematics  
Expected Graduation: May 2027  
GPA: 4.0/4.0

## Experience

<div id="experience-journey" class="experience-journey">
  <div class="experience-journey__entries">
    <div class="about-experience" data-journey-stop="norman">
      <div class="about-experience__text">
        <p><strong>Undergraduate Research Assistant</strong>, NetSys Research Lab<br>
        University of Oklahoma, Norman, OK<br>
        Sep 2025 - Present</p>
      </div>
      <div class="about-experience__visual">
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
    </div>

    <div class="experience-journey__connector" aria-hidden="true">
      <p class="experience-journey__connector-label">Research trail</p>
      <svg class="experience-journey__connector-map" viewBox="0 0 360 140">
        <path id="journey-connector-path" class="experience-journey__connector-path" d="M24 112 C88 20 204 18 336 92"></path>
        <circle id="journey-connector-traveler" class="experience-journey__connector-traveler" cx="24" cy="112" r="8"></circle>
      </svg>
    </div>

    <div class="about-experience" data-journey-stop="clemson">
      <div class="about-experience__text">
        <p><strong>Undergraduate Research Assistant</strong>, Tucker Research Group<br>
        Clemson Industrial Engineering, Clemson, SC<br>
        May 2025 - Jul 2025</p>
      </div>
      <div class="about-experience__visual">
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
