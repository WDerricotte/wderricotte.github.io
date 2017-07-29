---
layout: default
title: Blogging
---

<ol class="breadcrumb">
  <li><a href="/"><i class="fa fa-home"></i></a></li>
  <li class="active">Blogging</li>
</ol>

## Derricotte Research Group Blog
I will periodically update this blog with new research activity, news in chemistry, teaching, academia, etc. 

<div>
<ul>
{% for post in site.posts %}
<li>{{ post.date | date: "%b %-d, %Y" }}: <a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
</div>
