---
layout: page
title: All
id: all
permalink: /all
---

# All Posts

<h2>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% assign notes_by_year = recent_notes | group_by_exp: "note", "note.last_modified_at | date: '%Y'" %}
  {% for year in notes_by_year %}
    <h2>{{ year.name }}</h2>
    {% assign notes_by_month = year.items | group_by_exp: "note", "note.last_modified_at | date: '%B'" %}
    {% for month in notes_by_month %}
      <h3>{{ month.name }}</h3>
      <ul>
        {% for note in month.items %}
          <li>
            {{ note.last_modified_at | date: "%Y-%m-%d" }} — 
            <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">
              {{ note.path | split: "/" | last | replace: ".md", "" }}
            </a>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  {% endfor %}
</h2>


<style>
  .wrapper {
    max-width: 46em;
  }
</style>
