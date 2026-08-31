# Mayowa Adebambo — Engineering Portfolio

Source code and content for Mayowa Adebambo's multidisciplinary engineering portfolio, covering artificial intelligence, mechanical engineering, robotics, data science, embedded systems, and research.

The site is built with [Hugo](https://gohugo.io/) and [Hugo Blox](https://hugoblox.com/), with automated deployment to GitHub Pages.

## Local development

Requirements:

- Hugo Extended
- Node.js
- pnpm 10

Install the frontend dependencies and start the development server:

```bash
pnpm install
pnpm dev
```

Create a clean production build:

```bash
pnpm build
```

The generated site is written to `public/`. Build output, processed resources, dependencies, and private source documents are excluded from Git.

## Repository structure

```text
assets/              Custom CSS and site-wide images
config/_default/     Hugo and Hugo Blox configuration
content/             Homepage and project content
data/authors/        Profile, experience, skills, awards, and languages
layouts/             Custom Hugo blocks and template overrides
static/uploads/      Public CV and recruiter-facing PDF documents
source-documents/    Local editable research sources (ignored by Git)
```

Each project is a Hugo page bundle under `content/projects/<project-name>/`. Its `index.md` contains the page content and metadata, while project images and videos live alongside it.

## Deployment

Pushing the `main` branch triggers the GitHub Pages workflow in `.github/workflows/deploy.yml`. The production workflow performs a clean Hugo build and supplies the exact GitHub Pages base URL automatically.

The fallback URL used for local production metadata is configured in `config/_default/hugo.yaml`.

