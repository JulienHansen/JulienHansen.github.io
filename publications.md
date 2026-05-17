---
layout: default
title: Publications
permalink: /publications/
---

# Publications

My list of papers, preprints, and notes.

{% assign sorted_pubs = site.publications | sort: 'date' | reverse %}
{% for pub in sorted_pubs %}
<div class="publication">
  <p class="publication-title">
    {{ pub.title }}
    {% if pub.status %}<span class="publication-status status-{{ pub.status }}">{{ pub.status | replace: '-', ' ' }}</span>{% endif %}
  </p>
  <p class="publication-authors">{{ pub.authors }}</p>
  <p class="publication-venue">{{ pub.venue }} · {{ pub.date | date: "%Y" }}</p>
  {% if pub.links and pub.links.size > 0 %}
  <p class="publication-links">
    {% for link in pub.links %}<a href="{{ link.url }}">{{ link.name }}</a>{% endfor %}
  </p>
  {% endif %}
  {% assign abstract = pub.content | strip %}
  {% if abstract != "" %}
  <details class="publication-abstract">
    <summary>Abstract</summary>
    <div class="abstract-content">{{ pub.content }}</div>
  </details>
  {% endif %}
</div>
{% endfor %}
