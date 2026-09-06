---
title: "Research"
permalink: /research/
layout: single
author_profile: true
---

## Publications

{% include base_path %}

{% if site.author.googlescholar %}
<p class="publication-scholar-link">
  See also my
  <a href="{{ site.author.googlescholar }}">Google Scholar profile</a>.
</p>
{% endif %}

{% assign pubs = site.publications | sort: "date" | reverse %}

{% assign journal_pubs = site.publications | where: "pubtype", "J" %}
{% assign conference_pubs = site.publications | where: "pubtype", "C" %}
{% assign preprint_pubs = site.publications | where: "pubtype", "P" %}
{% assign dissertation_pubs = site.publications | where: "pubtype", "D" %}

{% assign jnum = journal_pubs | size %}
{% assign cnum = conference_pubs | size %}
{% assign pnum = preprint_pubs | size %}
{% assign dnum = dissertation_pubs | size %}

<div class="publication-list">

{% for post in pubs %}

  {% assign pubnumber = "" %}

  {% case post.pubtype %}
    {% when "J" %}
      {% assign pubnumber = "J" | append: jnum %}
      {% assign jnum = jnum | minus: 1 %}

    {% when "C" %}
      {% assign pubnumber = "C" | append: cnum %}
      {% assign cnum = cnum | minus: 1 %}

    {% when "P" %}
      {% assign pubnumber = "P" | append: pnum %}
      {% assign pnum = pnum | minus: 1 %}

    {% when "D" %}
      {% assign pubnumber = "D" | append: dnum %}
      {% assign dnum = dnum | minus: 1 %}
  {% endcase %}

  <div class="publication-item">

    <div class="publication-title-line">
      <span class="publication-number">[{{ pubnumber }}]</span>

      {% if post.paperurl %}
        <a class="publication-title"
           href="{{ post.paperurl }}"
           target="_blank"
           rel="noopener noreferrer">
          {{ post.title }}
        </a>
      {% else %}
        <span class="publication-title">{{ post.title }}</span>
      {% endif %}
    </div>

    {% if post.authors %}
      <div class="publication-authors">
        {{ post.authors }}
      </div>
    {% endif %}

    {% if post.venue %}
      <div class="publication-venue">
        {{ post.venue }}
      </div>
    {% endif %}

  </div>

{% endfor %}

</div>