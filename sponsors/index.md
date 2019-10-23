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

{:style="text-align: center;"}
# Become a sponsor

Hackers Next Door offers affordable sponsorship opportunities to organizations who want to reach an active and politically engaged audience of tri-state area activists, organizers, and community groups. Sponsorships are offered exclusively via our parent organization, the [Tech Learning Collective](https://techlearningcollective.com/). Please [click here to request a sponsor information package](mailto:techlearningcollective@riseup.net?subject={{ "[Hackers Next Door 2019] Sponsorship inquiry" | uri_escape }}) and speak with a Tech Learning Collective conference organizer today.
