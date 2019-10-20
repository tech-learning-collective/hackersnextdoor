---
title: Sessions
i18n: Sessions
---

# Sessions

{% assign events = site.events | sort: "title" %}
<ul style="list-style-type: none;">
{% for event in events %}
    <li>
        <a href="{{ event.url }}">
            <h2>{{ event.title }}</h2>
            <img src="{{ event.image }}" alt="" class="session-photo" />
        </a>
        <p class="speaker-photo">
        {% if site.data.speakers.speakers[event.speaker].image %}
        <img src="{{ site.data.speakers.speakers[event.speaker].image }}" alt="Profile photo for {{ site.data.speakers.speakers[event.speaker].name }}" />
        {% endif %}
        Presented by <a href="{% link speakers/index.md %}#{{ site.data.speakers.speakers[event.speaker].name | slugify }}">{{ site.data.speakers.speakers[event.speaker].name }}</a>
        </p>
        
        {{ event.teaser | markdownify }}

        <p>(<a href="{{ event.url }}">Read more&hellip;.</a>)</p>
    </li>
{% endfor %}
</ul>
