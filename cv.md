---
layout: page
title: "CV"
description: "Curriculum vitae — Deboleena Rakshit. Research Analyst II at IFPRI."
permalink: /cv/
---

<a href="{{ '/assets/files/Rakshit_Deboleena_CV_2026.pdf' | relative_url }}" class="btn-download" download>
  Download PDF &darr;
</a>

<p style="font-style: italic; font-size: var(--font-size-sm); color: var(--color-text-muted); margin-top: var(--space-3);">
  Last updated March 2026.
</p>

---

<span class="section-rule">Experience</span>

<ul class="experience-list">
  {% for job in site.data.experience %}
  <li class="experience-item">
    <div class="experience-header">
      <span class="experience-org">{{ job.org }}</span>
      <span class="experience-dates">{{ job.dates }}</span>
    </div>
    <p class="experience-role">{{ job.role }} &ensp;&middot;&ensp; {{ job.location }}</p>
    <ul>
      {% for bullet in job.bullets %}
        <li>{{ bullet }}</li>
      {% endfor %}
    </ul>
  </li>
  {% endfor %}
</ul>

<span class="section-rule">Education</span>

<table class="education-table">
  <tbody>
    <tr>
      <td><strong>Linear Algebra, Multivariable Calculus, Real Analysis</strong><br>
      American University, Washington, DC</td>
      <td>2023–2025</td>
    </tr>
    <tr>
      <td><strong>M.A. International Relations</strong><br>
      Specialization: Development Economics<br>
      School of Advanced International Studies (SAIS), Johns Hopkins University</td>
      <td>2017–2019</td>
    </tr>
    <tr>
      <td><strong>B.A. (Honors) English Literature</strong><br>
      Jadavpur University, Kolkata</td>
      <td>2008–2011</td>
    </tr>
  </tbody>
</table>

<span class="section-rule">Selected Publications</span>

{% assign recent_pubs = site.data.publications | slice: 0, 5 %}
<ol class="pub-list">
{% for pub in recent_pubs %}
  {% include pub-entry.html pub=pub %}
{% endfor %}
</ol>

<a href="{{ '/publications/' | relative_url }}" style="font-family: var(--font-sans); font-size: var(--font-size-sm);">View all publications &rarr;</a>

<span class="section-rule">Skills</span>

<div class="tools-grid">
  <div class="tools-group">
    <h4>Analysis</h4>
    <ul>
      <li>Stata</li>
      <li>Python</li>
      <li>Tableau</li>
      <li>LaTeX</li>
      <li>Google Earth Engine</li>
      <li>MS Excel</li>
    </ul>
  </div>
  <div class="tools-group">
    <h4>Survey &amp; CAPI</h4>
    <ul>
      <li>SurveyCTO</li>
      <li>Kobo Toolbox</li>
      <li>SurveyMonkey</li>
    </ul>
  </div>
</div>

<span class="section-rule">Languages</span>

<ul class="pill-list">
  <li class="pill">Bengali</li>
  <li class="pill">English</li>
  <li class="pill">French</li>
  <li class="pill">Hindi</li>
</ul>
