{% if page.layout != 'home' %}
    {% assign posts=site.posts | where:"lang-ref", page.lang-ref | sort: 'lang' %}
    {% if posts.size == 0 %}
        {% assign posts=site.pages | where:"lang-ref", page.lang-ref | sort: 'lang' %}
    {% endif %}
    {% if posts.size > 1 %}
    <footer class="lang-options">
        <em>{{ site.data.translations['differentLanguage'][page.lang] }}:</em>
        <ul>
        {% for post in posts %}
        <li>
            <a href="{{ site.base-url }}{{ post.url }}" class="{{ post.lang }}" title="{{ site.data.translations['viewIn'][post.lang] }} {{ post.lang }}">
                {{ site.data.languages[post.lang].icon }} {{ site.data.languages[post.lang].label }}
            </a>
        </li>
        {% endfor %}
        </ul>
    </footer>
    {% endif %}
{% endif %}