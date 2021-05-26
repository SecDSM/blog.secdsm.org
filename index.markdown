---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
permalink: /
title: SecDSM Community Blog
---

# SecDSM Community Blog

Blog Posts from the community are welcome! Please submit new posts via GitHub pull request at: [https://github.com/secdsm/secdsm.github.io](https://github.com/secdsm/secdsm.github.io)

{% for post in site.posts limit:5 %}
   <article>
        <h2>
            <a href="{{ post.url }}">
                {{ post.title }}
            </a>
        </h2>
        <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
        {{ post.content }}
    </article>
{% endfor %}
