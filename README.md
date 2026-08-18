# Seminários Brasil

Agenda de seminários brasileiros sobre Algoritmos, Computação Teórica e áreas
próximas, publicada em <https://seminariosbtc.github.io>.

## Publicar pela primeira vez

Este pacote já está configurado para o repositório
`seminariosbtc/seminariosbtc.github.io`.

1. Extraia o arquivo ZIP.
2. Copie **todo o conteúdo extraído** para a raiz do repositório, incluindo as
   pastas ocultas `.github` e o arquivo `.gitignore`.
3. Faça commit na branch `main`.
4. No GitHub, abra **Settings → Pages**.
5. Em **Build and deployment**, selecione **Deploy from a branch**.
6. Escolha a branch `main`, a pasta `/ (root)` e salve.

O GitHub Pages fará a compilação com Jekyll. Como este é um repositório de
usuário (`seminariosbtc.github.io`), o site usa `baseurl: ""` e não precisa de
nenhum ajuste adicional de caminhos.

## Base visual e técnica

- GitHub Pages + Jekyll;
- tema remoto
  [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes), versão
  4.28.1;
- skin clara e minimalista;
- próximo seminário calculado automaticamente pela data;
- arquivo de seminários anteriores com links opcionais para slides e gravação;
- formulário de colaboração por GitHub Issues.

## Estrutura

- `_seminars/`: um arquivo Markdown por seminário;
- `assets/slides/`: apresentações armazenadas no próprio repositório;
- `_posts/`: notas e atualizações do Caderno;
- `_pages/agenda.md`: agenda geral com filtro por área;
- `.github/ISSUE_TEMPLATE/novo-seminario.yml`: formulário comunitário;
- `assets/css/main.scss`: personalização do tema.

## Adicionar um seminário

1. Duplique um arquivo em `_seminars/`.
2. Renomeie-o usando `AAAA-MM-DD-titulo-curto.md`.
3. Atualize data, tema, formato, pessoa convidada, instituição, série e local.
4. Substitua o resumo demonstrativo pelo texto oficial.
5. Faça commit. A data determina automaticamente se o seminário aparece como
   próximo, futuro ou no arquivo.

## Adicionar apresentação ou gravação

Coloque o arquivo da apresentação em `assets/slides/` e adicione ao cabeçalho
do seminário:

```yaml
slides: "/assets/slides/nome-do-arquivo.pdf"
```

Para uma gravação externa, use:

```yaml
recording: "https://..."
```

Os links aparecem automaticamente na página inicial e na página do seminário.

## Receber sugestões

Habilite **Issues** em **Settings → General → Features**. O botão “Envie um
seminário” abrirá o formulário configurado em `.github/ISSUE_TEMPLATE/`.

Os eventos e nomes atualmente incluídos são ilustrativos e podem ser removidos
ou substituídos pelos seminários reais.
