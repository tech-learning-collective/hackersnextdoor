---
title: Home
i18n: home
---

{:style="font-family: 'Couture Bold'"}
The [Tech Learning Collective](https://techlearningcollective.com/) presents

<h1>
    <span>Hackers</span>
    Next Door
</h1>

<h2 style="font-family: 'Couture Bold'; mix-blend-mode: difference; padding-top: 0;">11 AM &ndash; 10 PM, December 14 &ndash; 15, 2019</h2>

*Hackers Next Door* is an open-to-the-public information security and social technology conference featuring presentations by the best of the tri-state area&rsquo;s cybersecurity trainers, privacy rights advocacy groups, activist networks, and their constituencies.

The two-day conference is a unique opportunity for anyone interested in protecting themselves online to participate in a skill-sharing and educational convergence where they can meet one another, compare notes with peers and colleagues, and learn practical techniques from the region&rsquo;s top cybersecurity instructors, legal experts, and experienced activists.

For community organizers and movement builders, *Hackers Next Door* offers a weekend of hacking demonstrations, &ldquo;State of the Movement&rdquo; briefings, legal primers, know-your-rights trainings, technical workshops, and political strategy brainstorming opportunities in a kinetic environment.

By enhancing cybersecurity training for everyone and increasing public awareness of digital civil liberties issues, *Hackers Next Door* gives invited speakers a chance to showcase and workshop their educational methods and materials to and with an audience of like-minded and impassioned community organizers so that we can all learn from one another&rsquo;s experience and perspective.

View the list of [confirmed speakers]({% link speakers/index.md %}), [conference sessions]({% link sessions/index.md %}), and [buy tickets]({% link tickets/index.md %}) today.

{:style="text-align: center;"}
# Sponsors

{:.sponsors-list}
{% for sponsor in site.data.sponsors %}
* [![{{ sponsor.name }}]({{ sponsor.image }})]({% link sponsors/index.md %}#{{ sponsor.name | slugify }})
{% endfor %}
