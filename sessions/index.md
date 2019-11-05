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
            <h2 style="padding-top: 3em;">{{ event.title }}</h2>
            {% if event.image %}<img src="{{ event.image }}" alt="" class="session-photo" />{% endif %}
        </a>
        {% for s in event.speakers %}
        {% assign speaker = site.data.speakers.speakers[s] %}
        <p class="speaker-photo">
        {% if speaker.image %}
        <img src="{{ speaker.image }}" alt="Profile photo for {{ speaker.name }}" />
        {% endif %}
        {% if forloop.first %}Presented by {% else %}and {% endif %}<a href="{% link speakers/index.md %}#{{ speaker.name | slugify }}">{{ speaker.name }}</a>
        </p>
        {% endfor %}
        
        {{ event.teaser | markdownify }}

        <p>(<a href="{{ event.url }}">Read more&hellip;.</a>)</p>
    </li>
{% endfor %}
</ul>
