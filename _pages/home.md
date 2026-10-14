---
layout: default
title: Home
permalink: /
nav: false # al-folio renders the home link in the navbar brand; avoid a duplicate Home item.
nav_order: 1
---

<!-- First draft. Replace the biography and contact links after your review. -->

<section class="academic-intro" aria-label="Introduction">
  <header class="intro-heading">
    <h1>Wanting Yang <span class="chinese-name">(杨婉婷)</span></h1>
    <p class="position">Ph.D. Candidate</p>
    <p class="affiliation">School of Data Science<br>The Chinese University of Hong Kong, Shenzhen</p>
  </header>

  <div class="intro-grid">
    <div class="profile-column">
      {% assign profile_photo = site.static_files | where: "path", "/assets/img/profile.jpg" %}
      {% if profile_photo.size > 0 %}
        <img class="profile-photo" src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Portrait of Wanting Yang">
      {% else %}
        <div class="profile-placeholder" role="img" aria-label="Profile photo placeholder">Profile photo<br>to be added</div>
      {% endif %}
    </div>
    <div class="intro-content">
      <h2>About me</h2>
      <!-- Replace with final biography. -->
      <div class="biography">
        <p>Hi! I am a fourth-year Ph.D. candidate at The Chinese University of Hong Kong, Shenzhen, advised by <a href="https://sites.google.com/view/jingwei-zhang" target="_blank">Prof. Jingwei Zhang</a>.</p>
        <p>My research interests lie broadly in stochastic modeling and approximate dynamic programming, with application in resource allocation, healthcare management and revenue management. In 2023, I received my B.S. in Mathematics from Southeast University.</p>
      </div>
    </div>
    <!-- Contact details are read from _config.yml. Missing details are hidden. -->
    <div class="contact-links" aria-label="Contact and academic links">
      {% if site.contact.email != nil and site.contact.email != "" %}<span class="email-text">Email: {{ site.contact.email | escape }}</span>{% endif %}
      {% if site.contact.scholar_userid != nil and site.contact.scholar_userid != "" %}<a href="https://scholar.google.com/citations?user={{ site.contact.scholar_userid | escape }}">Google Scholar</a>{% endif %}
    </div>
  </div>
</section>
