---
layout: archive
title: "Education"
permalink: /education/
author_profile: true
---

{% include base_path %}

## Education Experience

{% for edu in site.data.education %}
  {% if edu.type == 'exchange' %}
  <h4 style="margin-top:2rem;">Exchange & Summer Schools</h4>
  {% endif %}

  <div class="edu-row {% if edu.type == 'exchange' %}edu-exchange{% endif %}">
    <div class="edu-logo">
      <img src="{{ edu.logo | prepend: '/images/' | relative_url }}" alt="{{ edu.institution }} logo">
    </div>
    <div class="edu-text">
      <h3>{{ edu.degree }}</h3>
      <p class="institution">{{ edu.institution }}</p>
      <p class="date">{{ edu.period }}</p>
      {% if edu.description %}<p class="description">{{ edu.description }}</p>{% endif %}
    </div>
  </div>
{% endfor %}
