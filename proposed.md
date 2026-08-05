---
layout: default
title: In flight
subtitle: Work proposed to PostgreSQL that has not landed, and has not been rejected.
permalink: /proposed
nav_order: 2
description: >-
  PostgreSQL patches proposed by Andrei Lepikhov that are still open — commitfest status, target release and the pgsql-hackers thread for each.
---

<p class="note">Getting a feature into PostgreSQL takes years and several attempts;
self-join elimination was committed, reverted, and committed again a release later.
This page is the part of the work that is still in the middle of that. Statuses were
read from <a href="https://commitfest.postgresql.org/">commitfest.postgresql.org</a>
on {{ site.data.proposals.checked | date: "%-d %B %Y" }} — it is the authority, not
this page.</p>

## In a commitfest

{% assign live = site.data.proposals.commitfest %}
{% for p in live %}
<div class="project">
  <h3>{{ p.title }}<span class="status">{{ p.status }}</span></h3>
  <p class="meta">proposed {{ p.since }} &middot; targeting PostgreSQL {{ p.target }} &middot;
  {{ p.cf }}{% if p.coauthors %} &middot; with {{ p.coauthors }}{% endif %}</p>
  <p>{{ p.body }}</p>
  <p class="meta">
    <a href="https://commitfest.postgresql.org/patch/{{ p.id }}/">commitfest #{{ p.id }}</a>
    &middot; <a href="{{ p.thread }}">thread</a>
  </p>
</div>
{% endfor %}

## On the mailing list

<p class="note">Proposed on pgsql-hackers, with no commitfest entry under a matching
title.</p>

{% for p in site.data.proposals.hackers %}
<div class="project">
  <h3>{{ p.title }}</h3>
  <p class="meta">proposed {{ p.since }}</p>
  <p>{{ p.body }}</p>
  <p class="meta"><a href="{{ p.thread }}">thread</a></p>
</div>
{% endfor %}

## Carried in enterprise forks

<p class="note">Shipped to customers in a fork that carries patches core has not
taken. Older than the commitfest entries above and not currently registered, so no
status is quoted.</p>

<ul>
{%- for p in site.data.proposals.forks %}
  <li><strong>{{ p.title }}</strong> — {{ p.body }}</li>
{%- endfor %}
</ul>

<p>What did land is on the <a href="{{ '/projects' | relative_url }}">projects</a>
page, with the release each feature shipped in.</p>
