---
layout: default
title: Projects
---

# Projects

A curated list of things I’ve built. Each project page has stack details, links, and what I learned.

<div class="row g-3">
  {% assign sorted = site.projects | sort: "order" %}
  {% for p in sorted %}
    <div class="col-12 col-md-6">
      <div class="card h-100">
        <div class="card-body">
          <h3 class="h5 card-title mb-2">{{ p.title }}</h3>
          {% if p.tagline %}
            <p class="card-text mb-2">{{ p.tagline }}</p>
          {% endif %}

          <div class="d-flex flex-wrap gap-2 mb-3">
            {% if p.stack %}
              {% for tech in p.stack %}
                <span class="badge text-bg-light border">{{ tech }}</span>
              {% endfor %}
            {% endif %}
          </div>

          <a class="btn btn-sm btn-dark" href="{{ p.url }}">Read more</a>
          {% if p.live %}
            <a class="btn btn-sm btn-outline-dark" href="{{ p.live }}" target="_blank" rel="noopener">Live</a>
          {% endif %}
          {% if p.repo %}
            <a class="btn btn-sm btn-outline-dark" href="{{ p.repo }}" target="_blank" rel="noopener">Repo</a>
          {% endif %}
        </div>
      </div>
    </div>
{% endfor %}
</div>