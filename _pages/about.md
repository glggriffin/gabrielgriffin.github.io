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
  <aside class="experience-journey__graphic" aria-hidden="true">
    <div class="experience-journey__panel">
      <p class="experience-journey__eyebrow">Research Journey</p>
      <h3 class="experience-journey__title">Moving between labs</h3>
      <p class="experience-journey__note">Scroll through the section to move the marker between my research homes in Norman and Clemson.</p>

      <svg class="journey-map" viewBox="0 0 520 320">
        <path class="journey-map__land" d="M53 151 61 108 91 84 121 79 148 54 212 44 272 57 326 51 376 70 426 78 463 106 457 132 430 151 410 182 425 211 401 236 353 250 316 268 263 258 218 274 171 255 122 260 88 233 92 194Z" />
        <path id="journey-route" class="journey-map__route" d="M176 232 C203 191 248 163 293 172 C326 178 352 198 372 221" />

        <g class="journey-map__city">
          <circle cx="176" cy="232" r="10"></circle>
          <text x="118" y="257">Norman, OK</text>
        </g>

        <g class="journey-map__city">
          <circle cx="372" cy="221" r="10"></circle>
          <text x="345" y="201">Clemson, SC</text>
        </g>

        <g id="journey-traveler" class="journey-map__traveler" transform="translate(176 232)">
          <circle r="16"></circle>
          <text text-anchor="middle" dominant-baseline="central">GG</text>
        </g>
      </svg>
    </div>
  </aside>

  <div class="experience-journey__entries">
    <div class="about-experience">
      <div class="about-experience__text">
        <p><strong>Undergraduate Research Assistant</strong>, NetSys Research Lab<br>
        University of Oklahoma, Norman, OK<br>
        Sep 2025 - Present</p>
      </div>
      <figure class="about-experience__media">
        <img src="{{ base_path }}/images/Net%20Sys%20Photo.JPG" alt="NetSys Research Lab group photo">
        <figcaption>NetSys Research Lab group photo (Dec. 2025)</figcaption>
      </figure>
    </div>

    <div class="about-experience">
      <div class="about-experience__text">
        <p><strong>Undergraduate Research Assistant</strong>, Tucker Research Group<br>
        Clemson Industrial Engineering, Clemson, SC<br>
        May 2025 - Jul 2025</p>
      </div>
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
    const route = document.getElementById("journey-route");
    const traveler = document.getElementById("journey-traveler");

    if (!section || !route || !traveler) {
      return;
    }

    const clamp = (value, min, max) => Math.min(max, Math.max(min, value));
    const routeLength = route.getTotalLength();

    const updateJourney = () => {
      const rect = section.getBoundingClientRect();
      const viewportHeight = window.innerHeight || document.documentElement.clientHeight;
      const progress = clamp(
        (viewportHeight * 0.62 - rect.top) / Math.max(rect.height - viewportHeight * 0.18, 1),
        0,
        1
      );
      const point = route.getPointAtLength(progress * routeLength);
      traveler.setAttribute("transform", `translate(${point.x} ${point.y})`);
    };

    updateJourney();
    window.addEventListener("scroll", updateJourney, { passive: true });
    window.addEventListener("resize", updateJourney);
  });
</script>
