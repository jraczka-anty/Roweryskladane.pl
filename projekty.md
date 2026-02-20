---
layout: default
title: Work
permalink: /projekty/
---

<div style="max-width:900px; margin:0 auto; padding:56px 16px 24px 16px;">
  <h1 style="margin:0 0 10px 0; text-transform:uppercase; letter-spacing:0.06em; font-size:44px; line-height:1.05;">
    NASZA DROGA
  </h1>
  <p style="margin:0; opacity:0.9; max-width:62ch; font-size:18px; line-height:1.6;">
    Od ram rowerowych po mobilne projekty. Wszystko zaczyna się w ruchu.
  </p>
</div>

{% for project in site.projects %}
  <div style="max-width:900px; margin:0 auto; padding:24px 16px 56px 16px; border-bottom:1px solid rgba(255,255,255,0.08);">
    
    {% if project.header.teaser %}
      <a href="{{ project.url | relative_url }}" style="display:block; margin-bottom:18px;">
        <img
          src="{{ project.header.teaser | relative_url }}"
          alt="{{ project.title }}"
          loading="lazy"
          style="width:100%; display:block; border-radius:18px;"
        >
      </a>
    {% endif %}

    <h2 style="margin:0 0 8px 0; text-transform:uppercase; letter-spacing:0.04em; font-size:22px;">
      <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    </h2>

    {% if project.excerpt %}
      <p style="margin:0; opacity:0.92; max-width:58ch; font-size:16px; line-height:1.6;">
        {{ project.excerpt }}
      </p>
    {% endif %}

  </div>
{% endfor %}
