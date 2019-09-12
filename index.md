# Is Linux About…?

{% for page in site.pages %}
{% if page.title and page.url != "/" and page.url != "/404.html" %}
…[{{ page.url | replace: "/", "" | replace: "-", " " }}]({{ page.url }})?
{% endif %}
{% endfor %}

