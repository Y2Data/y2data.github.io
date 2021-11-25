---
layout: default
images:
  - image_path: /assets/images/RWNLP.png
    title: Real World NLP
  - image_path: /assets/images/RWNLP.png
    title: Fast AI
---
<ul class="photo-gallery">
  {% for image in page.images %}
    <li><img src="{{ image.image_path }}" alt="{{ image.title}}"/></li>
  {% endfor %}
</ul>
