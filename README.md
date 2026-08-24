# Manta Academy subject template

Use this repository template to create a publishable Manta Academy subject.
You only need to write Markdown, add assets, and configure optional interactive
tools. You do not need to know Nuxt or maintain a separate website repository.

Every push to `main` rebuilds the website and replaces the `gh-pages` branch in
the same repository.

## Create a subject

1. Create a repository from this template.
2. Add English subjects to `subjects/en` and French subjects to `subjects/fr`.
3. Put images and other static files in `assets`.
4. Copy `metadata.example.yml` to `metadata.yml` and configure any tools.
5. Push your changes to `main`.

For the first deployment, configure GitHub Pages to use **Deploy from a
branch**, select the `gh-pages` branch, and select the `/` folder. In the
repository's Actions settings, grant workflows read and write permissions.

## Subject content

Write subjects as Markdown files. Reef enables localization automatically:

- keep only `subjects/en` for an English-only site;
- keep only `subjects/fr` for a French-only site;
- keep both directories for a bilingual site with a locale switcher.

Assets keep their relative structure when copied to the generated website.

## Remote tools

A remote tool is downloaded from a public GitHub repository:

```yaml
tools:
  - id: match
    repository: MEA-RUN/match
    ref: main
```

`ref` may be a branch, tag, or commit SHA.

## Local tools

A tool specific to the subject can live directly in the repository:

```text
tools/
  my-tool/
    index.html
    style.css
    script.js
```

Reference it from `metadata.yml`:

```yaml
tools:
  - id: my-tool
    path: tools/my-tool
    name: My tool
```

Files referenced by `index.html` must use relative paths. Optional tool fields
include `entrypoint`, `icon`, `description`, `version`, and `category`.

## Use a tool in Markdown

Open a configured tool in Reef's right-hand panel with the `tools` MDC
component:

```mdc
:::tools{id="match"}
Open the matching tool
:::
```

## Organization repository security

For organization-owned repositories, deployment verifies that the actor has at
least write access. A pull request from a fork cannot publish anything until it
has been reviewed and merged into `main`. Protect `main` with the review rules
required by your organization.

## Repository structure

```text
.github/workflows/reef-deploy.yml
assets/
metadata.yml
subjects/
  en/
  fr/
tools/
```
