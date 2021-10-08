---
title: Nomisma.org Scientific Committee
layout: default
permalink: /about/working_groups/
---

# Working Groups

{% assign rows = site.group.size | divided_by: 2.0 | ceil %}

{% for group in site.group %}
{{group.content}}
{% endfor %}