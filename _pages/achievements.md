---
layout: archive
title: "Achievements"
permalink: /achievements/
author_profile: true
---

{% include base_path %}

{% for item in site.data.achievements %}
  <p>{{ item.title }}</p>
{% endfor %}
