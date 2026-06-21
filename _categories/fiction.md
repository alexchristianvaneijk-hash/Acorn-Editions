---
layout: catalog
title: Fiction
slug: /fiction/
category: fiction
---

{% assign books = site.books | where: "category", "fiction" %}

{% for book in books %}

<div class="book"
     data-search="{{ book.title | downcase }} {{ book.author | downcase }} {{ book.description | downcase }}">

    <a href="{{ book.url }}">

        <div class="cover">
            <img src="{{ book.cover_image }}" alt="{{ book.title }}">
        </div>

        <div class="title">{{ book.title }}</div>
        <div class="author">{{ book.author }}</div>

    </a>

</div>

{% endfor %}
