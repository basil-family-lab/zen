---
layout: default

css_id: home
---

<section id="hero">
  <h1>{{ site.home.hero.heading }}</h1>

  <p>{{ site.home.hero.body }}</p>

  <img
    src="/assets/images/profile.jpg"
    alt="{{ site.profile.name }}"
    class="profile-image"
  />
</section>

<section id="moment">
  <h2>{{ site.home.moment.heading }}</h2>

  {% for paragraph in site.home.moment.paragraphs %}
    <p>{{ paragraph }}</p>
  {% endfor %}
</section>

<section id="situations">
  <h2>{{ site.home.situations.heading }}</h2>

  {% for item in site.home.situations.items %}
    <h3>{{ item.subheading }}</h3>

    {% if item.paragraphs %}
      {% for paragraph in item.paragraphs %}
        <p>{{ paragraph }}</p>
      {% endfor %}
    {% endif %}

    {% if item.lines %}
      <p>{{ item.lines | join: '<br />' }}</p>
    {% endif %}

    {% if item.trailing_paragraph %}
      <p>{{ item.trailing_paragraph }}</p>
    {% endif %}
  {% endfor %}

  <p>
    <em>{{ site.home.situations.closing_emphasis }}</em>
  </p>
</section>

<section id="how-we-work">
  <h2>{{ site.home.how_we_work.heading }}</h2>

  {% for paragraph in site.home.how_we_work.paragraphs %}
    <p>{{ paragraph }}</p>
  {% endfor %}
</section>

<section id="framing">
  <h2>{{ site.home.framing.heading }}</h2>

  <h3>{{ site.home.framing.positives.heading }}</h3>
  <ul>
    {% for item in site.home.framing.positives.items %}
      <li>{{ item }}</li>
    {% endfor %}
  </ul>

  <h3>{{ site.home.framing.negatives.heading }}</h3>
  <ul>
    {% for item in site.home.framing.negatives.items %}
      <li>{{ item }}</li>
    {% endfor %}
  </ul>
</section>

<section id="about">
  <h2>{{ site.home.about.heading }}</h2>

  {% for paragraph in site.home.about.paragraphs %}
    <p>{{ paragraph }}</p>
  {% endfor %}
</section>

<section id="testimonials">
  <h2>{{ site.home.testimonials.heading }}</h2>

  {% for group in site.home.testimonials.groups %}
    <h3>{{ group.title }}</h3>
    <ul>
      {% for quote in group.quotes %}
        <li>{{ quote }}</li>
      {% endfor %}
    </ul>
  {% endfor %}
</section>

<section id="connect">
  <h2>{{ site.home.connect.heading }}</h2>

  <p>{{ site.home.connect.intro }}</p>

  <ul>
    {% for cta in site.home.connect.ctas %}
      <li>
        <a href="{{ site.action_links[cta.key] }}"
           data-ga-event="{{ cta.ga_event }}"
           data-ga-label="{{ cta.ga_label }}">
          {{ cta.label }}
        </a>
      </li>
    {% endfor %}
  </ul>
</section>
