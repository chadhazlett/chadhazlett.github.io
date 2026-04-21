# chadhazlett.com

Personal academic website, built with [Quarto](https://quarto.org) and
deployed to GitHub Pages at
[chadhazlett.github.io](https://chadhazlett.github.io) (later:
[chadhazlett.com](https://chadhazlett.com)).

## Local preview

```sh
~/opt/bin/quarto preview   # or `quarto preview` if on PATH
```

## Build + deploy

Every push to `main` triggers
[`.github/workflows/publish.yml`](./.github/workflows/publish.yml), which
renders with Quarto and publishes to the `gh-pages` branch.

## Updating publications

`publications.qmd` is plain markdown mirroring the CV. To add an entry,
edit that file directly, then commit and push. No bib file.

## Updating CV

Drop the new PDF at `assets/cv_hazlett_MMMYYYY.pdf` and update the link in
`cv.qmd`.
