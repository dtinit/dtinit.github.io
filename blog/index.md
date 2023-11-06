<h1>Blog&nbsp;<a class="socialIcon" rel="me" href="/feed.xml" target="_blank">
  <img height="24px" src="/images/rss+feed+24px.png" alt="The abstract icon with radiating quarter-rings that means transmission or feed"/>
</a></h1>


{% for post in site.posts %}
  <article class="section">
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
      {{ post.post-excerpt }}
    </p>
  </article>
{% endfor %}
