---
layout: page
title: "Tags"
permalink: /tags/
main_nav: true
---

{% for category in site.tags %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h3 id="{{cat}}">{{ cat | capitalize }}</h3>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  <div class="tags">
    <ul class="tags-posts">
    {% for post in site.tags[cat] %}
      <li>
          <a class="post-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endfor %}
    </ul>
  </div>
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>
