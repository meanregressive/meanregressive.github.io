---
layout: publications
title: "Publications"
description: "Working papers, journal articles, and reports — 2020–2025."
permalink: /publications/
---

## Working Papers

{% assign wps = site.data.publications | where: "type", "W" %}
<ol class="pub-list">
{% for pub in wps %}
  {% include pub-entry.html pub=pub %}
{% endfor %}
</ol>

## Journal Articles

{% assign journals = site.data.publications | where: "type", "J" %}
<ol class="pub-list">
{% for pub in journals %}
  {% include pub-entry.html pub=pub %}
{% endfor %}
</ol>

## Reports &amp; Briefs

{% assign reports = site.data.publications | where: "type", "R" %}
<ol class="pub-list">
{% for pub in reports %}
  {% include pub-entry.html pub=pub %}
{% endfor %}
</ol>
