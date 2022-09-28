<footer markdown="1">
{% if include.author %}
  {% assign author = include.author %}
  {% if include.author-link %}
    {% assign author-link = include.author-link %}
  {% else %}
    {% assign author-link = site.author-link %}
  {% endif %}
{% else %}
  {% assign author = site.author %}
  {% assign author-link = site.author-link %}
{% endif %}


© {{ site.time | date: '%Y' }} [{{ author }}]({{ author-link }}) • [Public stats](https://plausible.io/islinuxabout.xyz)

[Contribute to this site]({{ site.repo }})

</footer>
