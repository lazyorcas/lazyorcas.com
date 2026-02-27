---
title: Oscar - The Pitfall of Idealism
description: A young adventurer set sail to the Pacific with the ambition to explore the Mariana Trench.
layout: music
favicon: /assets/images/music/the-pitfall-of-idealism.ico
---

{% assign key = "the-pitfall-of-idealism" %}
{% assign album = site.data.music.albums[key] %}
{% assign cover_src = "/assets/images/music/" | append: key | append: ".webp" %}

<main>
  <header>
    <div class="container music-header">
      <time datetime="{{ album.release_date }}">
        {{ album.release_date | date: "%B %-d, %Y" }}
      </time>
      <h1>{{ album.title }}</h1>
      <p class="sypnosis">{{ album.sypnosis }}</p>
      {% if album.acknowledgements %}
        <div class="acknowledgements">{{ album.acknowledgements | markdownify }}</div>
      {% endif %}
    </div>
  </header>
  <section>
    <ol class="tracks">
      {% for track in album.tracks %}
        <li class="track" data-soundcloud-track-id="{{ track.id }}" id="{{ track.slug }}">
          <div class="track-container">
            <h2 class="container">{{ track.title }}</h2>
            {% if track.youtube_id %}
              {% include youtube.html youtube_id=track.youtube_id %}
            {% else %}
              {% include soundcloud.html track_id=track.id %}
            {% endif %}
            {% if track.story %}
              <div class="container track-story">
                {{ track.story | markdownify }}
              </div>
            {% endif %}
          </div>
        </li>
      {% endfor %}
    </ol>
  </section>
</main>
