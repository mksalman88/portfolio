---
layout: page
title: "Poetry"
permalink: /poetry/
category: Personal
---

<div class="row">
  {% assign poems = site.projects | where: "project-type", "poetry" %}
  {% for poem in poems %}
    <div class="col-sm-6 col-md-4 mb-4">
      <div class="card h-100">
        <a href="{{ poem.url | relative_url }}">
          {% if poem.image %}
            <img class="card-img-top" src="{{ poem.image | relative_url }}" alt="{{ poem.title }}">
          {% endif %}
          <div class="card-body text-center">
            <h5 class="card-title">{{ poem.title }}</h5> <!-- Each card shows the correct poem title -->
          </div>
        </a>
      </div>
    </div>
  {% endfor %}
</div>