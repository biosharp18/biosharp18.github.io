# biosharp18's website

Public address: <https://biosharp18.github.io>

This site uses the [Researcher theme](https://github.com/ankitsultana/researcher)
with Jekyll. GitHub Pages publishes the root folder of the `main` branch.

## Where to make changes

| What you want to change | File |
| --- | --- |
| Homepage introduction | `index.markdown` |
| About page | `about.markdown` |
| Site name, description, and navigation links | `_config.yml` |
| Blog posts | `_posts/` |
| Link color and page width | `_sass/vars.scss` |
| Additional styling | `assets/main.scss` |

Keep the settings between the `---` lines at the top of each page. Edit the
text underneath using Markdown: `# Heading`, `**bold text**`, and
`[link text](https://example.com)`.

The existing "Welcome to Jekyll!" post is an example. You can edit it, remove it,
or add posts named `YYYY-MM-DD-your-title.markdown`. New posts need a header like:

```yaml
---
layout: post
title: "My first post"
date: 2026-11-09
---
```

The homepage automatically lists published posts. If there are no posts, the
Posts section disappears.

To add a resume, upload your own PDF to `assets/resume.pdf`, then add a link
under `nav` in `_config.yml`:

```yaml
  - name: Resume
    link: /assets/resume.pdf
```

## Publish an update

On GitHub, open the file, click the pencil icon, make your changes, and commit
them to `main`. GitHub Pages will rebuild the website. You can check progress
under the repository's **Actions** tab or **Settings → Pages**.

When editing this checkout locally, commit your changes and push them to
`origin/main` to publish. Local edits alone do not update the public website.

## Preview locally

Install Ruby 3.3 and Bundler, then run these commands in the repository:

```sh
bundle install
bundle exec jekyll serve
```

Open <http://localhost:4000>. Restart the server after changing `_config.yml`.
The `github-pages` dependency matches GitHub Pages' built-in Jekyll and plugin
versions. To check a build without running a server:

```sh
bundle exec jekyll build --strict_front_matter
```

## Theme source and license

Researcher was created by Ankit Sultana. The styles in `_sass/` were copied
from the upstream `gh-pages` branch at commit
`6e8d54c936da772028b5871e3626d070e17d3b3a`.

The layout in `_layouts/default.html` adapts Researcher's structure with working
home and stylesheet links, Jekyll SEO/feed metadata, and accessible navigation.
Additional layouts support this site's homepage, pages, and existing posts.
The original monospace font, narrow layout, and red link color are retained.

Researcher's theme code is licensed under GPL-3.0; see
[LICENSE-Researcher.txt](LICENSE-Researcher.txt). The theme is stored locally,
so changes to the upstream repository do not automatically change this site.
