---
layout: layouts/base.njk
pageClass: posts
templateEngineOverride: njk, md
---


<main>
  {{ content | safe }}
  <div class="footnote">
    <p class="date">
      Ultima modifica il <time datetime="{{ date }}">{{ date | dateDisplay }}</time>
    </p>
  </div>
</main>
