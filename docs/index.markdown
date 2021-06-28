---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
---
<h2>Hello!</h2>

* Welcome to my website, scroll down for my recent posts.
* Here's my [blog](https://y2d.club) hosted on WordPress (deprecation alert).
* Here's a list view of all my posts:
  [List of Posts]({{ site.url }}/all) ({{ site.posts.size }} posts.)
* View my [resume](/assets/CV.pdf)!
* [Certifications]({{ site.url }}/certs)
* [Competition Portfolio]({{ site.url }}/CompetitionPortfolio)

<h3>My recent posts:</h3>

{% for post in site.posts limit:5 %}
  <li><a href="{{ post.url }}">{{ post.title }} ({{ post.date | date: "%b %d, %Y" }})</a></li>
{{ post.excerpt | truncatewords: 30 }}
{% endfor %}
