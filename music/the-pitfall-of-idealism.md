---
title: The Pitfall of Idealism
layout: music
favicon: /assets/images/music/the-pitfall-of-idealism.ico
---

{% assign key = "the-pitfall-of-idealism" %}
{% assign album = site.data.music.albums[key] %}
{% assign cover_src = "/assets/images/music/" | append: key | append: ".webp" %}

<main>
  <header class="container">
    <time datetime="{{ album.release_date }}">
      {{ album.release_date | date: "%B %-d, %Y" }}
    </time>
    <h1>{{ album.title }}</h1>
    <p class="sypnosis">{{ album.sypnosis }}</p>
    {% if album.acknowledgements %}
      <div class="acknowledgements">{{ album.acknowledgements | markdownify }}</div>
    {% endif %}
  </header>
  <section>
    <ol class="tracks">
      {% for track in album.tracks %}
        <li class="container" data-soundcloud-track-id="{{ track.id }}">
          <div class="track-container">
            <h2>{{ track.title }}</h2>
            {% if track.youtube_id %}
              {% include youtube.html youtube_id=track.youtube_id %}
            {% else %}
              {% include soundcloud.html track_id=track.id %}
            {% endif %}
            {% if track.story %}
              <div class="track-story">
                {{ track.story | markdownify }}
              </div>
            {% endif %}
          </div>
        </li>
      {% endfor %}
    </ol>
  </section>
  <div class="glow"></div>
</main>
