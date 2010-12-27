---
layout: things
---
# Things I Love

I tend to hate clutter, love throwing things out, and develop fierce loyalty to the things I love. I also really appreciate friends and folks I look up to as recommendation engines. They're how I've discovered plenty of the things I really love. So that's what this is about. Imagine that it's like free advertising, but only for things I really, really love. And maybe you'll discover something you like, too.

<ul id="thing_list">
    {% for post in site.categories.things %}
        <li class="{{ post.orientation }}">
            <a href="{{ post.link }}"><img src="{{ post.image }}" alt="{{ post.title }} Thumbnail" width="360" height="180"></a>
            <h4><a href="{{ post.link }}">{{ post.title }}</a></h4>
            <p>{{ post.content }}</p>
        </li>            
    {% endfor %}
</ul>