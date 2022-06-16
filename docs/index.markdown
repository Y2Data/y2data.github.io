---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
---
<h2>Hello!</h2>

* Welcome to my website, scroll down for my recent posts.
* View my [resume](/assets/CV.pdf)!
* [Certifications]({{ site.url }}/certs)

* Here's a list view of all my posts:
  [List of Posts]({{ site.url }}/all) ({{ site.posts.size }} posts.)
{% comment %}
* [Final Paper](/assets/finalPaper.pdf)
* [Competition Portfolio]({{ site.url }}/CompetitionPortfolio)
{% endcomment %}




<h3>My recent posts: </h3>
{% for post in site.posts limit:3 %}
{% if post.visible != 0 %}
  <li><a href="{{ post.url }}">{{ post.title }} ({{ post.date | date: "%b %d, %Y" }})</a></li>
{{ post.excerpt | truncatewords: 30 }}
{% endif %}
{% endfor %}
