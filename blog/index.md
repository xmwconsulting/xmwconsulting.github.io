--- 
layout: default 
title: XMW Consulting - Blog
---    

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
{:.post-title}
## {{ year.name }}
{% for post in year.items %}
{:.post-title}
### &raquo; <a href="{{ post.url }}">{{ post.title }}</a>

<div class="tags-and-date-flex">
    <div style="flex-basis: 80%; text-align: left">
        <p class="subscript-style"><i class="fa fa-tags"></i> {{ post.categories | join: ', ' }}</p>
    </div>
    <div style="flex-basis: 20%; text-align: right">
        <p class="subscript-style">{{ post.date | date: "%Y-%m-%d %H:%M" }}</p>
    </div>
</div>

{: style="text-indent: 1em"}
{{ post.excerpt | strip_html }}
{% endfor %}
{% endfor %}
