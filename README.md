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

1. Visit [your Scholar profile](https://scholar.google.com/citations?user=pbD0dGwAAAAJ).
2. Select all entries, Export → BibTeX → "Export all my articles".
3. Save over `references.bib`.
4. (Optional) Tidy: `npx bibtex-tidy --curly --numeric --sort=-year references.bib`
5. Commit + push.

## Updating CV

Drop the new PDF at `assets/cv_hazlett_MMMYYYY.pdf` and update the link in
`cv.qmd`.
