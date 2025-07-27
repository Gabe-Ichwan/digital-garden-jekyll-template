---
layout: page
title: Tags
permalink: /tags
---

# All Tags

<h2>
  {% assign tags_list = site.notes | map: "tags" | join: "," | split: "," | uniq | sort %}
  {% for tag in tags_list %}
    {% if tag != "" %}
        <h2 id="{{ tag | slugify }}">{{ tag | replace: "_", " " }}</h2>
        <ul>
          {% assign tagged_notes = site.notes | where_exp: "note", "note.tags contains tag" %}
          {% for note in tagged_notes %}
            <li>
              {{ note.last_modified_at | date: "%Y-%m-%d" }} —
              <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">
                {{ note.path | split: "/" | last | replace: ".md", "" }}
              </a>
            </li>
          {% endfor %}
        </ul>
    {% endif %}
  {% endfor %}
</h2>