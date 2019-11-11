---
layout: default
permalink: /
---

<div class="larg">{% assign terms = site.data.terms | sort: 'name' %}
  <dl>{% for term in terms %}<dt data-url="{{ term.url }}" data-dfn="{{ term.definition }}">{{ term.name }}</dt>{% endfor %}
  </dl>
</div>
<div class="flap">
</div>
