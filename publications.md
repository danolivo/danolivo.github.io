---
layout: default
title: Publications
subtitle: Journal articles, conference papers and the Ph.D. thesis.
permalink: /publications
nav_order: 2
---

{% assign db = site.data.publications | where: "area", "db" %}
{% assign hpc = site.data.publications | where: "area", "hpc" %}
{% assign cfd = site.data.publications | where: "area", "cfd" %}

<p class="meta">{{ db.size | plus: hpc.size | plus: cfd.size }} entries.
Where a copy is available it is linked from the
<a href="https://github.com/danolivo/conf">conf</a> repository, which also holds
slides, benchmarks and working notes.</p>

## Database systems

{% include biblio.html items=db %}

## Parallel and high-performance computing

{% include biblio.html items=hpc %}

## Aerothermodynamics and CFD

<p class="note">Published as conference abstracts, proceedings and journal articles
between 2012 and 2017, during eight years at the Makeyev State Rocket Centre.</p>

{% include biblio.html items=cfd %}

## Registered software

<ul class="biblio">
{%- for s in site.data.awards.software %}
  <li>
    <span class="authors">{{ s.authors }}.</span>
    <span class="btitle" lang="ru">{% include sentence.html text=s.title %}</span>
    <span class="venue">Rospatent certificate of state registration of a computer
    program, {{ s.number }}.</span>
  </li>
{%- endfor %}
</ul>

## Grants and awards

<ul class="biblio">
{%- for g in site.data.awards.grants %}
  <li>
    <span class="venue">{{ g.year }}.</span>
    <span class="btitle">{{ g.title }}.</span>
    {%- if g.url %}<span class="refs"><a href="{{ g.url }}">link</a></span>{% endif %}
  </li>
{%- endfor %}
</ul>
