---
logo: dark
published: false
---

# Styleguide and Components
The above is what the <em><h1></em> element will look like. There should only be one on each page. Many of the typography elements are styled directly on their tags. Most of the other examples use classes for their styling.

<section>
  <h2>Typography (and an example of an h2 element)</h2>

  <h3>This is an H3</h3>
  <h4>This is an H4</h4>
  <h5>This is an H5</h5>

  <span class="heading-subtitle">
    Here is some slightly larger text that can be used in sub-title like cases.
  </span>

  <p>
    This is a paragraph of text. Most body text will probably be this size. If you need bigger or smaller than this but it's still body text, you might want to add a class for that specific instance to attach to the paragraph, or make a re-usuable class that defines the slightly larger body text.
  </p>

  <span class="list-heading">
  And the .list-heading class can be used for enphasizing something that's almost a header but not semantically a header
  </span>

  <small>This is small text, for little notes and stuff.</small>

  <p>This is text styled as a "tag", which will be used for the actual blog tags.</p>
  <span class="tag-item">communication</span>

  {% highlight html %}
  <span class="tag-item">communication</span>
  {% endhighlight %}

  Here are multiple tags together, which is the most likely way they will be used.
  <ul class="tag-list">
    <li class="tag-item">communication</li>
    <li class="tag-item">policy</li>
  </ul>

  {% highlight html %}
  <ul class="tag-list">
    <li class="tag-item">communication</li>
    <li class="tag-item">policy</li>
  </ul>
  {% endhighlight %}

</section>

<hr>

<section>
  <h2>Buttons and Links</h2>

  <button class="button" type="button">Default Button</button>
  <button class="button button-outline" type="button">Outline Button</button>

  {% highlight html %}
  <button class="button" type="button">Default Button</button>
  <button class="button button-outline" type="button">Outline Button</button>
  {% endhighlight %}

  <p>
    And sometimes you need a button to look like a link: <button class="button-link" type="button">Link Button</button>
  </p>

  {% highlight html %}
  <button class="button-link" type="button">Link Button</button>
  {% endhighlight %}

  <a href="https://www.xkcd.com">Regular link</a>

  {% highlight html %}
  <a href="https://www.xkcd.com">XKCD</a>
  {% endhighlight %}

  <p>
    And here is a link that looks like a button because it makes use of the button classes: <a href="https://www.xkcd.com" class="button">Link to XKCD</a>
  </p>

  {% highlight html %}
  <a href="https://www.xkcd.com" class="button">Link to XKCD</a>
  {% endhighlight %}
</section>

<hr>

<section>
  <h2>Images</h2>

  <img class="team-avatar" src="/images/staff/mcriley.jpg" />

  {% highlight html %}
  <img class="team-avatar" src="/images/staff/mcriley.jpg" />
  {% endhighlight %}

  <h3>Social Icons</h3>
  <img class="social-icon" src="/images/icons/linkedIn.svg">
  <img class="social-icon" src="/images/icons/mastodon.svg">
  <img class="social-icon" src="/images/icons/twitter.svg">

  <h3>White versions of social icons</h3>
  <div style="background-color: #000;padding: 10px; width: max-content;">
    <img class="social-icon" src="/images/icons/github-outline.svg">
    <img class="social-icon" src="/images/icons/linkedIn-outline.svg">
    <img class="social-icon" src="/images/icons/mastodon-white.svg">
  </div>
</section>

<hr>

<section>
  <h2>Form Elements</h2>

  <label for="newsletterEmail">
    Enter your email
    <input class="text-input" id="newsletterEmail" placeholder="jane@example.com" type="email" />
  </label>
</section>

<hr>

<section>
  <h2>Components</h2>

  <h3>Headers</h3>
  <p>There are two color versions of the header: <em>light</em> and <em>dark</em>. Which one is used on which page is determined by the front-matter variable for <strong>logo</strong>.</p>

  <h3>Details/Summary elements</h3>
  <p>We can use these for the FAQ, but they're handy for lots of other places too. A different disclosure image can be added later to look like the chevron on the mockup.</p>

  <details>
    <summary>What are some examples of data portability?</summary>
    <p>
      There are many use cases for users porting data directly between services, some we know about today, and some we have yet to discover. A couple of examples of ones we know users want today are...
    </p>
  </details>
  <details>
    <summary>Who is responsible for protecting data?</summary>
    <p>
      There are many use cases for users porting data directly between services, some we know about today, and some we have yet to discover. A couple of examples of ones we know users want today are...
    </p>
  </details>
</section>
