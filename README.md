# Noahs-ARK.github.io

Source for the website of [Noah's ARK](https://noahs-ark.github.io), Noah Smith's research group. Built with [Jekyll](https://jekyllrb.com) and hosted on [GitHub Pages](https://pages.github.com), which rebuilds and redeploys automatically on every push to `master`.

## Credits

This site is built on the [academicpages](https://github.com/academicpages/academicpages.github.io) template, created by [Stuart Geiger](https://github.com/staeiou), which is itself a fork of the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) Jekyll theme by [Michael Rose](https://github.com/mmistakes) (© 2016, MIT License — see [LICENSE](LICENSE)). Icon sets vendored under `assets/fonts/` are [Font Awesome](https://fontawesome.com) and [Academicons](https://jpswalsh.github.io/academicons/).

## Local development

The site needs a Ruby that isn't the macOS system Ruby (too old, and on Apple Silicon its native gems are the wrong architecture). This repo is set up to use [rbenv](https://github.com/rbenv/rbenv) with Ruby 3.3.12 (pinned in `.ruby-version`).

One-time setup, if rbenv/Ruby 3.3.12 aren't already installed:

```bash
# install rbenv + ruby-build (see https://github.com/rbenv/rbenv#installation)
rbenv install 3.3.12
```

Then, from the repo root:

```bash
export LANG=en_US.UTF-8   # required - without it, Sass fails on non-ASCII characters
bundle install             # installs gems into vendor/bundle (gitignored)
bundle exec jekyll serve --livereload
```

The site will be at `http://localhost:4000`.

## Content

**People.** `_pages/people.md` renders tables from `_data/members.csv`, `_data/phdalumni.csv`, `_data/postdocalumni.csv`, `_data/mastersalumni.csv`, and `_data/otheralumni.csv`. Each row's `image` column points at a photo in `images/` — current members and alumni are each given a whimsically-named "collective noun" animal photo (`camp_of_chameleons.jpg`, `herd_of_manatees.jpg`, etc.) as their avatar. Add a person by adding a row to the relevant CSV and a matching image to `images/`.

**Publications.** Linked externally to `nasmith.github.io/publications` (see `_data/navigation.yml`) rather than maintained in this repo.

## Notes

- `files/` holds PDFs and other downloads linked directly from pages. Anything placed here is publicly reachable at `https://noahs-ark.github.io/files/<name>`, linked or not — treat it as published the moment it's committed.
- `package.json` / the npm `uglify` script is theme build tooling that regenerates `assets/js/main.min.js` from the vendored jQuery plugins under `assets/js/plugins`. It's rarely touched; you only need it if you change those plugin sources.
