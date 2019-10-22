---
title: Sponsors
i18n: sponsors
---

{:style="margin-bottom: 50px;"}
# Sponsors

{% for sponsor in site.data.sponsors %}

## {{ sponsor.name }}{% if sponsor.abbr %} ({{ sponsor.abbr }}){% endif %}

{% if sponsor.image %}
<p class="speaker-photo">
    <img src="{{ sponsor.image }}" alt="Logo for {{ sponsor.name }}"
        {% if sponsor.image_style %}style='{{ sponsor.image_style }}'{% endif %}
    />
</p>
{% endif %}

{{ sponsor.description | markdownify }}

* Website: [{{ sponsor.website | replace: "https://", "" | replace: "http://", "" }}]({{ sponsor.website }} "Visit {{ sponsor.name }}&rsquo;s website.")

{% endfor %}

