---
layout: default
title: Curriculum vitae
subtitle: Print this page for a paper copy.
permalink: /cv
nav_order: 5
description: >-
  Curriculum vitae of Andrei Lepikhov: Staff Software Engineer at pgEdge, previously Postgres Professional and the Academician V.P. Makeyev State Rocket Centre.
---

<p class="meta">{{ site.profile.role }} at {{ site.profile.company }} &middot;
{{ site.profile.location }} &middot;
<a href="mailto:{{ site.profile.email }}">{{ site.profile.email }}</a> &middot;
<a href="https://github.com/danolivo">github.com/danolivo</a></p>

<p class="note">A shorter, one-page version is available as a
<a href="https://github.com/danolivo/resume/blob/master/resume-w.pdf">PDF</a>.</p>

## Experience

{% for e in site.data.cv.experience %}
<div class="project">
  <h3>{{ e.company }}{% if e.period %}<span class="status">{{ e.period }}</span>{% endif %}</h3>
  {%- if e.role %}
  <p class="meta">{{ e.role }}{% if e.kind %} · {{ e.kind }}{% endif %}{% if e.where %} · {{ e.where }}{% endif %}</p>
  {%- endif %}
  {%- if e.body %}<p>{{ e.body }}</p>{% endif %}
  {%- for r in e.roles %}
  <h4>{{ r.role }}</h4>
  <p class="meta">{{ r.period }}{% if r.kind %} · {{ r.kind }}{% endif %}{% if r.where %} · {{ r.where }}{% endif %}</p>
  <p>{{ r.body }}</p>
  {%- endfor %}
</div>
{% endfor %}

## Open source

<p class="note">The planner and executor work below is my own, and runs across
employers rather than belonging to any one of them: the salaried subject is
replication, the contributor subject has been query optimization since 2017.
Upstream history credits me as author on 43 commits and as reviewer on 67, across
PostgreSQL 12 to 19.</p>

{% assign core = site.data.projects | where: "group", "core" %}
{% assign own = site.data.projects | where: "personal", true %}

<h3>In PostgreSQL core</h3>
<ul>
{%- for p in core %}
  <li><strong>{{ p.name }}</strong>{% if p.release %} ({{ p.release }}){% endif %} —
  {{ p.body | strip }}</li>
{%- endfor %}
</ul>

<h3>Open upstream</h3>
<p>{{ site.data.proposals.commitfest | size }} patches in the PostgreSQL commitfest and
one more on the mailing list, neither landed nor rejected — listed with their status
<a href="{{ '/proposed' | relative_url }}">here</a>.</p>

<h3>Extensions of my own</h3>
<ul>
{%- for p in own %}
  <li><strong>{{ p.name }}</strong>{% if p.status %} ({{ p.status }}){% endif %} —
  {{ p.summary | default: p.body }}{% if p.repo %} <a href="{{ p.repo }}">{{ p.repo | remove: "https://github.com/" }}</a>{% endif %}</li>
{%- endfor %}
</ul>

## Education

{% for e in site.data.cv.education %}
<div class="project">
  <h3>{{ e.degree }}<span class="status">{{ e.year }}</span></h3>
  <p class="meta">{{ e.where }}</p>
  {%- if e.body %}<p>{{ e.body }}</p>{% endif %}
</div>
{% endfor %}

## Selected publications

{% assign selected = site.data.publications | where: "type", "journal" | where: "area", "db" %}
{% include biblio.html items=selected %}

<p>Complete list on the <a href="{{ '/publications' | relative_url }}">publications</a> page —
{{ site.data.publications | size }} entries in total, plus
{{ site.data.awards.software | size }} registered software programs and
{{ site.data.awards.grants | size }} grants and awards.</p>

## Talks

<p>{{ site.data.talks | size }} conference and meetup talks between
{% assign years = site.data.talks | map: "year" | sort %}{{ years | first }} and
{{ years | last }} — see the <a href="{{ '/talks' | relative_url }}">talks</a> page.</p>

## Core competencies

<ul>
{%- for c in site.data.cv.competencies %}
  <li><strong>{{ c.label }}:</strong> {{ c.items }}</li>
{%- endfor %}
</ul>

## Certifications

<ul>
{%- for c in site.data.cv.certifications %}
  <li>{{ c.year }} — {{ c.title }}</li>
{%- endfor %}
</ul>
