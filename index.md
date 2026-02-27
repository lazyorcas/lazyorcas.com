---
---

<main>
  <header class="container">
    <h1>Oscar's Personal Website</h1>
    <p>Heya! This is my personal website where you can find my works with software, music, film, video games.</p>
  </header>
  <section class="container">
    <h2>Music</h2>
    <ol>
      {% for album in site.data.music.albums %}
        <li>
          <a href="/music/{{ album[0] }}">{{ album[1].title }}</a>
        </li>
      {% endfor %}
    </ol>
  </section>
  <footer  class="container">
    <div>
      <h2>Contact</h2>
      <a href="mailto:{{ site.data.contacts.email }}">{{ site.data.contacts.email }}</a>
    </div>
  </footer>
</main>
