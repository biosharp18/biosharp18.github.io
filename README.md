# biosharp18's website

Public address: <https://biosharp18.github.io>

This site uses the [Researcher theme](https://github.com/ankitsultana/researcher)
with Jekyll. GitHub Pages publishes the root folder of the `main` branch.

## Where to make changes

| What you want to change | File |
| --- | --- |
| Homepage introduction and publications | `index.markdown` |
| Profile photo | `assets/pic.JPEG` |
| Site name, description, and navigation links | `_config.yml` |
| Link color, photo size, and page width | `_sass/vars.scss` |
| Additional styling | `assets/main.scss` |

Keep the settings between the `---` lines at the top of each page. Edit the
text underneath using Markdown: `# Heading`, `**bold text**`, and
`[link text](https://example.com)`.

The site is a single-page research profile. Add publications to the numbered
list in `index.markdown`, including paper or code links when they are available.
The site title links back to the homepage, and the header links to GitHub.

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

From the repository, run:

```sh
./scripts/preview
```

Open <http://localhost:4000>. Leave the command running while you edit. Saving
a file rebuilds the preview; refresh your browser to see the result. Press
**Ctrl+C** to stop it. Restart it after changing `_config.yml`.

This checkout has a local Ruby installation in `vendor/ruby`, which the script
uses automatically. The `vendor/` folder is ignored by Git. On a different
computer, install Ruby 3.3 and Bundler first; the script will install the site's
dependencies when needed. The `github-pages` dependency matches GitHub Pages'
built-in Jekyll and plugin versions.

If you are editing on a remote server, forward port **4000** to your computer.
In VS Code Remote, use the **Ports** panel to forward it. Alternatively, run this
in a separate terminal on your own computer, using your usual SSH destination:

```sh
ssh -N -L 4000:127.0.0.1:4000 your-user@your-server
```

Then open <http://localhost:4000> on your computer. The preview is private to the
server and your SSH connection; it does not publish any edits to GitHub.

To check a build without running a server, in a terminal with Ruby and Bundler
available:

```sh
bundle exec jekyll build --strict_front_matter
```

## Visitor analytics

MapMyVisitors is included in `_layouts/default.html`, so visits to every page
using the shared layout can be counted. Its script is inside a hidden container:
the map does not appear on the website, but you can view statistics through
your MapMyVisitors account.

The widget loads only in production builds, including GitHub Pages. Normal
local previews do not load it or add preview visits to your statistics. Commit
and push changes to the layout to publish them.

## Theme source and license

Researcher was created by Ankit Sultana. The styles in `_sass/` were copied
from the upstream `gh-pages` branch at commit
`6e8d54c936da772028b5871e3626d070e17d3b3a`.

The layout in `_layouts/default.html` adapts Researcher's structure with working
home and stylesheet links, Jekyll SEO metadata, and accessible navigation.
The page layout is used for the 404 page. Unused sample pages, blog templates,
and styles have been removed. The original monospace font, narrow layout, and
red link color are retained. Theme attribution is kept here and in the license.

Researcher's theme code is licensed under GPL-3.0; see
[LICENSE-Researcher.txt](LICENSE-Researcher.txt). The theme is stored locally,
so changes to the upstream repository do not automatically change this site.
