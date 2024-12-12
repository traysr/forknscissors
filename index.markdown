---
layout: page
---

{% assign postsByMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}

<div class="post-archive">
  {% for monthGroup in postsByMonth %}
    <h4>{{ monthGroup.name }}</h4>
    <ul class="post-list">
      {% for post in monthGroup.items %}
        <li>
          <span class="post-meta">{{ post.date | date: "%d" }}</span>
          <a href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </li>
      {% endfor %}
    </ul>
  {% endfor %}
</div>