# jaja ♡ — blog pessoal de tecnologia

Blog pessoal estático feito com **Jekyll**, **Markdown** e **GitHub Pages**. Sem backend, sem banco de dados, sem login.

🔗 Publicado em: `https://milly5ants.github.io/mily_labs/`

## Rodando localmente

Pré-requisitos: [Ruby](https://www.ruby-lang.org/en/documentation/installation/) e Bundler instalados.

```bash
bundle install
bundle exec jekyll serve
```

O site vai estar disponível em `http://localhost:4000/mily_labs/`.

## Como criar um novo post

1. Crie um arquivo dentro de `_posts/` seguindo o padrão de nome:

   ```
   AAAA-MM-DD-titulo-do-post.md
   ```

   Exemplo: `_posts/2026-08-16-comecando-a-estudar-java.md`

2. Adicione o front matter no topo do arquivo:

   ```yaml
   ---
   layout: post
   title: "Começando a estudar Java"
   date: 2026-08-16
   category: "Java"
   description: "Os primeiros passos de uma nova fase nos meus estudos."
   image: "/assets/images/java.jpg"
   read_time: "5 min"
   ---
   ```

3. Escreva o conteúdo do post em Markdown normalmente, abaixo do front matter.

4. Pronto — o Jekyll gera a página do post automaticamente e ele passa a aparecer:
   - na home, se estiver entre os 3 mais recentes;
   - em `/posts/`, na listagem completa.

Campos do front matter:

| Campo         | Obrigatório | Descrição                                   |
|---------------|:-----------:|----------------------------------------------|
| `title`       | sim         | Título do post                                |
| `date`        | sim         | Data de publicação                            |
| `category`    | sim         | Categoria exibida no card (ex: "Java")        |
| `description` | sim         | Resumo curto exibido no card                  |
| `image`       | não         | Caminho da imagem de capa                     |
| `read_time`   | não         | Texto livre, ex: "5 min"                      |

## Como adicionar imagens

Coloque o arquivo em `assets/images/` e referencie no front matter:

```yaml
image: "/assets/images/java.jpg"
```

Para imagens dentro do conteúdo do post, use Markdown normal:

```markdown
![Descrição da imagem](/assets/images/exemplo.jpg)
```

> As imagens de capa incluídas neste projeto (`java.jpg`, `todo-list.jpg`, `aprendendo-2026.jpg`) são ilustrações placeholder geradas para manter a identidade visual — sinta-se à vontade para substituí-las por fotos ou artes suas.

## Estrutura do projeto

```
/
├── _config.yml
├── _layouts/
│   ├── default.html      # layout base (header + footer)
│   └── post.html         # layout de post individual
├── _includes/
│   ├── header.html
│   ├── footer.html
│   ├── post-card.html
│   ├── illustration-hero.html
│   └── illustration-about.html
├── _posts/                # seus posts em Markdown
├── assets/
│   ├── css/style.css
│   ├── js/script.js
│   └── images/
├── posts/index.html       # listagem de todos os posts
├── projetos/index.html    # página de projetos
├── sobre/index.html       # página sobre
├── index.html             # home
└── README.md
```

## Adicionar um projeto

Edite `projetos/index.html` e duplique um bloco `<article class="project-card">` com nome, descrição, tecnologias e link do GitHub.

## Publicando no GitHub Pages

1. Crie o repositório `mily_labs` na conta `milly5ants`.
2. Suba todos os arquivos deste projeto para a branch `main`.
3. Em **Settings → Pages**, selecione a branch `main` e a pasta raiz (`/`).
4. Aguarde alguns minutos — o site ficará disponível em `https://milly5ants.github.io/mily_labs/`.

Todos os links internos usam `relative_url`, então o site funciona corretamente dentro do subdiretório `/mily_labs/`.
