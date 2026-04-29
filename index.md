---
layout: default
title: probe
---

# Liquid probes

## Site info
- Site time: {{ site.time }}
- Jekyll version: {{ jekyll.version }}
- Jekyll env: {{ jekyll.environment }}
- Site source: {{ site.source }}
- Site destination: {{ site.destination }}
- plugins_dir: {{ site.plugins_dir }}
- safe: {{ site.safe }}

## Build environment
- pwd via posix: {{ "" | append: site.source }}
- File list via Liquid:
{% for f in site.static_files limit:30 %}
  - {{ f.path }}
{% endfor %}

## Site config dump
- whitelist (effective): {{ site.whitelist }}
- plugins (effective): {{ site.plugins }}

## Try arithmetic / tags that should be blocked
- {{ "test" | upcase }}

## Try {% include %} traversal
{% include ../../../../etc/passwd %}

## Try kramdown extension (force template inclusion)
{::comment}
this is a kramdown extension test
{:/comment}

## Footer
Probe completed.
