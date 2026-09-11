# ygao61.github.io

Personal site for **Yuan Gao** — live at <https://ygao61.github.io>.

Built on [al-folio](https://github.com/alshedivat/al-folio) (MIT), trimmed to three pages:
**About** (homepage), **Publications** (a section of the homepage, reached from the navbar),
and **GitHub**.

## Running it locally

The system Ruby (2.6) is too old, and Ruby 4.x cannot build the native gems against the Command
Line Tools installed on this machine. Use Homebrew's Ruby 3.3:

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
export LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8   # the build reads files as US-ASCII without this
bundle install
bundle exec jekyll serve
```

Then open <http://127.0.0.1:4000>. It rebuilds on save.

Both exports matter. Without the UTF-8 locale the build crashes on the first non-ASCII character
in the content; without the Ruby 3.3 path `bundle install` fails compiling `bigdecimal`.

## Where the content lives

| What | File |
| --- | --- |
| Homepage text, skills list, photo, address | `_pages/about.md` |
| Publications | `_bibliography/papers.bib` |
| Venue name colours (light + dark) | `_data/venues.yml` |
| Co-author name → link | `_data/coauthors.yml` |
| GitHub / LinkedIn / Scholar links | `_data/socials.yml` |
| Repos listed on `/code/` | `_data/repositories.yml` |
| News items (not shown on the homepage) | `_news/*.md` |
| Preview figures | `assets/img/publication_preview/` |
| Profile photo | `assets/img/prof_pic.jpg` |
| Name, site URL, feature toggles, page width | `_config.yml` |

### Adding a publication

Add a BibTeX entry to `_bibliography/papers.bib`. Beyond the standard fields:

- `abbr` — picks the venue colour from `_data/venues.yml` (no badge is drawn any more).
- `preview` — a filename in `assets/img/publication_preview/`.
- `code`, `demo`, `webserver` — each renders one link chip. `doi` renders the `Paper` chip.
  A field you leave out simply produces no chip.

`demo` and `webserver` are not al-folio fields; they are defined in `_layouts/bib.liquid` and
filtered out of the BibTeX popup via `filtered_bibtex_keywords` in `_config.yml`.

## Theme overrides

These shadow files inside the `al_folio_core` gem. Upgrading the gem will not update them, so
check them if something breaks after a `bundle update`:

| File | Why it exists |
| --- | --- |
| `_includes/header.liquid` | Navbar builds hrefs from page permalinks, which cannot express `/#publications` |
| `_includes/selected_papers.liquid` | Upstream hardcodes `--group_by none`; the homepage groups by year |
| `_layouts/about.liquid` | Social icons moved into the profile column; heading renamed and given an anchor |
| `_layouts/bib.liquid` | Venue colour on the name instead of a badge; Paper/GitHub/Demo/Webserver chips |
| `_sass/_custom.scss` | Profile width, icon size, link chips, venue colours, anchor scroll offset |
| `assets/css/main.scss` | Copy of the gem's entry point, with `@use "custom"` appended |

## Deploying

`.github/workflows/deploy.yml` builds on every push to `main` and publishes `_site` to the
`gh-pages` branch, which **Settings → Pages** serves from. `update-citations.yml` refreshes
Google Scholar citation counts into `_data/citations.yml` on a schedule.

## Deliberately not here

- **No CV PDF.** The CV goes out as an attachment when applying; hosting it would put a phone
  number on a public, indexable page. It was removed from the git history as well.
- **No plain-text email.** The address on the homepage is written `ygao61 [at] umd [dot] edu`
  and there are no `mailto:` links anywhere in the built site.
- **`imagemagick: false`** in `_config.yml`, because it is not installed locally. CI does install
  it, so responsive WebP can be turned back on after `brew install imagemagick`.
- **The blog is wired up but hidden** (`nav: false` in `_pages/blog.md`). Drop a file in `_posts/`
  and flip it back on.
