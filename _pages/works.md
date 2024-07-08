---
layout: archive
title: "Works"
permalink: /works/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.works reversed %}
  {% include archive-single.html %}
{% endfor %}
