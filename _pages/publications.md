---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can find an updated list of my articles on <u><a href="https://scholar.google.com/citations?hl=en&user=PnhZJWMAAAAJ">my Google Scholar profile</a>.</u>

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
*Contributed equally to this work.

<script>
  var htmls = document.getElementsByClassName("archive__item");
  const name = "Nathan Wong";

  const original = "Published in ";
  const replace = "Submitted to ";

  for (var i = 0; i < htmls.length; i+=1) {
    var html = htmls[i].innerHTML;
    var idx = html.match(name).index;
    document.getElementsByClassName("archive__item")[i].innerHTML = html.substring(0, idx) + "<strong>" + name + "</strong>" + html.substring(idx + name.length, html.length);

    html = document.getElementsByClassName("archive__item")[i].innerHTML;
    var preprint = html.match("arXiv");    
    if (preprint) {
      var originalMatch = html.match(original);
      document.getElementsByClassName("archive__item")[i].innerHTML = html.substring(0, originalMatch.index) + replace + html.substring(originalMatch.index + replace.length, html.length);
    }
  }
</script>