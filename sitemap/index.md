---
layout: default
title: Mapa del sitio
nav_order: 95
description: "Mapa estructural de páginas y documentación pública de Quercus Flumen."
---

# Mapa del sitio

Listado automático de páginas públicas de Quercus Flumen.

Este mapa se actualiza automáticamente a partir de las páginas publicadas en el sitio.

<ul>
{% assign pages = site.pages | sort: "url" %}
{% for page in pages %}
  {% unless page.url contains "/assets/" %}
  {% unless page.url contains "/404" %}
  {% unless page.url contains "/feed" %}
  {% unless page.url contains ".xml" %}
  {% unless page.url contains ".css" %}
    <li>
      <a href="{{ page.url | relative_url }}">
        {{ page.title | default: page.url }}
      </a>
    </li>
  {% endunless %}
  {% endunless %}
  {% endunless %}
  {% endunless %}
  {% endunless %}
{% endfor %}
</ul>
