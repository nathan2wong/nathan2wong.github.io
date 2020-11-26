---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

[XML version]({{ base_path }}/sitemap.xml)

<h2>Pages</h2>
{% for post in site.pages %}
  {% if post.author_profile %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}