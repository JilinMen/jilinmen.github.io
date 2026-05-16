---
permalink: /
title:
layout: single
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
{% assign profile = site.data.profile %}

<section class="home-section home-intro" id="about">
  <div class="section-heading section-heading--center">
    <h2>{{ profile.headline | default: "About me" }}</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <div class="home-summary">
    {{ profile.summary | markdownify }}
  </div>
</section>

{% if profile.news %}

<section class="home-section" id="news">
  <div class="section-heading section-heading--center">
    <h2>News</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <ol class="news-list">
    {% for item in profile.news %}
      <li>
        <time>{{ item.date }}</time>
        <span>{{ item.text | markdownify | remove: '<p>' | remove: '</p>' }}</span>
      </li>
    {% endfor %}
  </ol>
</section>
{% endif %}

{% if profile.publications %}

<h3 class="subtle-heading">Publications</h3>
  {% for group in profile.publications %}
    <h3 class="publication-year-heading">{{ group.year }}</h3>
    <div class="publication-list">
      {% for paper in group.items %}
        <article class="publication-item{% if paper.highlight %} publication-item--highlight{% endif %}">
          <div class="publication-meta">
            <span>{{ paper.venue }}</span>
            {% if paper.role %}<span>{{ paper.role }}</span>{% endif %}
          </div>
          <h4>{{ paper.title }}</h4>
          <p>{{ paper.authors }}</p>
          {% if paper.doi %}
            <a class="text-link" href="{{ paper.doi }}" target="_blank" rel="noopener">DOI</a>
          {% endif %}
        </article>
      {% endfor %}
    </div>
  {% endfor %}
</section>
{% endif %}

{% if profile.apps %}

<section class="home-section" id="apps">
  <div class="section-heading section-heading--center">
    <h2>Apps & Tools</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <div class="card-grid">
    {% for app in profile.apps %}
      <article class="project-card">
        <div>
          <h3>{{ app.name }}</h3>
          <p>{{ app.description }}</p>
        </div>
        {% if app.url %}
          <a class="text-link" href="{{ app.url }}" target="_blank" rel="noopener">Launch app</a>
        {% endif %}
      </article>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if profile.presentations %}

<section class="home-section" id="presentations">
  <div class="section-heading section-heading--center">
    <h2>Conference Presentations</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <ul class="compact-list">
    {% for talk in profile.presentations %}
      <li>
        <strong>{{ talk.year }}</strong>
        <span>{{ talk.text }}</span>
      </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

{% if profile.training %}

<section class="home-section" id="training">
  <div class="section-heading section-heading--center">
    <h2>Workshops & Training</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <ul class="compact-list">
    {% for item in profile.training %}
      <li>
        <strong>{{ item.date }}</strong>
        <span>{{ item.text }}</span>
      </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

{% if profile.honors %}

<section class="home-section" id="honors">
  <div class="section-heading section-heading--center">
    <h2>Awards & Honors</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <div class="timeline-list">
    {% for honor in profile.honors %}
      <div class="timeline-item">
        <span>{{ honor.year }}</span>
        <p>{{ honor.text }}</p>
      </div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if profile.service %}

<section class="home-section" id="service">
  <div class="section-heading section-heading--center">
    <h2>Academic Service</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>

  {% if profile.service.reviewing %}
    `<h3 class="subtle-heading">`Journal Reviewer`</h3>`
    `<ul class="plain-list">`
      {% for journal in profile.service.reviewing %}
        `<li>`{{ journal }}`</li>`
      {% endfor %}
    `</ul>`
  {% endif %}

  {% if profile.service.guest_editor %}
    `<h3 class="subtle-heading">`Guest Editor for Special Issues`</h3>`
    `<ul class="compact-list">`
      {% for item in profile.service.guest_editor %}
        `<li>`
          `<strong>`{{ item.year }}`</strong>`
          `<span>`{{ item.text }}
        `</li>`
      {% endfor %}
    `</ul>`
  {% endif %}

</section>
{% endif %}

<section class="home-section visitor-map-section" id="visitor-map">
  <div class="section-heading section-heading--center">
    <h2>Visitor Map</h2>
    <span class="section-rule" aria-hidden="true"></span>
  </div>
  <div class="visitor-map-frame">
    <script type="text/javascript" id="clustrmaps"
            src="https://clustrmaps.com/map_v2.js?d=S_BcfnqEHHFLFetUdLEM2o_pLXucxLV_u_Lsn-B9GIU&cl=00cc66&w=300&t=tt">
    </script>
    <noscript>
      <a href="https://clustrmaps.com/map_v2.js?d=S_BcfnqEHHFLFetUdLEM2o_pLXucxLV_u_Lsn-B9GIU&cl=00cc66&w=300&t=tt"
         target="_blank" rel="noopener">View visitor map</a>
    </noscript>
  </div>
</section>
