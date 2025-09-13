---
layout: archive
title: "Achievements"
permalink: /achievements/
author_profile: true
---
{% include base_path %}

<!-- ===== 1. Projects & Papers ===== -->
<h3 id="project">Projects & Papers</h3>
{% for item in site.data.achievements | where: "category", "project" %}
  <div class="achieve-row">
    {% if item.logo %}
      <div class="achieve-logo">
        <img src="{{ item.logo | prepend: '/images/achievements/' | relative_url }}" alt="{{ item.title }}">
      </div>
    {% endif %}
    <div class="achieve-text {% unless item.logo %}no-logo{% endunless %}">
      <h4>{{ item.title }}</h4>
      <p class="year">{{ item.year }}</p>
      {% if item.authors %}<p class="authors"><strong>Authors:</strong> {{ item.authors }}</p>{% endif %}
      {% if item.advisor %}<p class="advisor"><strong>Advisor:</strong> {{ item.advisor }}</p>{% endif %}
      {% if item.desc %}<p class="desc">{{ item.desc | markdownify }}</p>{% endif %}
      {% if item.outcome %}<p class="outcome"><strong>Outcome:</strong> {{ item.outcome | markdownify }}</p>{% endif %}
    </div>
  </div>
{% endfor %}
