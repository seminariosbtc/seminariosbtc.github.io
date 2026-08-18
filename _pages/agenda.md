---
title: "Agenda"
permalink: /agenda/
excerpt: "Próximos seminários, colóquios e encontros acadêmicos."
---

<p class="sb-page-lead">
  Encontros presenciais, híbridos e online reunidos em uma única agenda.
  Nesta demonstração, os eventos são ilustrativos.
</p>

<div class="sb-agenda-tools" role="group" aria-label="Filtrar eventos por área">
  <button class="sb-filter is-active" type="button" data-filter="todos" aria-pressed="true">Todos</button>
  <button class="sb-filter" type="button" data-filter="algoritmos" aria-pressed="false">Algoritmos</button>
  <button class="sb-filter" type="button" data-filter="combinatoria" aria-pressed="false">Combinatória</button>
  <button class="sb-filter" type="button" data-filter="logica" aria-pressed="false">Lógica</button>
  <button class="sb-filter" type="button" data-filter="otimizacao" aria-pressed="false">Otimização</button>
</div>

<div class="sb-event-list" id="agenda-list">
  {% assign agenda = site.seminars | sort: "event_date" %}
  {% for event in agenda %}
    <a class="sb-event" data-topic="{{ event.topic_slug }}" href="{{ event.url | relative_url }}">
      <div class="sb-date" aria-label="{{ event.date_label }}">
        <span>{{ event.month_short }}</span>
        <strong>{{ event.day }}</strong>
      </div>
      <div>
        <span class="sb-event__topic">{{ event.topic }} · {{ event.format }}</span>
        <h3>{{ event.title }}</h3>
        <p>{{ event.speaker }} · {{ event.affiliation }}</p>
      </div>
      <div class="sb-event__place">
        <strong>{{ event.series }}</strong>
        <span>{{ event.location }} · {{ event.time }}</span>
      </div>
      <span class="sb-event__arrow" aria-hidden="true">↗</span>
    </a>
  {% endfor %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const filters = document.querySelectorAll(".sb-filter");
    const events = document.querySelectorAll("#agenda-list .sb-event");

    filters.forEach(function (filter) {
      filter.addEventListener("click", function () {
        const selected = filter.dataset.filter;
        filters.forEach(function (item) {
          const active = item === filter;
          item.classList.toggle("is-active", active);
          item.setAttribute("aria-pressed", active ? "true" : "false");
        });
        events.forEach(function (event) {
          event.hidden = selected !== "todos" && event.dataset.topic !== selected;
        });
      });
    });
  });
</script>
