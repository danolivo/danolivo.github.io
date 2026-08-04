---
layout: default
title: Andrei Lepikhov
description: >-
  Andrei Lepikhov: PostgreSQL contributor since 2017 on the query planner and executor, and Staff Software Engineer at pgEdge on logical replication.
---

<div class="intro">
  <img class="portrait" src="{{ '/assets/img/portrait.jpg' | relative_url }}"
       width="900" height="675"
       alt="Andrei Lepikhov at his laptop, a PostgreSQL elephant sticker on the lid">
  <div class="intro-text">
    <h1>Andrei Lepikhov</h1>
    <p class="lede">Database systems engineer and PostgreSQL contributor since 2017. At
    {{ site.profile.company }} I work on active-active logical replication; as a contributor
    my own subject is the query planner and executor.</p>
    <p>Two tracks, not one. Replication is the day job. The planner work — self-join removal,
    GROUP BY ordering, cardinality estimation, pre-sorted paths — is what I take to
    pgsql-hackers, and what most of the extensions and papers here are about.</p>
    <p>Ph.D. on query processing in parallel database systems for hierarchically organised
    multiprocessors, then eight years at Postgres Professional, latterly heading its query
    optimisation lab. For eight years before that, and overlapping it, I was a senior
    scientist computing supersonic and hypersonic flows around re-entry vehicles — heat
    loads, ablating thermal protection, rocket engine combustion.</p>
    <p>I write about Postgres internals at
    <a href="https://danolivo.substack.com">danolivo.substack.com</a>.</p>
    <p class="meta">{{ site.profile.location }} &middot;
    <a href="mailto:{{ site.profile.email }}">{{ site.profile.email }}</a></p>
  </div>
</div>

## What I am working on

{% assign featured = site.data.projects | where: "featured", true %}
<ul>
{%- for p in featured %}
  <li><strong>{{ p.name }}</strong> — {{ p.summary }}</li>
{%- endfor %}
</ul>

<p>More on the <a href="{{ '/projects' | relative_url }}">projects</a> page, including the
distributed and high-availability systems I worked on earlier and the planner experiments
that have not landed anywhere yet.</p>

## Recent talks

<ul class="biblio">
{%- for t in site.data.talks limit: 3 %}
  {%- capture venue_text %}{{ t.event }}{% if t.place %}, {{ t.place }}{% endif %}{% endcapture -%}
  <li>
    <span class="btitle"{% if t.lang == "ru" %} lang="ru"{% endif %}>{% include sentence.html text=t.title %}</span>
    <span class="venue">{% include sentence.html text=venue_text %}</span>
    {%- if t.slides %} <span class="refs"><a href="{{ site.materials }}{{ t.slides }}" aria-label="Slides: {{ t.title | escape }}">slides</a></span>{% endif %}
  </li>
{%- endfor %}
</ul>

<p>Full list of <a href="{{ '/talks' | relative_url }}">talks</a> and
<a href="{{ '/publications' | relative_url }}">publications</a>.</p>

## Elsewhere

<ul>
{%- for link in site.links %}
  <li><a href="{{ link.url }}">{{ link.name }}</a></li>
{%- endfor %}
</ul>
