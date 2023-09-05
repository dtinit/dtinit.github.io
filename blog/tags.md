Find a post by its tag(s):
<ul class="posts-by-tag">
  {% for tag in site.tags %}
    {% assign tagname = tag | first %}
    {% assign posts = tag | last %}    
    <li class="tag-anchor" >
      <a href="#{{tagname}}">{{ tagname | downcase | replace:" ","-" }}</a>

      <ul>
        {% for post in posts %}
          <li>
            <a href="{{ post.url }}">{{ post.title }}</a>
            <span class="post-date">{{ post.date | date: "%B %-d, %Y"  }}</span>
          </li>
        {% endfor %}
      </ul>
    </li>
  {% endfor %}
</ul>
