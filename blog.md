---
layout: default
title: Journal
permalink: /journal/
---

<div style="max-width:900px; margin:0 auto; padding:56px 16px;">
  <h1 style="margin:0 0 12px 0; text-transform:uppercase; letter-spacing:0.06em; font-size:44px;">
    JOURNAL
  </h1>
  <p style="margin:0 0 48px 0; opacity:0.9; max-width:62ch; font-size:18px; line-height:1.6;">
    Notatki z drogi. Rzeczy, które dzieją się pomiędzy projektami.
  </p>

  {% for post in site.posts %}
    <div style="
      display:grid;
      grid-template-columns: 180px 1fr;
      gap:32px;
      margin-bottom:56px;
      align-items:start;
    ">

      {% if post.header.teaser %}
        <a href="{{ post.url | relative_url }}">
          <img
            src="{{ post.header.teaser | relative_url }}"
            alt="{{ post.title }}"
            loading="lazy"
            style="
              width:100%;
              display:block;
              border-radius:14px;
            "
          >
        </a>
      {% endif %}

      <div>
        <h2 style="
          margin:0 0 10px 0;
          font-size:22px;
          letter-spacing:0.04em;
          text-transform:uppercase;
        ">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>

        {% if post.excerpt %}
          <p style="
            margin:0;
            opacity:0.92;
            max-width:60ch;
            font-size:16px;
            line-height:1.6;
          ">
            {{ post.excerpt }}
          </p>
        {% endif %}
      </div>

    </div>
  {% endfor %}
</div>
