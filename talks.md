---
layout: default
title: Talks
subtitle: Conference and meetup appearances, with slides where they survived.
permalink: /talks
nav_order: 4
description: >-
  Conference talks by Andrei Lepikhov on the PostgreSQL query optimizer — PG BootCamp, PGDay Israel, FOSSASIA, PGConf.EU, HighLoad++ — with slides and video.
---

{% assign groups = site.data.talks | group_by: "year" | sort: "name" | reverse %}
{%- for group in groups %}
<h2>{{ group.name }}</h2>
<ul class="biblio">
  {%- for t in group.items %}
  {%- capture venue_text %}{{ t.event }}{% if t.place %}, {{ t.place }}{% endif %}{% if t.lang == "ru" %} (in Russian){% endif %}{% endcapture -%}
  <li>
    <span class="btitle"{% if t.lang == "ru" %} lang="ru"{% endif %}>{% include sentence.html text=t.title %}</span>
    <span class="venue">{% include sentence.html text=venue_text %}</span>
    {%- if t.coauthors %} <span class="venue">With {{ t.coauthors }}.</span>{% endif %}
    <span class="refs">
      {%- if t.slides %}<a href="{{ site.materials }}{{ t.slides }}" aria-label="Slides: {{ t.title | escape }}">slides</a>{% endif -%}
      {%- if t.video %}<a href="{{ t.video }}" aria-label="Video: {{ t.title | escape }}">video</a>{% endif -%}
      {%- if t.url %}<a href="{{ t.url }}" aria-label="Schedule: {{ t.title | escape }}">schedule</a>{% endif -%}
    </span>
  </li>
  {%- endfor %}
</ul>
{%- endfor %}
