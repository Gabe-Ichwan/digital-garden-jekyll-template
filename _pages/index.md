---
layout: page
title: Home
id: home
permalink: /
---

# Gabe's Blue Blog

# ██▒▒▒▒▒▒▒▒

You've found my blog!


**Recent Posts**

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 1000 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — 
      <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">
        {{ note.path | split: "/" | last | replace: ".md", "" }}
      </a>
    </li>
  {% endfor %}
</ul>


<style>
  .wrapper {
    max-width: 46em;
  }
</style>
