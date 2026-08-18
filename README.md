# Seminários Brasil

Agenda online de seminários sobre Algoritmos, Computação Teórica e áreas
próximas, publicada em <https://seminariosbtc.github.io>.

## Publicar pela primeira vez

O pacote está configurado para o repositório
`seminariosbtc/seminariosbtc.github.io`.

1. Extraia o arquivo ZIP.
2. Copie todo o conteúdo para a raiz do repositório.
3. Faça commit na branch `main`.
4. Em **Settings → Pages**, selecione **Deploy from a branch**.
5. Escolha `main`, a pasta `/ (root)` e salve.

## Estrutura

- `_seminars/`: um arquivo Markdown por seminário;
- `_layouts/seminar.html`: modelo comum das páginas individuais;
- `assets/slides/`: apresentações armazenadas no repositório;
- `_pages/agenda.md`: todos os seminários, sem filtros;
- `_pages/contato.md`: contato por e-mail;
- `assets/css/main.scss`: personalização do tema Minimal Mistakes.

## Adicionar um seminário

Duplique um arquivo em `_seminars/`, renomeie-o usando
`AAAA-MM-DD-titulo-curto.md` e preencha o cabeçalho:

```yaml
---
title: "Título da palestra"
event_date: "2026-09-10"
date_label: "10 de setembro de 2026"
day: "10"
month_short: "SET"
time: "15h"
topic: "Algoritmos"
topic_slug: "algoritmos"
speaker: "Nome da pessoa convidada"
affiliation: "Instituição"
series: "Nome da série"
event_link: "https://..."
slides:
recording:
---

Texto do resumo da palestra.
```

Todos os encontros são apresentados como online. A data determina
automaticamente se o seminário aparece entre os próximos ou no arquivo.

## Apresentação e gravação

Coloque apresentações em `assets/slides/` e preencha:

```yaml
slides: "/assets/slides/nome-do-arquivo.pdf"
recording: "https://..."
```

A página individual sempre mostra as áreas de resumo, link e arquivo. Quando
um material ainda não existe, ela exibe “Ainda não disponível”.

## Contato

Sugestões, correções e materiais podem ser enviados para
[seminariosbtc@gmail.com](mailto:seminariosbtc@gmail.com).

Os eventos e nomes atualmente incluídos são ilustrativos e podem ser removidos
ou substituídos pelos seminários reais.
