---
layout: archive
title: "Achievements"
permalink: /achievements/
author_profile: true
---

{% include base_path %}

{% for cat in site.data.achievements | map: 'category' | uniq %}
{% for item in site.data.achievements %}
  <p>{{ item.title }}</p>
{% endfor %}
{% endfor %}
