---
title: Sessions
i18n: Sessions
redirect_from:
    - /sessions
    - /sessions/
---

# Sessions

{% assign events = site.events | sort: "title" %}
<ul style="list-style-type: none;">
{% for event in events %}
    <li>
        <a href="{{ event.url }}">
            <h2 style="padding-top: 3em;">{{ event.title }}</h2>
            {% if event.image %}<img src="{{ event.image }}" alt="" class="session-photo" />{% endif %}
        </a>
        {% include speaker-byline.html speakers=event.speakers %}
        
        {{ event.teaser | markdownify }}

        <p>(<a href="{{ event.url }}">Read more&hellip;.</a>)</p>
    </li>
{% endfor %}
</ul>
