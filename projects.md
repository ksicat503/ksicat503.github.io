---
layout: page
title: Projects
---

<div class="projects-grid">
  {% for project in site.data.projects %}
  <article class="card">
    <h2 class="card__title">
      {% if project.in_progress %}
        {{ project.title }}
      {% else %}
        <a href="{{ project.url }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a>
      {% endif %}
    </h2>
    <p class="card__description">{{ project.description }}</p>
    {% if project.tags %}
    <div class="card__tags">
      {% for tag in project.tags %}
      <span class="card__tag">{{ tag }}</span>
      {% endfor %}
      {% if project.in_progress %}<span class="card__tag card__tag--wip">In Progress</span>{% endif %}
    </div>
    {% endif %}
    {% if project.app_url %}
    <a class="card__link" href="{{ project.app_url }}" target="_blank" rel="noopener noreferrer">
      Try it here
    </a>
    {% endif %}
    {% unless project.in_progress %}
    <a class="card__link" href="{{ project.url }}" target="_blank" rel="noopener noreferrer">
      <svg aria-hidden="true" width="1em" height="1em">
        <use href="{{ '/assets/fontawesome/icons.svg' | relative_url }}#github"></use>
      </svg>
      View on GitHub
    </a>
    {% endunless %}
  </article>
  {% endfor %}
</div>
