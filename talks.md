---
layout: default
title: Talks
subtitle: Conference and meetup appearances, with slides where they survived.
permalink: /talks
nav_order: 3
---

{% assign groups = site.data.talks | group_by: "year" | sort: "name" | reverse %}
{%- for group in groups %}
<h3>{{ group.name }}</h3>
<ul class="biblio">
  {%- for t in group.items %}
  <li>
    <span class="btitle">{{ t.title }}.</span>
    <span class="venue">{{ t.event }}{% if t.place %}, {{ t.place }}{% endif %}{% if t.lang == "ru" %} (in Russian){% endif %}.</span>
    {%- if t.coauthors %}<span class="venue">With {{ t.coauthors }}.</span>{% endif %}
    <span class="refs">
      {%- if t.slides %}<a href="{{ site.materials }}{{ t.slides }}">slides</a>{% endif -%}
      {%- if t.video %}<a href="{{ t.video }}">video</a>{% endif -%}
      {%- if t.url %}<a href="{{ t.url }}">schedule</a>{% endif -%}
    </span>
  </li>
  {%- endfor %}
</ul>
{%- endfor %}
