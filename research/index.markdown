---
layout: default
title: Research
permalink: /research/
---

# Research

<div class="pub-list">
{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% for p in pubs %}
  <div class="pub">
    <div class="pub-media">
      <img src="{{ p.image | relative_url }}" alt="{{ p.title }}">
    </div>

    <div class="pub-body">
      <div class="pub-title">
        <a href="{{ p.url }}" target="_blank" rel="noopener">{{ p.title }}</a>
      </div>

      <div class="pub-authors">{{ p.authors }}</div>
      <div class="pub-venue"><em>{{ p.venue }}</em>{% if p.year %} · {{ p.year }}{% endif %}</div>

      <div class="pub-summary">{{ p.summary }}</div>

      {% if p.links %}
      <div class="pub-links">
        {% for l in p.links %}
          <a href="{{ l.url }}" target="_blank" rel="noopener">{{ l.name }}</a>{% unless forloop.last %} · {% endunless %}
        {% endfor %}
      </div>
      {% endif %}
    </div>
  </div>
{% endfor %}
</div>
