---
layout: archive
title: "Sitemap"
description: "Pages on Chenghong Zhu's academic website."
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

Browse the pages on this website, or view the [XML sitemap]({{ base_path }}/sitemap.xml).

<h2>Pages</h2>
{% for post in site.pages %}
  {% if post.title and post.sitemap != false and post.redirect_to == nil %}
  {% include archive-single.html %}
  {% endif %}
{% endfor %}

{% if site.posts.size > 0 %}
<h2>Posts</h2>
{% for post in site.posts %}
  {% unless post.sitemap == false %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endif %}

{% for collection in site.collections %}
  {% if collection.output and collection.label != "posts" and collection.docs.size > 0 %}
    <h2>{{ collection.label | capitalize }}</h2>
    {% for post in collection.docs %}
      {% unless post.sitemap == false %}
      {% include archive-single.html %}
      {% endunless %}
    {% endfor %}
  {% endif %}
{% endfor %}
