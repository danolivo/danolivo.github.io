---
layout: default
title: Projects
subtitle: Database systems, PostgreSQL extensions and planner experiments.
permalink: /projects
nav_order: 1
description: >-
  PostgreSQL work by Andrei Lepikhov: Spock logical replication, pg_track_optimizer, pg_index_stats, pg_middleout, Switch Join, and self-join removal in core.
---

<p class="note">Two threads run through this page. Logical replication is what I am
paid to work on — currently Spock at pgEdge. The planner and executor are what I
work on as a PostgreSQL contributor, and they account for everything under core,
the extensions in my own account, and the experiments at the bottom.</p>

{% assign tools = site.data.projects | where: "group", "tool" %}
{% assign core = site.data.projects | where: "group", "core" %}
{% assign systems = site.data.projects | where: "group", "system" %}
{% assign extensions = site.data.projects | where: "group", "extension" %}
{% assign prototypes = site.data.projects | where: "group", "prototype" %}

## Published regularly

{% for p in tools %}
<div class="project">
  <h3>{{ p.name }}{% if p.status %}<span class="status">{{ p.status }}</span>{% endif %}</h3>
  <p>{{ p.body }}</p>
  <p class="meta">
    {%- for l in p.links %}{% unless forloop.first %} &middot; {% endunless %}<a href="{{ l.url }}">{{ l.name }}</a>{% endfor -%}
  </p>
</div>
{% endfor %}

## In PostgreSQL core

{% for p in core %}
<div class="project">
  <h3>{{ p.name }}</h3>
  <p>{{ p.body }}</p>
  {%- if p.links %}
  <p class="meta">
    {%- for l in p.links %}{% unless forloop.first %} &middot; {% endunless %}<a href="{{ l.url }}">{{ l.name }}</a>{% endfor -%}
  </p>
  {%- endif %}
</div>
{% endfor %}

## Extensions

{% for p in extensions %}
<div class="project">
  <h3>{{ p.name }}{% if p.status %}<span class="status">{{ p.status }}</span>{% endif %}</h3>
  {%- if p.years %}<p class="meta">{{ p.years }}</p>{% endif %}
  <p>{{ p.body }}</p>
  <p class="meta">
    {%- if p.repo %}<a href="{{ p.repo }}">repository</a>{% endif -%}
    {%- for l in p.links %} &middot; <a href="{{ l.url }}">{{ l.name }}</a>{% endfor -%}
  </p>
</div>
{% endfor %}

## Systems

{% for p in systems %}
<div class="project">
  <h3>{{ p.name }}{% if p.status %}<span class="status">{{ p.status }}</span>{% endif %}</h3>
  {%- if p.years %}<p class="meta">{{ p.years }}</p>{% endif %}
  <p>{{ p.body }}</p>
  <p class="meta">
    {%- if p.repo %}<a href="{{ p.repo }}">repository</a>{% endif -%}
    {%- for l in p.links %}{% unless forloop.first and p.repo == nil %} &middot; {% endunless %}<a href="{{ l.url }}">{{ l.name }}</a>{% endfor -%}
  </p>
</div>
{% endfor %}

## Planner experiments

<p class="note">Optimizer ideas explored as branches and prototypes. Some are on their
way into PostgreSQL, some are dead ends kept for the record.</p>

{% for p in prototypes %}
<div class="project">
  <h3>{{ p.name }}</h3>
  <p>{{ p.body }}</p>
  <p class="meta">
    {%- for l in p.links %}{% unless forloop.first %} &middot; {% endunless %}<a href="{{ l.url }}">{{ l.name }}</a>{% endfor -%}
  </p>
</div>
{% endfor %}
