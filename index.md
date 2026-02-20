---
layout: home
title: Roweryskladane.pl
excerpt: "\"Składaki\" to coraz popularniejsze połączenie przyjemności z jazdy, miejskiej mobilności i wyjątkowego stylu."
classes: wide
entries_layout: grid
header:
  overlay_image: /assets/hero.JPG
  overlay_filter: 0.25
  overlay_position: "right center"
  actions:
    - label: "Recenzje"
      url: "/projekty/"
    - label: "Artykuły"
      url: "/journal/"
---
{% assign latest_post = site.posts.first %}

{% assign sorted_projects = site.projects | sort: "date" %}
{% assign latest_project = sorted_projects | last %}
{% if latest_project == nil %}
  {% assign latest_project = site.projects.first %}
{% endif %}

<div style="max-width:920px; margin: 34px auto 0 auto;">

  <div style="display:grid; grid-template-columns: 1fr 1fr 1fr; gap:22px;">

    <!-- Latest Project -->
    <a href="{{ latest_project.url | relative_url }}" style="display:block; text-decoration:none;">
      <div style="border:1px solid rgba(255,255,255,.10); border-radius:16px; overflow:hidden; background:rgba(255,255,255,.03); height:100%;">
        {% if latest_project.header.teaser %}
          <img src="{{ latest_project.header.teaser | relative_url }}" alt="" loading="lazy" style="width:100%; height:200px; object-fit:cover; display:block;">
        {% endif %}
        <div style="padding:16px 16px 18px 16px;">
          <div style="font-size:12px; letter-spacing:.08em; text-transform:uppercase; opacity:.7; margin-bottom:6px;">
            Latest work
          </div>
          <div style="font-size:17px; font-weight:700; letter-spacing:.02em; text-transform:uppercase; margin-bottom:8px;">
            {{ latest_project.title }}
          </div>
          {% if latest_project.excerpt %}
            <div style="opacity:.85; line-height:1.6;">
              {{ latest_project.excerpt | strip_html | truncate: 100 }}
            </div>
          {% endif %}
        </div>
      </div>
    </a>

    <!-- Latest Journal -->
    <a href="{{ latest_post.url | relative_url }}" style="display:block; text-decoration:none;">
      <div style="border:1px solid rgba(255,255,255,.10); border-radius:16px; overflow:hidden; background:rgba(255,255,255,.03); height:100%;">
        {% if latest_post.header.teaser %}
          <img src="{{ latest_post.header.teaser | relative_url }}" alt="" loading="lazy" style="width:100%; height:200px; object-fit:cover; display:block;">
        {% endif %}
        <div style="padding:16px 16px 18px 16px;">
          <div style="font-size:12px; letter-spacing:.08em; text-transform:uppercase; opacity:.7; margin-bottom:6px;">
            Latest journal
          </div>
          <div style="font-size:17px; font-weight:700; letter-spacing:.02em; text-transform:uppercase; margin-bottom:8px;">
            {{ latest_post.title }}
          </div>
          {% if latest_post.excerpt %}
            <div style="opacity:.85; line-height:1.6;">
              {{ latest_post.excerpt | strip_html | truncate: 100 }}
            </div>
          {% endif %}
        </div>
      </div>
    </a>

    <!-- About -->
    <a href="{{ '/about/' | relative_url }}" style="display:block; text-decoration:none;">
      <div style="border:1px solid rgba(255,255,255,.10); border-radius:16px; overflow:hidden; background:rgba(255,255,255,.03); height:100%; display:flex; flex-direction:column; justify-content:center;">
        <div style="padding:28px 22px; text-align:center;">
          <img src="{{ '/assets/logo.png' | relative_url }}" alt="ANTY" style="width:96px; height:auto; margin-bottom:16px;">
          <div style="font-size:12px; letter-spacing:.08em; text-transform:uppercase; opacity:.7; margin-bottom:8px;">
            About
          </div>
          <div style="opacity:.85; line-height:1.6;">
            Manifest, podejście i kontakt.  
            Dlaczego robimy to w ten sposób.
          </div>
        </div>
      </div>
    </a>

  </div>

  <div style="display:flex; justify-content:space-between; gap:14px; margin-top:16px; opacity:.85;">
    <a href="{{ '/projekty/' | relative_url }}" style="text-decoration:none;">→ Zobacz Work</a>
    <a href="{{ '/journal/' | relative_url }}" style="text-decoration:none;">→ Zobacz Journal</a>
  </div>

</div>

<style>
@media (max-width: 900px){
  div[style*="grid-template-columns: 1fr 1fr 1fr"]{
    grid-template-columns: 1fr !important;
  }
}
</style>
