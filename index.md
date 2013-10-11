---
layout: default
---


{% for post in site.posts %}
<div class="post">
	<h2>{{post.title}}</h2>
	{% if post.content contains "<!--more-->" %}
		{{post.excerpt}}
		<p class="readmore">Read the rest of <a href="{{post.url}}">{{post.title}}</a></p>
	{% else %}
		{{ post.content }}
	{% endif %}
</div>
{% endfor %}
