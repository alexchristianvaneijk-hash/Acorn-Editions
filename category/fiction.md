---
layout: catalog
title: Fiction
permalink: /fiction/
category: fiction
theme: main
---

{% assign books = site.books | where: "category", "fiction" %}

{% for book in books %}

<div class="feature-card"
     data-genre="{{ book.genre | downcase }}"
     data-tags="{{ book.tags | join: ' ' | downcase }}"
     data-search="{{ book.title | downcase }} {{ book.author | downcase }} {{ book.description | downcase }} {{ book.tags | join: ' ' | downcase }}">

  <a class="card-link-overlay" href="{{ book.url }}"></a>

  <div class="cover-wrapper">
    <img src="{{ book.cover_image }}" alt="{{ book.title }}">
    <div class="book-type">{{ book.type }}</div>
  </div>

  <h4>{{ book.title }}</h4>
  <p>{{ book.author }}</p>

  <div class="download-buttons">
    <a href="{{ book.epub_file }}" class="download-btn">EPUB</a>
    <a href="{{ book.pdf_file }}" class="download-btn">PDF</a>
  </div>

</div>

{% endfor %}
