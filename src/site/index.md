---
title: Stanzinoblog
subtitle: Appunti in libertà delle cose che mi appassionano di volta in volta
layout: layouts/base.njk
---




## Lista degli Articoli

### Javascript

<ul class="listing">
{%- for page in collections.javascript -%}
  <li>
    <a href="{{ page.url }}">{{ page.data.title }}</a> -
    <time datetime="{{ page.date }}">{{ page.date | dateDisplay("LLLL d, y") }}</time>
  </li>
{%- endfor -%}
</ul>

### NodeJS
<ul class="listing">
{%- for page in collections.nodejs -%}
  <li>
    <a href="{{ page.url }}">{{ page.data.title }}</a> -
    <time datetime="{{ page.date }}">{{ page.date | dateDisplay("LLLL d, y") }}</time>
  </li>
{%- endfor -%}
</ul>

### Python
<ul class="listing">
{%- for page in collections.python -%}
  <li>
    <a href="{{ page.url }}">{{ page.data.title }}</a> -
    <time datetime="{{ page.date }}">{{ page.date | dateDisplay("LLLL d, y") }}</time>
  </li>
{%- endfor -%}
</ul>