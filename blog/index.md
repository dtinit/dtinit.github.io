---
title: DTI Blog
---

<ul class="posts">
  {% for post in site.posts %}
    <li>
        <a href="{{ post.url | relative_url }}">
          <h2 class="post-title">{{ post.title | escape }}</h2>
        </a>
        <div class="post-meta">
          <div class="post-date">
            <i class="calendar-icon"></i>
            {{ post.date | date: "%b %-d, %Y" }}
          </div>
          {%- if post.tags.size > 0-%}
          <ul class="post-tags">
            {%- for tag in post.tags -%}
            <li><a href="tags#{{tag}}">{{ tag }}</a></li>
            {%- endfor -%}
          </ul>
          {%- endif -%}
        </div>
        <div class="post">
            {{ post.post-excerpt }}
        </div>
    </li>
  {% endfor %}
</ul>
