---
permalink: /sitemap.xml
eleventyExcludeFromCollections: true
---
<?xml version="1.0" encoding="utf-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
{% for page in collections.all %}
{% if page %}
<url>
<loc>{{ site.url }}{{ page.url | url }}</loc>
<lastmod>{{ page.date | date: "%Y-%m-%d" }}</lastmod>
<changefreq>
{%- if page.data.changeFreq -%}
{{page.data.changeFreq}}
{%- else -%}
monthly
{%- endif -%}
</changefreq>
</url>
{% endif %}
{% endfor %}
</urlset>