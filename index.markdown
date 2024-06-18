---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
---
<div class="blog-list">
    {% for post in site.posts %}
    <a href="{{ post.url }}" class="blog-item">
        <img src="{{ post.image }}" alt="{{ post.title }}">
        <h2>{{ post.title }}</h2>
        <p>{{ post.description }}</p>
        <div class="meta">
            <span class="author">{{ post.author }}</span>
            <span class="date">{{ post.date | date:"%B %d, %Y" }}</span>
        </div>
    </a>
    {% endfor %}
</div>

