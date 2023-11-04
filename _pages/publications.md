---
layout: archive
title: "项目"
permalink: /publications/
author_profile: true
---
1111111111111111111111111111111111111111
122222


{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
