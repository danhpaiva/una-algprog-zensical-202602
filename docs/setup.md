# 🛠️ Guia de Início Rápido

Este template foi desenvolvido para facilitar a criação de materiais didáticos modernos e automatizados para a UNA, usando [Zensical](https://zensical.org) para gerar o site. Siga os passos abaixo para configurar seu ambiente.

---

## 1. Configuração Local

Para editar e visualizar o site em sua máquina:

1. **Clone o repositório:**

```bash
git clone https://github.com/danhpaiva/una-algprog-zensical-202602.git
cd una-algprog-zensical-202602

```

2. **Crie e ative o ambiente virtual:**

```bash
python -m venv venv
# No Windows:
.\venv\Scripts\activate
# No Linux/Mac:
source venv/bin/activate

```

3. **Instale as dependências:**

```bash
pip install -r requirements.txt

```

4. **Inicie o servidor de visualização:**

```bash
zensical serve

```

Acesse `http://127.0.0.1:8000` no seu navegador.

---

## 🚀 Publicação Automática (GitHub Pages)

O deploy está configurado via **GitHub Actions**. Para que funcione corretamente em seu próprio repositório:

1. Vá em **Settings > Actions > General**.
2. Em **Workflow permissions**, selecione **"Read and write permissions"** e salve.
3. Vá em **Settings > Pages** e em **Build and deployment > Source**, escolha **"GitHub Actions"** (não use *"Deploy from a branch"*).
4. Ao fazer um `git push` para a branch `main`, o site é publicado automaticamente. A branch `develop` apenas valida o build, sem publicar.

---

## 🎨 Personalização

* **Nome da Disciplina:** Altere o campo `site_name` no arquivo `mkdocs.yml`.
* **Menu Lateral:** Organize suas aulas e pastas na seção `nav:` do `mkdocs.yml`.
* **Cores e Temas:** Você pode alterar a cor primária de `indigo` para outras cores (ex: `red`, `blue`, `deep-purple`) no `mkdocs.yml`.

---

### 💡 Dica para o Professor

Para criar caixas de destaque (Admonitions), utilize a sintaxe abaixo nos seus arquivos Markdown:

```markdown
!!! tip "Dica"
    Seu conteúdo aqui com recuo de 4 espaços.

!!! info "Importante"
    Este template já conta com suporte a modo escuro automático!

```