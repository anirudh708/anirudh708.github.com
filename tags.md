---
layout: default
title: Tags
---
<div class="post">
<h3>{{page.title}}</h3>

{% capture tags %}
  {% for tag in site.tags %}
    {{ tag[0] }}
  {% endfor %}
{% endcapture %}
{% assign sortedtags = tags | split:' ' | sort %}

{% for tag in sortedtags %}
  <h4 id="{{ tag | escape }}">{{ tag }}</h4>
  <ul>
  {% for post in site.tags[tag] %}
    <li><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
{% endfor %}
</div>