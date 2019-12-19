---
title: Schedule
i18n: schedule
redirect_from:
    - /schedule
    - /schedule/
---

# Schedule

[View schedule in Google/Apple/Microsoft/Mozilla calendar app.](https://h2vx.com/ics/get-cal.php?uri={{ page.url | absolute_url | uri_escape }} "Download this schedule to your calendar.")

{% assign last_block = site.data.schedule.blocks | sort: "startDate" | last %}
{% assign last_block_end_time = last_block.startDate | date: "%s" | plus: last_block.duration %}
{% assign first_block_start_time = site.data.schedule.startDate | date: "%s" %}

{% assign daily_duration = last_block_end_time | minus: first_block_start_time %}
{% assign daily_time_slices = daily_duration | divided_by: site.data.schedule.timeIncrement %}

<table id="conference-schedule">
    <caption>Full conference schedule for {{ site.title }}</caption>
    <thead>
        <tr>
            <th scope="col">
                Session Block
            </th>
            <th scope="col">
                Time
            </th>
            <th scope="col">
                {{ site.data.schedule.startDate | date: site.date_format }}
            </th>
            <th scope="col">
                {{ site.data.schedule.endDate | date: site.date_format }}
            </th>
        </tr>
    </thead>
    <tbody>
    {% assign first_slice_time = site.data.schedule.startDate | date: "%s" %}
    {% assign block_index = 0 %}
    {% for i in (1..daily_time_slices) %}
        {% assign x = i | minus: 1 %}
        {% assign print_block = false %}
        {% assign time_step = site.data.schedule.timeIncrement | times: x %}
        {% assign current_slice_time = first_slice_time | plus: time_step %}
        {% assign current_block = site.data.schedule.blocks[block_index] %}
        {% assign current_block_end_time = current_block.startDate | date: "%s" | plus: current_block.duration %}
        {% if current_block_end_time <= current_slice_time %}
            {% assign block_index = block_index | plus: 1 %}
            {% assign current_block = site.data.schedule.blocks[block_index] %}
            {% assign print_block = true %}
        {% endif %}
        {% assign block_row_span = current_block.duration | divided_by: site.data.schedule.timeIncrement %}
        <tr>
            {% if print_block or forloop.first %}
            <td class="block-name" rowspan="{{ block_row_span }}">
                <h2>{{ current_block.name }}</h2>
            </td>
            {% endif %}

            <td class="time-slot">{{ current_slice_time | date: site.time_format }}</td>

            {% for session in site.events %}
            {% assign session_start_time = session.startDate | date: "%s" | plus: 0 %}
            {% assign session_end_time = session.endDate | date: "%s" | plus: 0 %}
            {% if session_start_time == current_slice_time %}
            {% assign session_row_span = session_end_time | minus: session_start_time | divided_by: site.data.schedule.timeIncrement %}
            <td rowspan="{{ session_row_span }}">
                {% include h-event.html event=session %}
                {% include speaker-byline.html speakers=session.speakers %}
            </td>
            {% endif %}
            {% endfor %}

            {% for s in site.data.schedule.meta_sessions %}
            {% assign session_start_time = s.startDate | date: "%s" | plus: 0 %}
            {% assign session_end_time = s.startDate | date: "%s" | plus: s.duration %}
            {% if session_start_time == current_slice_time %}
            {% assign session_row_span = session_end_time | minus: session_start_time | divided_by: site.data.schedule.timeIncrement %}
            <td rowspan="{{ session_row_span }}">
                {% include h-event.html event=s %}
            </td>
            {% endif %}
            {% endfor %}

            {% for session in site.events %}
            {% assign session_start_time = session.startDate | date: "%s" | minus: 86400 %}
            {% assign session_end_time = session.endDate | date: "%s" | minus: 86400 %}
            {% if session_start_time == current_slice_time %}
            {% assign session_row_span = session_end_time | minus: session_start_time | divided_by: site.data.schedule.timeIncrement %}
            <td rowspan="{{ session_row_span }}">
                {% include h-event.html event=session %}
                {% include speaker-byline.html speakers=session.speakers %}
            </td>
            {% endif %}
            {% endfor %}

            {% for s in site.data.schedule.meta_sessions %}
            {% assign session_start_time = s.startDate | date: "%s" | minus: 86400 %}
            {% assign session_end_time = s.startDate | date: "%s" | plus: s.duration | minus: 86400 %}
            {% if session_start_time == current_slice_time %}
            {% assign session_row_span = session_end_time | minus: session_start_time | divided_by: site.data.schedule.timeIncrement %}
            <td rowspan="{{ session_row_span }}">
                {% include h-event.html event=s %}
            </td>
            {% endif %}
            {% endfor %}
        </tr>
    {% endfor %}
    </tbody>
</table>

[View schedule in Google/Apple/Microsoft/Mozilla calendar app.](https://h2vx.com/ics/get-cal.php?uri={{ page.url | absolute_url | uri_escape }} "Download this schedule to your calendar.")
