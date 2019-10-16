---
title: Speakers
i18n: speakers
---

# Speakers

{% for org in site.data.speakers.organizations %}

## {{ org.name }}{% if org.abbr %} ({{ org.abbr }}){% endif %}

{{ org.description | markdownify }}

* Website: [{{ org.website | replace: "https://", "" | replace: "http://", "" }}]({{ org.website }} "Visit {{ org.name }}&rsquo;s website.")

{% if org.speakers %}
### Speakers from {{ org.name }}

{% for s in org.speakers %}
{% assign speaker = site.data.speakers.speakers[s] %}

### {{ speaker.name }}

![Profile photo for {{ speaker.name }}](https://images.squarespace-cdn.com/content/v1/5c1bfc7eee175995a4ceb638/1551879667607-U5862LNXDDVSTI5W2L2P/ke17ZwdGBToddI8pDm48kO4BBCY1546PJ-qsvJktNVhZw-zPPgdn4jUwVcJE1ZvWEtT5uBSRWt4vQZAgTJucoTqqXjS3CfNDSuuf31e0tVEQ3Hvk2AfVOfKY0qvQqXnDS4CpCqDfb0dh44SO-lE1L4BaWi_xRK_ZQFJlfc0WoWs/headshot.jpg){:style="float: left; border-radius: 50%; width: 25%; margin: 0 2em 0 0;"}

{{ speaker.bio | markdownify }}

Presentations:

{% for presentation in speaker.presentations %}
* {{ presentation }}
{% endfor %}{% comment %}End Presentation Loop{% endcomment %}
{% endfor %}{% comment %}End Speaker Loop{% endcomment %}
{% endif %}
{% endfor %}{% comment %}End Organization Loop{% endcomment %}

