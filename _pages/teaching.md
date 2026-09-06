---
title: "Teaching"
permalink: /teaching/
layout: single
author_profile: true
---

{% assign current_teaching = site.teaching | where: "status", "current" | sort: "date" | reverse %}
{% if current_teaching.size > 0 %}
<ul class="teaching-list">
{% for item in current_teaching %}
  <li>
    <strong>{{ item.title }}</strong>{% if item.venue %} — {{ item.venue }}{% endif %}
    {% if item.type %}<br><span class="teaching-meta">{{ item.type }}</span>{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}

## Past courses

{% assign past_teaching = site.teaching | where: "status", "past" | sort: "date" | reverse %}
<ul class="teaching-list">
{% for item in past_teaching %}
  <li>
    <strong>{{ item.title }}</strong>{% if item.venue %} — {{ item.venue }}{% endif %}
    {% if item.type %}<br><span class="teaching-meta">{{ item.type }}</span>{% endif %}
  </li>
{% endfor %}
</ul>
