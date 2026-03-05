---
layout: page
title: "Essays"
description: "Long-form writing on gender, development economics, and research methods."
permalink: /blog/
---

<p class="blog-intro">
  Occasional essays on gender equality, women's economic empowerment, violence prevention,
  and the craft of doing development research. A place to step back from the weeds of
  analysis and think about what it all means.
</p>

{% if paginator.posts and paginator.posts.size > 0 %}
  <ul class="post-list">
    {% for post in paginator.posts %}
    <li class="post-list-item">
      <p class="post-list-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
        {% if post.categories and post.categories.size > 0 %}
          &ensp;&middot;&ensp;
          {% for cat in post.categories %}
            <span class="post-category">{{ cat }}</span>
          {% endfor %}
        {% endif %}
      </p>
      <h2 class="post-list-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      {% if post.description %}
        <p class="post-list-excerpt">{{ post.description }}</p>
      {% else %}
        <p class="post-list-excerpt">{{ post.excerpt | strip_html | truncatewords: 40 }}</p>
      {% endif %}
      <a href="{{ post.url | relative_url }}" class="post-list-readmore">Read &rarr;</a>
    </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
  <nav class="pagination" aria-label="Pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}">&larr; Newer</a>
    {% else %}
      <span>&larr; Newer</span>
    {% endif %}

    <span class="current">Page {{ paginator.page }} of {{ paginator.total_pages }}</span>

    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}">Older &rarr;</a>
    {% else %}
      <span>Older &rarr;</span>
    {% endif %}
  </nav>
  {% endif %}

{% elsif site.posts.size > 0 %}
  <ul class="post-list">
    {% for post in site.posts %}
    <li class="post-list-item">
      <p class="post-list-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
        {% if post.categories and post.categories.size > 0 %}
          &ensp;&middot;&ensp;
          {% for cat in post.categories %}
            <span class="post-category">{{ cat }}</span>
          {% endfor %}
        {% endif %}
      </p>
      <h2 class="post-list-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      {% if post.description %}
        <p class="post-list-excerpt">{{ post.description }}</p>
      {% else %}
        <p class="post-list-excerpt">{{ post.excerpt | strip_html | truncatewords: 40 }}</p>
      {% endif %}
      <a href="{{ post.url | relative_url }}" class="post-list-readmore">Read &rarr;</a>
    </li>
    {% endfor %}
  </ul>

{% else %}
  <p style="color: var(--color-text-muted); font-style: italic;">No essays yet. Check back soon.</p>
{% endif %}
