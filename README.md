# danolivo.github.io

Personal site. Jekyll 4, no theme gem, no JavaScript, no external assets.

## Local build

```bash
bundle install
bundle exec jekyll serve
```

Ruby 4 works. The `github-pages` gem does **not** — it pins Jekyll 3.10, whose
dependency chain requires Ruby < 4. That is why deployment goes through
`.github/workflows/pages.yml` instead of the classic Pages builder, and why
**Settings → Pages → Source must be set to "GitHub Actions"**.

## Adding content

All content lives in `_data/`; the pages are templates over it.

| File                     | Holds                                              |
|--------------------------|----------------------------------------------------|
| `_data/publications.yml` | journal articles, conference papers, thesis        |
| `_data/talks.yml`        | conference and meetup talks                        |
| `_data/projects.yml`     | systems, extensions, planner experiments           |
| `_data/awards.yml`       | grants, awards, registered software                |
| `_data/cv.yml`           | experience, education, certifications              |

Adding a talk is three lines of YAML. Each file documents its own fields at the
top.

`featured: true` on a project promotes it to the "What I am working on" list on
the home page; `summary:` is the one-line wording used there.

## Papers and slides

Copies live in the companion [conf](https://github.com/danolivo/conf) repository,
not here — it is 600 MB, including a 79 MB slide deck. `site.materials` in
`_config.yml` is the base URL; `pdf:` and `slides:` entries are paths relative to
it.

Two conventions worth keeping:

- CFD-era entries (2012–2017) carry no `pdf:`. They are listed
  bibliographically, linking public proceedings where those exist online.
- A `pdf:`/`slides:` path must point at a file actually committed and pushed to
  `conf`, otherwise the link 404s. Check before adding.
