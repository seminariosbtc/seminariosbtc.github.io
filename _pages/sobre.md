---
title: "Quem somos"
permalink: /quem-somos/
excerpt: "Conheça as pessoas que mantêm a agenda."
---

<section class="sb-about-copy" aria-labelledby="about-project-title">
  <p class="sb-kicker">O projeto</p>
  <h2 id="about-project-title">Sobre nós</h2>

  <p>
    O projeto dos Seminários Brasileiros de Teoria da Computação é uma iniciativa de estudantes de doutorado brasileiros para incentivar a colaboração entre pesquisadores de diferentes áreas e grupos de Teoria da Computação no Brasil. Temos como principal motivação garantir que os estudantes de pós-graduação tenham acesso a diferentes tópicos, grupos de pesquisa, e outros pesquisadores, uma vez que a participação em eventos presenciais encontra obstáculos financeiros dada a grandeza territorial do país e no número de eventos locais da área.
  </p>
</section>

<section class="sb-team-section" aria-labelledby="team-title">
  <p class="sb-kicker">Equipe</p>
  <h2 id="team-title">Pessoas</h2>

  <div class="sb-team-grid">
    {% for person in site.data.team %}
      {% assign person_name = person.name | default: "Nome da pessoa" %}
      <article class="sb-person">
        <div class="sb-person__photo">
          {% if person.photo %}
            <img src="{{ person.photo | relative_url }}" alt="Foto de {{ person_name }}">
          {% else %}
            <span>Foto</span>
          {% endif %}
        </div>

          <h3>{% if person.profile_url %}
                <a
                  class="sb-person__name-link"
                  href="{{ person.profile_url }}"
                  target="_blank"
                  rel="noopener noreferrer">
                  {{ person_name }}
                </a>
              {% else %}
                {{ person_name }}
              {% endif %}
          </h3>
        <p>{{ person.institution | default: "Instituição" }}</p>

        {% if person.email %}
          <a href="mailto:{{ person.email }}">{{ person.email }}</a>
        {% else %}
          <span class="sb-person__email">email@instituicao.br</span>
        {% endif %}
      </article>
    {% endfor %}
  </div>
</section>
