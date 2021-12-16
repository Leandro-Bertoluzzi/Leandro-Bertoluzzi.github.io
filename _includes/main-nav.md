<nav>
  {% assign posts=site.pages | where:"lang", page.lang | sort: 'title' %}
  {% if posts.size > 0 %}
    {% for post in posts %}
    <a href="{{ site.base-url }}{{ post.url }}">{{ post.title }}</a>
    {% endfor %}
  {% endif %}
</nav>