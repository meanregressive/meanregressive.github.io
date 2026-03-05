---
layout: page
title: "Research"
description: "Research interests, methods, and work experience."
permalink: /research/
---

<span class="section-rule">Research interests</span>

<ul class="interest-list">
  <li class="interest-item">
    <h3>Gender Equality &amp; Women's Economic Empowerment</h3>
    <p>
      How do social protection programs, livelihood interventions, and behavior change communications
      shift women's economic participation and decision-making power within households? I am interested
      in both the measurement of empowerment — the conceptual and methodological challenges of
      operationalizing agency — and in the program conditions under which changes are durable.
    </p>
  </li>
  <li class="interest-item">
    <h3>Intimate Partner Violence &amp; Transfers</h3>
    <p>
      Cash and food transfers to poor households can reduce intimate partner violence, but the
      mechanisms and durability of that effect are not well understood. I co-authored a study
      (<a href="https://doi.org/10.1016/j.socscimed.2025.117901" rel="noopener" target="_blank">Lokot et al., 2025</a>)
      that followed up a Bangladesh RCT nine years after the program ended, one of the longest
      post-program follow-ups in this literature. The findings complicate optimistic accounts of
      durable norm change.
    </p>
  </li>
  <li class="interest-item">
    <h3>Household Resilience &amp; Social Protection</h3>
    <p>
      I am involved in evaluating graduation programs — integrated packages of cash, training,
      and mentorship targeting ultra-poor households — in both the Bangladesh and Somalia contexts.
      In Egypt, I work with 13 million administrative records from the Ministry of Social Solidarity
      on the Takaful and Karama social protection programs.
    </p>
  </li>
  <li class="interest-item">
    <h3>Gender Attitudes &amp; Masculinities</h3>
    <p>
      Before joining IFPRI, I spent four years at Equimundo working on the International Men and
      Gender Equality Survey (IMAGES), a harmonized cross-national dataset covering men's attitudes
      toward gender roles, caregiving, and violence across 33 countries and 67,000 respondents.
      I remain interested in how gender norms — and the interventions designed to shift them —
      operate across cultural contexts.
    </p>
  </li>
</ul>

<span class="section-rule">Methods</span>

My day-to-day work combines experimental and quasi-experimental methods. I design and analyze
randomized controlled trials, work with large administrative datasets in Stata and Python, and
conduct systematic reviews. Earlier in my career I worked extensively with household surveys and
mixed-method designs. I am comfortable across these registers and think the choice of method
should follow the question — not the other way around.

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

<span class="section-rule">Presentations</span>

<ul class="presentations-list">
  <li class="presentation-item">
    <span class="presentation-event">IFPRI RISE Research Day Conference</span>
    <span class="presentation-year">2024</span>
  </li>
  <li class="presentation-item">
    <span class="presentation-event">Sexual Violence Research Initiative (SVRI) Forum</span>
    <span class="presentation-year">2022</span>
  </li>
</ul>
