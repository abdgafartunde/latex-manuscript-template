# LaTeX Manuscript Template

A clean, reusable LaTeX template for computational and applied mathematics research papers. Designed for quick cloning or downloading when starting a new manuscript.

## Quick Start

```bash
# Compile
pdflatex main
bibtex main
pdflatex main
pdflatex main

# Or with latexmk (recommended)
latexmk -pdf main
```

## Project Structure

```
.
├── main.tex                  # Main document: packages, theorem environments, custom commands, title block
├── references.bib            # Bibliography file (template with one example entry)
├── CITATION.cff              # Citation metadata (for GitHub + Zenodo)
├── .gitignore                # Ignores LaTeX build artifacts
├── figures/
│   └── .gitkeep              # Place your figure files (PDF, PNG, EPS) here
├── sections/
│   ├── introduction.tex      # Introduction
│   ├── setting.tex           # Problem formulation / setting
│   ├── method.tex            # Method / main contribution
│   ├── numerics.tex          # Numerical experiments
│   └── conclusion.tex        # Conclusion
└── README.md
```

## Customization Checklist

When starting a new paper, update the following in `main.tex`:

- [ ] `\title{...}` — paper title
- [ ] `\author{...}` — author names, affiliations, corresponding author email
- [ ] Abstract content
- [ ] Keywords
- [ ] Section files (in `sections/`) — replace placeholder text with your content
- [ ] Bibliography (`references.bib`) — add your references
- [ ] If needed, uncomment optional sections (Related Work, Preliminaries, Appendix, Acknowledgments)

## Optional Sections

The template includes commented-out stubs for common additional sections. Uncomment and rename as needed:

- **Related Work** — separate from Introduction for papers with extensive prior work
- **Preliminaries** — for notation-heavy or theory papers
- **Appendix** — for supplementary proofs or additional experiments
- **Acknowledgments** — for funding and colleague acknowledgments

## Template Features

- **Theorem environments**: theorem, proposition, lemma, corollary, definition, assumption, remark — all share a common counter, with `\cref`/`\Cref` support
- **Custom math commands**: common shortcuts for blackboard bold, calligraphic, norms, inner products, etc.
- **Preconfigured packages**: `amsmath`, `booktabs`, `natbib`, `cleveref`, `hyperref`, `algorithm`, `subcaption`, etc.
- **Flexible section structure**: keep, reorder, or remove section files as your paper requires

## Conventions

- Use `\citet{}` for textual citations, `\citep{}` for parenthetical
- Use `\eqref{}` for equation references
- Use `align` or `equation` environments (never `eqnarray`)
- Use `booktabs` for tables (no vertical rules)
- American English spelling throughout

## Citation

If you use this template in your work, you can cite it via its Zenodo DOI:

> Tiamiyu, A. T. (2026). *LaTeX Manuscript Template for Computational and Applied Mathematics*. Zenodo. `DOI-HERE`

A `CITATION.cff` file is included in the repository for GitHub's "Cite this repository" widget.

### Setting up the DOI (first-time only)

1. Push this repo to GitHub and make it public.
2. Go to [zenodo.org/account/settings/github](https://zenodo.org/account/settings/github) and flip the switch on your repo.
3. Create a GitHub Release (`v1.0.0`) — Zenodo automatically archives it and mints a **concept DOI** (resolves to all versions) and a version-specific DOI.
4. Copy the concept DOI, uncomment the `identifiers` block in `CITATION.cff`, and paste the DOI.
5. Commit the updated `CITATION.cff` directly to `main` — no second release needed. The Zenodo landing page displays the DOI regardless; the next release (`v1.1.0`) will have the DOI inside its archived copy.

All future GitHub Releases are automatically archived on Zenodo with their own version DOI.
