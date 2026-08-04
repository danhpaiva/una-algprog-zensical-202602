# Algoritmos e Programação - UNA (2026/2)

Material didático da disciplina **Algoritmos e Programação** (UNA, semestre 2026/2), publicado como site estático com [Zensical](https://zensical.org) e hospedado no GitHub Pages.

🔗 **Site publicado:** https://danhpaiva.github.io/una-algprog-zensical-202602

## Estrutura de pastas

```
.
├── docs/                  # Todo o conteúdo publicado (único diretório lido pelo build)
│   ├── index.md           # Página inicial
│   ├── setup.md           # Guia de início rápido (não está no menu por padrão)
│   ├── ferramentas.md      # Página de ferramentas usadas na disciplina
│   ├── assets/             # Imagens e outros arquivos estáticos
│   ├── aulas/              # Uma página por aula (01-aula.md, 02-aula.md, ...)
│   ├── listas/              # Listas de exercícios (01-lista.md, 02-lista.md, ...)
│   └── trabalhos/           # Enunciados de projetos/trabalhos
├── mkdocs.yml              # Configuração do site (tema, navegação, extensões)
├── requirements.txt         # Dependências Python (Zensical)
├── .github/workflows/ci.yml # Pipeline de build e publicação (GitHub Actions)
└── site/                    # Saída do build (gerada localmente, ignorada pelo git)
```

Só o conteúdo dentro de `docs/` é publicado. Páginas que existem em `docs/` mas não aparecem no menu lateral (como `setup.md`, ou `trabalhos/projeto-01.md` enquanto a seção correspondente estiver comentada em `nav:` no `mkdocs.yml`) continuam acessíveis por URL direta — elas simplesmente não têm um link no menu.

> Se no futuro for necessário manter rascunhos que **não devem ser publicados de forma alguma**, mova-os para fora de `docs/` (por exemplo, uma pasta `rascunhos/` na raiz do repositório) — o Zensical publica tudo o que está em `docs_dir`, então a chave `exclude_docs` do MkDocs não é suportada como forma de esconder conteúdo.

## Como rodar localmente

Pré-requisito: Python 3.12+.

```bash
git clone https://github.com/danhpaiva/una-algprog-zensical-202602.git
cd una-algprog-zensical-202602

python -m venv venv
# Windows:
.\venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

pip install -r requirements.txt

zensical serve
```

Acesse `http://127.0.0.1:8000` no navegador. O servidor recarrega automaticamente ao salvar arquivos em `docs/` ou no `mkdocs.yml`.

Para gerar o site estático (o mesmo processo usado no CI) sem subir um servidor:

```bash
zensical build --strict
```

O resultado fica em `site/`.

## Como publicar (GitHub Pages)

O deploy é automático via GitHub Actions a cada push na branch `main`. Para habilitar em um repositório próprio (fork ou novo projeto a partir deste template):

1. **Settings → Actions → General → Workflow permissions**: selecione **"Read and write permissions"** e salve.
2. **Settings → Pages → Build and deployment → Source**: selecione **"GitHub Actions"** (não use *"Deploy from a branch"*).
3. Faça um `git push` para `main` — o workflow builda e publica o site automaticamente.

## Fluxo de branches do CI

O workflow em [`.github/workflows/ci.yml`](.github/workflows/ci.yml) roda em push para `main` e `develop`:

| Branch    | O que acontece                                                                 |
|-----------|---------------------------------------------------------------------------------|
| `develop` | Roda `zensical build --strict` só para validar que o build não quebra. Não publica. |
| `main`    | Roda o mesmo build e, em seguida, publica o resultado no GitHub Pages.           |

O job de build e o job de deploy são separados: se o deploy falhar por algo transitório, é possível re-executar apenas o job `deploy` sem reconstruir o site. O `concurrency` do workflow evita deploys simultâneos, mas nunca cancela um deploy de produção já em andamento.

## Como personalizar

Toda a configuração do site vive em [`mkdocs.yml`](mkdocs.yml) (o Zensical lê esse arquivo diretamente, sem precisar de conversão):

- **Nome da disciplina:** campo `site_name`.
- **URL do site e do repositório:** `site_url`, `repo_url` e `repo_name` — mantenha-os sincronizados com a URL real do `git remote -v` caso o repositório seja renomeado ou movido, senão o botão "editar página" e o sitemap ficam desatualizados sem gerar erro de build.
- **Menu lateral:** seção `nav:`.
- **Tema e cores:** seção `theme:` (paleta, fontes, features do Material).
- **Extensões de Markdown** (admonitions, abas, blocos de código com Mermaid, etc.): seção `markdown_extensions:`.

Não é necessário declarar um plugin de busca: a busca é nativa do Zensical e herda automaticamente o idioma configurado em `theme.language`.

## Licença

Distribuído sob a licença MIT. Veja [`LICENSE`](LICENSE) para o texto completo.
