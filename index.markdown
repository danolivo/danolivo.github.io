---
layout: default
title: Andrei Lepikhov
---

<div class="intro">
  <img class="portrait" src="{{ '/assets/img/portrait.jpg' | relative_url }}"
       width="480" height="480" alt="Andrei Lepikhov">
  <div class="intro-text">
    <h1>Andrei Lepikhov</h1>
    <p class="lede">{{ site.profile.role }} at {{ site.profile.company }}. Database systems
    engineer with 15+ years on PostgreSQL internals — query optimisation, logical
    replication and distributed systems — with features contributed to PostgreSQL core.</p>
    <p>Ph.D. on query processing in parallel database systems for hierarchically organised
    multiprocessors, then eight years in the Postgres optimiser laboratory at Postgres
    Professional, and now active-active logical replication at pgEdge. Alongside that, and
    for eight years before it, I was a senior scientist computing supersonic and hypersonic
    flows around re-entry vehicles — heat loads, ablating thermal protection, rocket engine
    combustion.</p>
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
  <li>
    <span class="btitle">{{ t.title }}.</span>
    <span class="venue">{{ t.event }}{% if t.place %}, {{ t.place }}{% endif %}.</span>
    {%- if t.slides %}<span class="refs"><a href="{{ site.materials }}{{ t.slides }}">slides</a></span>{% endif %}
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
