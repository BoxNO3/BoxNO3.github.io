---
layout: archive
title: "Achievements"
permalink: /achievements/
author_profile: true
---

{% include base_path %}
{% for cat in "project,prize" %}
{% assign items = site.data.achievements | where: "category", cat %}

{% if items.size > 0 %}
{% if cat == "project" %}
<h3 id="project">Projects & Papers</h3>
{% for item in items %}
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
{% else %}{% comment %} ====== prize 简洁列表 ====== {% endcomment %}
<h3 id="prize">Honors & Awards</h3>
<ul class="award-list">
{% for item in items %}
<li><strong>{{ item.title }}</strong>&nbsp;&nbsp;{{ item.year }}</li>
{% endfor %}
</ul>
{% endif %}
{% endif %}
{% endfor %}
