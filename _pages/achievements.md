---
layout: archive
title: "Achievements"
permalink: /achievements/
author_profile: true
---
#{{ site.data.achievements | inspect }}
{% include base_path %}

{% for cat in "project,prize" %}
  {% assign items = site.data.achievements | where: "category", cat %}
  {% if items.size > 0 %}
    <h3 id="{{ cat }}">{{ cat | replace: 'project', 'Projects & Prizes' | replace: 'prize', 'Honors & Awards' | replace: 'leadership', 'Leadership' }}</h3>

    {% for item in items %}
    <div class="achieve-row">
      <div class="achieve-logo">
        <img src="{{ item.logo | prepend: '/images/achievements/' | relative_url }}" alt="{{ item.title }}">
      </div>
      <div class="achieve-text">
        <h4>{{ item.title }}</h4>
        <p class="year">{{ item.year }}</p>
        {% if item.authors %}<p class="authors"><strong>Authors:</strong> {{ item.authors }}</p>{% endif %}
        {% if item.advisor %}<p class="advisor"><strong>Advisor:</strong> {{ item.advisor }}</p>{% endif %}
        <p class="desc">{{ item.desc | markdownify }}</p>
        <p class="outcome">{{ item.outcome | markdownify }}</p>
      </div>
    </div>
    {% endfor %}
  {% endif %}
{% endfor %}
