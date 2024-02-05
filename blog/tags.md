---
logo: light
---

# Find a post by its tag(s)

<ul class="posts-by-tag">
  {% for tag in site.tags %}
    {% assign tagname = tag | first %}
    {% assign posts = tag | last %}    
    <li>
      <span class="tag-anchor" id="{{ tagname }}">
        {{ tagname | downcase | replace:" ","-" }}
      </span>

      <ul>
        {% for post in posts %}
          <li>
            <a href="{{ post.url }}">{{ post.title }}</a>
            <time class="post-date" datetime="{{ post.date }}">
              {{ post.date | date: "%B %-d, %Y"  }}
            </time>
          </li>
        {% endfor %}
      </ul>
    </li>
  {% endfor %}
</ul>
