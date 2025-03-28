---
layout: page
title: Home
id: home
permalink: /
---

# Gabe's Place 🔮

Hello! This is a site where I post about my interests. 


**Recent Posts**

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 5 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — 
      <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">
        {{ note.path | split: "/" | last | split: "." | first }}
      </a>
    </li>
  {% endfor %}
</ul>


<style>
  .wrapper {
    max-width: 46em;
  }
</style>
