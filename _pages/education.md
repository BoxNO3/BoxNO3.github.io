---
layout: archive
title: "Education"
permalink: /education/
author_profile: true
---

{% include base_path %}

## Education Experience

{% for edu in site.data.education %}
<div class="edu-row">
  <div class="edu-logo">
    <img src="{{ edu.logo | prepend: '/images/edu-logos/' | relative_url }}" alt="{{ edu.institution }} logo">
  </div>
  <div class="edu-text">
    <h3>{{ edu.degree }}</h3>
    <p class="institution">{{ edu.institution }}</p>
    <p class="date">{{ edu.period }}</p>
    {% if edu.description %}<p class="description">{{ edu.description }}</p>{% endif %}
  </div>
</div>
{% endfor %}
