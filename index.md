---
layout: home
title: "Home"
permalink: /
---

<section class="home-hero">
  <h1 class="hero-name">Deboleena Rakshit</h1>
  <p class="hero-role">Research Analyst II, IFPRI &ensp;&middot;&ensp; Washington, DC</p>
  <p class="hero-tagline">I came to econometrics through literature and international relations.</p>
  <ul class="hero-links">
    <li><a href="mailto:{{ site.author.email }}">Email</a></li>
    <li><a href="{{ '/cv/' | relative_url }}">CV</a></li>
    <li><a href="https://github.com/{{ site.author.github }}" rel="noopener" target="_blank">GitHub</a></li>
    <li><a href="https://www.linkedin.com/in/{{ site.author.linkedin }}/" rel="noopener" target="_blank">LinkedIn</a></li>
    <li><a href="https://bsky.app/profile/{{ site.author.bluesky }}" rel="noopener" target="_blank">Bluesky</a></li>
  </ul>
</section>

<section class="home-statement">
  <p>
    I am a researcher at the <a href="https://www.ifpri.org" rel="noopener" target="_blank">International Food Policy Research Institute</a>,
    where I evaluate the impacts of social protection and livelihoods programs on gender equality,
    poverty, and household resilience. My work spans randomized controlled trials in Bangladesh, Somalia,
    and Mozambique, as well as large-scale administrative data analysis. Gender-based violence, women's
    labor force participation and economic empowerment, and the conditions under which interventions
    produce durable behavioral change are the questions that animate most of my work.
  </p>
  <p>
    Before becoming an economist, I studied English literature in Kolkata and international relations
    at Johns Hopkins SAIS. I spent four years at Equimundo working on gender attitudes and masculinities
    research across more than thirty countries. In 2025 I completed graduate coursework in Linear Algebra,
    Multivariable Calculus, and Real Analysis at American University in preparation for a PhD in Economics.
    The disciplines have layered rather than replaced one another: close reading and textual evidence,
    policy context and institutional analysis, and now formal quantitative methods.
  </p>
</section>

<section class="home-recent-work">
  <p class="section-label">Recent work</p>
  {% assign recent_pubs = site.data.publications | slice: 0, 3 %}
  {% for pub in recent_pubs %}
    <div class="recent-pub">
      <span class="pub-type-badge badge-{{ pub.type | downcase }}">{{ pub.type }}</span>
      <div>
        {% if pub.url %}
          <a href="{{ pub.url }}" rel="noopener" target="_blank">{{ pub.title }}</a>
        {% else %}
          {{ pub.title }}
        {% endif %}
        <br>
        <span style="font-family: var(--font-sans); font-size: var(--font-size-sm); color: var(--color-text-muted);">
          {{ pub.venue }} ({{ pub.year }})
        </span>
      </div>
    </div>
  {% endfor %}
  <a href="{{ '/publications/' | relative_url }}" class="view-all">View all publications &rarr;</a>
</section>

{% if site.posts.size > 0 %}
<section class="home-latest-essay">
  <p class="section-label">Latest essay</p>
  {% assign latest = site.posts.first %}
  <p class="essay-date">{{ latest.date | date: "%B %-d, %Y" }}</p>
  <h2 class="essay-title"><a href="{{ latest.url | relative_url }}">{{ latest.title }}</a></h2>
  {% if latest.description %}
    <p class="essay-excerpt">{{ latest.description }}</p>
  {% else %}
    <p class="essay-excerpt">{{ latest.excerpt | strip_html | truncatewords: 40 }}</p>
  {% endif %}
  <a href="{{ latest.url | relative_url }}" class="read-more">Read &rarr;</a>
</section>
{% endif %}
