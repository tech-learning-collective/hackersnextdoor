---
title: Speakers
i18n: speakers
---

{:style="margin-bottom: 50px;"}
# Speakers

{% for org in site.data.speakers.organizations %}

## {{ org.name }}{% if org.abbr %} ({{ org.abbr }}){% endif %}

{% if org.image %}
<p class="speaker-photo">
    <img src="{{ org.image }}" alt="Logo for {{ org.name }}"
        {% if org.image_style %} style="{{ org.image_style }}"{% endif %}
    />
</p>
{% endif %}

{{ org.description | markdownify }}

{% if org.website %}
* Website: [{{ org.website | replace: "https://", "" | replace: "http://", "" }}]({{ org.website }} "Visit {{ org.name }}&rsquo;s website.")
{% endif %}

{% if org.speakers %}
### Speakers from {{ org.name }}

{% for s in org.speakers %}
{% assign speaker = site.data.speakers.speakers[s] %}

#### {{ speaker.name }}

{% if speaker.image %}
{:.speaker-photo}
![Profile photo for {{ speaker.name }}]({{ speaker.image }})
{% endif %}

{{ speaker.bio | markdownify }}

{{ speaker.name }} will be presenting:

{% for presentation in speaker.presentations %}
{% assign p = site.events | where: "slug", presentation | first %}
* [{{ p.title }}]({{ p.url }} "View session details.")
{% endfor %}{% comment %}End Presentation Loop{% endcomment %}
{% endfor %}{% comment %}End Speaker Loop{% endcomment %}
{% endif %}
{% endfor %}{% comment %}End Organization Loop{% endcomment %}

