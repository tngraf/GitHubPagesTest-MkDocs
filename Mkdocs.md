# MkDocs

**MkDocs** is a greate tool to create statics websites for documentation.  
**Material for MkDocs** significantly enhances the MkDocs functionality.

## Setup for MkDocs

Create a basic Python Poetry project with a `pyproject.toml` similar to this one:

```code
[tool.poetry]
name = "GitHubPagesTest"
version = "0.1.0"
description = ""

[tool.poetry.dependencies]
python = "^3.12"
mkdocs = "^1.6.1"

[build-system]
requires = ["poetry-core"]
build-backend = "poetry.core.masonry.api"
```

Install all dependencies:

```code
poetry install --no-root
```

Either use MkDocs to create initial data by calling

```code
poetry run MkDocs new
```

**or** create a file `mkdocs.yml` with the following contents

```code
site_name: GitHubPagesTest

nav:
  - Home: index.md
```

**and** create a folder `docs` that contains a file `index.md` with the contents

```code
# Welcome to MkDocs

Test 1
```

### Build MkDocs Pages

Build MkDocs pages with the command

```code
poetry run MkDocs build
```

This will create a folder `site` that contains the HTML code of the pages.

### Live Preview

You can always have a live preview of your pages by running

```code
poetry run MkDocs server
```

The pages will be available by the address <http://127.0.0.1:8000/>.

### Deploy MkDocs to GitHub Pages

There is direct support to deploy to GitHub (Project) Pages:

Project Pages sites are simpler as the site files get deployed to a branch within the project repository (gh-pages by default). After you checkout the primary working branch (usually master) of the git repository where you maintain the source documentation for your project, run the following command:

```code
mkdocs gh-deploy
```

That's it! Behind the scenes, MkDocs will build your docs and use the `ghp-import` tool to commit them to the gh-pages branch and push the gh-pages branch to GitHub.

## Switch to Material for MkDocs

Install mkdocs material

```code
poetry add mkdocs-material
```

### Admonitions (aka Callouts)

Admonitions - also known as callouts - are great for highlighting parts of the documentation.

To enable them, add this configuration to the `mkdocs.yml`:

```code
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
```

* Create a new page called admonitions.md
* This is an example of an adominition with a title:

```code
!!! note "Title of the callout"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.
```

## Resources

* [MkDocs](https://www.mkdocs.org/)
* [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
* [Material for MkDocs: Full Tutorial To Build And Deploy Your Docs Portal](https://www.youtube.com/watch?v=xlABhbnNrfI)
* [Written Guide](https://jameswillett.dev/getting-started-with-material-for-mkdocs/)
* [GitHub Demo Repo](https://github.com/james-willett/material-mkdocs-youtube-2024)
