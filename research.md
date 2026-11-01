---
layout: page
title: "research"
permalink: /research/
description: "Peer-reviewed articles, working papers, policy reports, and conference presentations by Deboleena Rakshit."
subtitle: "Peer-reviewed articles, working papers, technical and policy reports, conference presentations, and peer review."
---

<h2 class="group-heading">peer-reviewed articles</h2>
<ol class="pub-list">
{% assign items = site.data.publications | where: "type", "journal" %}
{% for pub in items %}{% include pub-entry.html pub=pub %}{% endfor %}
</ol>

<h2 class="group-heading">working papers</h2>
<ol class="pub-list">
{% assign items = site.data.publications | where: "type", "working" %}
{% for pub in items %}{% include pub-entry.html pub=pub %}{% endfor %}
</ol>

<h2 class="group-heading">technical &amp; policy reports</h2>
<ol class="pub-list">
{% assign items = site.data.publications | where: "type", "report" %}
{% for pub in items %}{% include pub-entry.html pub=pub %}{% endfor %}
</ol>

<h2 class="group-heading">presentations</h2>
<div>
{% for c in site.data.cv.conferences %}
  <div class="talk">
    <div class="pub-badge"><abbr>{{ c.year }}</abbr></div>
    <div>
      <div class="pub-title">{{ c.title }}</div>
      <div class="pub-venue"><em>{{ c.event }}</em>, {{ c.place }}, {{ c.year }}</div>
      {% if c.url %}<div class="pub-links"><a class="btn-sm" href="{{ c.url }}" rel="noopener" target="_blank">Program</a></div>{% endif %}
    </div>
  </div>
{% endfor %}
</div>

<h2 class="group-heading">peer review</h2>
<div>
{% for r in site.data.cv.peer_review %}
  <div class="talk">
    <div class="pub-badge"><abbr>{{ r.years }}</abbr></div>
    <div><div class="pub-title">{{ r.journal }}</div></div>
  </div>
{% endfor %}
  <p class="pub-venue">Full record on <a href="https://orcid.org/{{ site.author.orcid }}" rel="noopener" target="_blank">ORCID</a>.</p>
</div>
