---
title: "Talks, conferences, and schools"
permalink: /talks/
author_profile: true
---

{% assign talks = site.talks | sort: "date" | reverse %}
{% for post in talks %}
  {% include archive-single-talk.html %}
{% endfor %}
