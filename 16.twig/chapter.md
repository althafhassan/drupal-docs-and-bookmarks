---
title: Twig
---

Debug:

{% for item in items %}
{{ dump(item.content) }}
  {{ dump(item.content["#context"]["value"]) }}
{% endfor %}