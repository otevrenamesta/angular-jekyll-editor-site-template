---
layout: index
title: Město ?
section: blog
---


Vítejte na oficiálních stránkách města ?.

## Aktuality


{% for post in site.posts limit:20 %}  
<article>
	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
	<h6>{{ post.date | date_to_string }}</h6>
	{% if post.splash %}<img src="{{ post.splash }}"/>{% endif %}
	{{ post.excerpt }}
</article>
{% endfor %}  
