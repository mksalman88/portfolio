---
layout: default
title: Bookshelf
permalink: /books/
description: A list of the best books I've held in my hands.
nav: true
nav_order: 5
collection: books
---

<div class="container px-0">
  <div class="row">
    {% assign items = site.books | sort: 'title' %}
    {% for book in items %}
      <div class="col-12 col-sm-6 col-md-4 mb-4 d-flex">
        <div class="card shadow-sm w-100 h-100 border-0">
          {% if book.cover %}
            <img class="card-img-top"
                 src="{{ book.cover | relative_url }}"
                 alt="{{ book.title }} cover"
                 loading="lazy">
          {% endif %}
          <div class="card-body text-center">
            <h6 class="card-title mb-1">{{ book.title }}</h6>
            <p class="card-text text-muted">{{ book.author }}</p>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
</div>

<style>
.card-img-top {
  aspect-ratio: 3 / 4;
  object-fit: cover;
  border-radius: 0.5rem;
}
.card-title {
  font-weight: 700;
  font-size: 1rem;
}
.card-text {
  font-size: .95rem;
  margin-bottom: 0;
}
</style>