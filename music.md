---
layout: homepage
title: Music
permalink: /music.html
---

[← Back to home](./)

## Music Recommendations

A few songs and albums I keep coming back to.

<style>
  .song { display: flex; gap: 16px; align-items: flex-start; margin: 0 0 24px; }
  .song img { width: 110px; height: 110px; object-fit: cover; border-radius: 6px; flex-shrink: 0; }
  .song .note { margin-top: 4px; }
  .song .tag { font-size: 0.75rem; border: 1px solid currentColor; border-radius: 3px; padding: 0 5px; margin-left: 6px; opacity: 0.7; }
  @media (max-width: 480px) { .song img { width: 80px; height: 80px; } }
</style>

{% for song in site.data.music %}
<div class="song">
  {% if song.cover %}<img src="{{ song.cover | relative_url }}" alt="{{ song.title }} cover">{% endif %}
  <div>
    <strong>{{ song.title }}</strong>{% if song.type == "album" %}<span class="tag">Album</span>{% endif %} · {{ song.artist }}{% if song.year %} ({{ song.year }}){% endif %}
    {% if song.note %}<div class="note">{{ song.note }}</div>{% endif %}
  </div>
</div>
{% endfor %}
