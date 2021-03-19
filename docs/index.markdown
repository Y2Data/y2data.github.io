---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
---
<h2>Hello!</h2>

* Welcome to my website, scroll down for my recent posts.
* Here's my [blog](https://y2d.club) hosted on WordPress (deprecation alert).
* I'll add more whenever possible.
* View my [resume](/assets/CV.pdf)!

<h3>My recent posts:</h3>

{% for post in site.posts %}
  <ul>
    <li><a href="{{ post.url }}">{{ post.title }} ({{ post.date | date: "%b %d, %Y" }})</a></li>
  </ul>

{{ post.excerpt | truncatewords: 30 }}

{% endfor %}
