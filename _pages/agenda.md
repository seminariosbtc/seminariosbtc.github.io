---
title: "Agenda"
permalink: /agenda/
excerpt: "Todos os seminários da agenda."
---

<p class="sb-page-lead">
  Todos os seminários são online e permanecem visíveis nesta página depois da
  data do encontro.
</p>

{% assign today = "now" | date: "%Y%m%d" %}
{% assign agenda = site.seminars | sort: "event_date" %}

<section class="sb-agenda-section" aria-labelledby="agenda-upcoming">
  <p class="sb-kicker">Agenda</p>
  <h2 id="agenda-upcoming">Próximos seminários</h2>

  <div class="sb-event-list">
    {% assign upcoming_count = 0 %}
    {% for event in agenda %}
      {% assign event_day = event.event_date | date: "%Y%m%d" %}
      {% if event_day >= today %}
        <a class="sb-event" href="{{ event.url | relative_url }}">
          <div class="sb-date" aria-label="{{ event.date_label }}">
            <span>{{ event.month_short }}</span>
            <strong>{{ event.day }}</strong>
          </div>
          <div>
            <h3>{{ event.title }}</h3>
            <p>{{ event.speaker }} · {{ event.affiliation }} · {{ event.topic }} · {{ event.time }}</p>
          </div>
          <span class="sb-event__arrow" aria-hidden="true">→</span>
        </a>
        {% assign upcoming_count = upcoming_count | plus: 1 %}
      {% endif %}
    {% endfor %}

    {% if upcoming_count == 0 %}
      <p class="sb-empty-line">Nenhum seminário futuro anunciado por enquanto.</p>
    {% endif %}
  </div>
</section>

<section class="sb-agenda-section" aria-labelledby="agenda-past">
  <p class="sb-kicker">Arquivo</p>
  <h2 id="agenda-past">Seminários anteriores</h2>

  <div class="sb-event-list">
    {% assign past_agenda = agenda | reverse %}
    {% assign past_count = 0 %}
    {% for event in past_agenda %}
      {% assign event_day = event.event_date | date: "%Y%m%d" %}
      {% if event_day < today %}
        <a class="sb-event" href="{{ event.url | relative_url }}">
          <div class="sb-date" aria-label="{{ event.date_label }}">
            <span>{{ event.month_short }}</span>
            <strong>{{ event.day }}</strong>
          </div>
          <div>
            <h3>{{ event.title }}</h3>
            <p>{{ event.speaker }} · {{ event.affiliation }} · {{ event.topic }} · {{ event.time }}</p>
          </div>
          <span class="sb-event__arrow" aria-hidden="true">→</span>
        </a>
        {% assign past_count = past_count | plus: 1 %}
      {% endif %}
    {% endfor %}

    {% if past_count == 0 %}
      <p class="sb-empty-line">O arquivo será preenchido após o primeiro seminário.</p>
    {% endif %}
  </div>
</section>
