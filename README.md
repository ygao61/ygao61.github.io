# ygao61.github.io

Personal academic site for Yuan Gao, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme (MIT).

## Run it locally

This machine needs Ruby 3.3 (the system Ruby 2.6 is too old, and Ruby 4.x can't build the
native gems with the Command Line Tools installed here):

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
export LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8   # the build reads files as US-ASCII without this
bundle install
bundle exec jekyll serve
```

Then open <http://127.0.0.1:4000>. The server rebuilds on save.

## Where the content lives

| What | File |
| --- | --- |
| Name, site URL, feature toggles | `_config.yml` |
| Homepage bio | `_pages/about.md` |
| Publications | `_bibliography/papers.bib` |
| News items on the homepage | `_news/*.md` (one file each) |
| Project pages and cards | `_projects/*.md` |
| CV page contents | `_data/cv.yml` |
| CV PDF (download button) | `assets/pdf/Yuan_Gao_CV.pdf` |
| Email, Scholar, GitHub, LinkedIn | `_data/socials.yml` |
| Repos shown on `/code/` | `_data/repositories.yml` |
| Journal badge colors | `_data/venues.yml` |
| Co-author name → link | `_data/coauthors.yml` |

Adding a publication means adding a BibTeX entry — set `selected = {true}` to also surface it on
the homepage, and `abbr` to control the colored venue badge.

## Things left to do

- Replace `assets/img/prof_pic.svg` with a real photo (any square JPG/PNG; update `image:` in
  `_pages/about.md` to match the filename).
- The blog is wired up but hidden from the nav (`nav: false` in `_pages/blog.md`). Drop a post in
  `_posts/` and flip it back on if you want one.
- `imagemagick` is disabled in `_config.yml` because it isn't installed locally. CI installs it,
  so you can turn it back on for responsive WebP if you install it here too (`brew install imagemagick`).

## Deploying

`.github/workflows/deploy.yml` builds on every push to `main` and publishes `_site` to the
`gh-pages` branch. In the repo's **Settings → Pages**, set the source to the `gh-pages` branch.
