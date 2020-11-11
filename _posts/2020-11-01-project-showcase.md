---
img-grid:
  src: jekyll-logo.png
  alt: Jekyll logo
img-header:
  src: project-showcase.png
  alt: Screenshot of project showcase website
category: Website
github-repo: jacobcallear/jacobcallear.github.io
languages: Jekyll Liquid, HTML, CSS, JavaScript
summary:
  My online digital portfolio - you're looking at it! Built using the static
  site generator Jekyll. Forked from Jerome Lachaud's
  [freelancer-theme.](https://github.com/jeromelachaud/freelancer-theme)
---

### Code Samples

`HTML` / `Jekyll Liquid`: Extract from a layout file that adds a markdown-
formatted summary and a GitHub repository link to each project post. A website
link is added if available.

{% raw %}
```html
{{ post.summary | markdownify }}
<p>
  <a href="https://github.com/{{ post.github-repo }}">
    <i class="fa fa-fw fa-github"></i>
    GitHub repo
  </a>
</p>
{% if post.website %}
  <p>
    <a href={{ post.website }}>
      <i class="fa fa-fw fa-globe"></i>
      Website
    </a>
  </p>
{% endif %}
{% if post.content %}
  <p>{{ post.content }}</p>
{% endif %}
```
{% endraw %}
