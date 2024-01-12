---
title: Blog
logo: light
---

<h1>
  Blog
  <a class="socialIcon" href="/feed.xml">
    <img height="24px" src="/images/rss+feed+24px.png" alt="RSS Feed"/>
  </a>
</h1>


{% for post in site.posts %}
  <article class="post">
    <div class="post-image">
      <img src="{{ post.thumbnail }}"/>
    </div>
    <div class="post-text-stuff">
      <h2 class="post-title">
        <a href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h2>
      <div class="post-meta">
        <time class="post-date" datetime="{{ post.date }}">{{ post.date | date: "%b %-d, %Y" }}</time>
        {%- if post.tags.size > 0 -%}
          <ul class="post-tags">
            {%- for tag in post.tags -%}
              <li>
                <a href="tags#{{tag}}">{{ tag }}</a>
              </li>
            {%- endfor -%}
          </ul>
        {%- endif -%}
      </div>
      <p>
        {{ post.excerpt }}
      </p>
    </div>
  </article>
{% endfor %}
