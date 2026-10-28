---
layout: page
title: "coding"
permalink: /coding/
description: "Agentic AI for research, open-source tools, and the data stack Deboleena Rakshit works with."
subtitle: "Agentic AI for research, open-source tools, and the stack I work with."
---

<h2 class="group-heading">tools</h2>

<div class="talk">
  <div class="pub-badge"><abbr>Agent skill</abbr></div>
  <div>
    <div class="pub-title">capi-form-lifecycle</div>
    <p class="pub-venue">An agent skill to build and manage Computer-Assisted Personal Interviewing (CAPI) surveys end-to-end, from the paper questionnaire to a deployed SurveyCTO form and back.</p>
    <div class="pub-links"><a class="btn-sm" href="https://github.com/meanregressive/capi-form-lifecycle" rel="noopener" target="_blank">Code</a></div>
  </div>
</div>

<h2 class="group-heading">agentic ai at ifpri</h2>

<div class="talk">
  <div class="pub-badge"><abbr>Training</abbr></div>
  <div>
    <div class="pub-title">Getting started with agentic AI for research</div>
    <p class="pub-venue">Led an IFPRI-wide training attended by 100+ employees.</p>
  </div>
</div>
<div class="talk">
  <div class="pub-badge"><abbr>Workshop</abbr></div>
  <div>
    <div class="pub-title">Claude Code and agentic AI for research analysts</div>
    <p class="pub-venue">Designed and led a hands-on session for a team of 15 research analysts based in Bangladesh.</p>
  </div>
</div>
<div class="talk">
  <div class="pub-badge"><abbr>Policy</abbr></div>
  <div>
    <div class="pub-title">Data Governance Management Committee</div>
    <p class="pub-venue">Member of the committee helping draft IFPRI's organizational policy on AI use.</p>
  </div>
</div>

<h2 class="group-heading">stack</h2>

<table class="kv">
  {% for s in site.data.cv.skills %}
    {% if s.label != "Languages" and s.label != "Writing and editing" %}
      <tr><th>{{ s.label }}</th><td>{{ s.value }}</td></tr>
    {% endif %}
  {% endfor %}
</table>
