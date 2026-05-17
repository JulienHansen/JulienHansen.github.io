---
layout: default
title: Projects
permalink: /projects/
---

# Projects

Code, tools, and explorations. Some are tied to a paper, some are not.

{% assign sorted_projects = site.projects | sort: 'date' | reverse %}
{% for project in sorted_projects %}
<div class="project">
  <p class="project-title">
    {{ project.title }}
    {% if project.status %}<span class="project-status status-{{ project.status }}">{{ project.status }}</span>{% endif %}
  </p>
  <p class="project-desc">{{ project.description }}</p>
  {% if project.tags and project.tags.size > 0 %}
  <p class="project-tags">{% for t in project.tags %}<span class="project-tag">{{ t }}</span>{% endfor %}</p>
  {% endif %}
  {% if project.links and project.links.size > 0 %}
  <p class="project-links">
    {% for link in project.links %}<a href="{{ link.url }}">{{ link.name }}</a>{% endfor %}
  </p>
  {% endif %}
</div>
{% endfor %}
