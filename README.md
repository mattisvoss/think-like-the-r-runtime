# Think Like the R Runtime

*A first-principles course in how R actually works, for the statistical and machine learning community.*

This is a free, open-source book by Mattis Voss. It explains R from the ground up: not how to call functions, but what the machine and the interpreter are doing when you do. It starts below the language, with bits, memory addresses, pointers, the stack and the heap, and the CPU loop, and builds up through environments, closures, lazy evaluation, the call stack, object systems, reactivity, and performance. It then climbs to the deepest idea in the language, code as data, ending by building a small working interpreter for R, in R, and a capstone that shows every idea together in one realistic system.

It is written for people who use R to fit models, build reproducible pipelines with [`targets`](https://docs.ropensci.org/targets/), and ship [Shiny](https://shiny.posit.co/) apps, and who would rather understand the tool than memorise incantations. Almost no prior R knowledge is assumed, and no computer architecture background is required: the first chapter builds it from nothing.

## Read it

The rendered book lives at:

```
https://mattisvoss.github.io/think-like-the-r-runtime/
```

(Replace `mattisvoss` with your own GitHub username once you publish.) A PDF download is linked in the sidebar of the site.

## Contents

- **Part I: The Machine.** Foundations (memory, pointers, the stack and heap, the CPU)
- **Part II: Names and Values.** Environments, Closures, Lazy Evaluation, The Call Stack
- **Part III: Organising Behaviour.** Object Systems (S3, S4, R6), Reactivity
- **Part IV: Making It Fast.** Performance
- **Part V: Code as Data.** Metaprogramming, The Metacircular Evaluator
- **Capstone.** One System, Every Idea

## Building locally

This is a [Quarto](https://quarto.org) book. The code blocks are illustrative and are **not** executed during the build, so you only need Quarto itself; you do **not** need R or any R packages installed.

```bash
# Install Quarto from https://quarto.org/docs/get-started/
quarto preview      # live preview in your browser
quarto render       # render to _book/ (HTML + PDF)
```

The PDF build additionally needs a LaTeX installation, which Quarto can manage:

```bash
quarto install tinytex
```

## Publishing to GitHub Pages

A GitHub Action (`.github/workflows/publish.yml`) renders the whole book and deploys it on every push to `main`. To turn it on:

1. Push this repository to GitHub on the `main` branch.
2. In **Settings → Pages**, set the source to the **`gh-pages`** branch (the first push creates it automatically).
3. Replace `mattisvoss` in `_quarto.yml` and this README with your own GitHub username.

No R installation is needed in the Action, because the code blocks are not executed.

## Getting it read

For an open book, distribution is the whole point. Some channels that reach R users directly:

- **[R-bloggers](https://www.r-bloggers.com/)** syndicates blog posts to a large R audience; submit your announcement post.
- The **#rstats** community on Bluesky, Mastodon, and LinkedIn, plus **r/rstats** and the **[Posit Community](https://forum.posit.co/)** forum.
- **[The Big Book of R](https://www.bigbookofr.com/)**, a catalogue of free R books worth being listed in.
- A **[Zenodo](https://zenodo.org/)** deposit gives the book a DOI so it can be cited and is archived permanently. The included `CITATION.cff` pairs with this.

## Repository layout

```
.
├── index.qmd                    Preface
├── 01-foundations.qmd           Part I: The Machine
├── 02-environments.qmd          Part II: Names and Values
├── 03-closures.qmd
├── 04-lazy-evaluation.qmd
├── 05-call-stack.qmd
├── 06-object-systems.qmd        Part III: Organising Behaviour
├── 07-reactivity.qmd
├── 08-performance.qmd           Part IV: Making It Fast
├── 09-metaprogramming.qmd       Part V: Code as Data
├── 10-metacircular-evaluator.qmd
├── 11-capstone.qmd              Capstone
├── _quarto.yml                  Book configuration
├── theme.scss                   HTML styling
├── tex/preamble.tex             PDF styling
├── references.bib               Further-reading references
├── CITATION.cff                 How to cite this book
├── CONTRIBUTING.md              How to contribute
├── LICENSE                      CC BY 4.0 (prose)
├── LICENSE-CODE                 MIT (code examples)
└── .github/workflows/           Auto-build and deploy
```

## License

This book is free to read, share, and build on. The prose is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/); see [`LICENSE`](LICENSE). The code examples and build configuration are licensed under the [MIT License](https://opensource.org/licenses/MIT); see [`LICENSE-CODE`](LICENSE-CODE). Please give appropriate credit when you reuse the material.

## Contributing

Corrections, clearer examples, and new exercises are welcome. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Acknowledgements

The structure of this book, its choice of topics and the order in which they build, follows Sumit Saha's course **[*Think Like the JavaScript Engine*](https://www.freecodecamp.org/news/think-like-the-javascript-engine/)** (freeCodeCamp, 2026). Part V draws its inspiration from Abelson and Sussman's **Structure and Interpretation of Computer Programs** (MIT Press), in particular the idea of understanding a language by building an evaluator for it. All text and code in this book are original and written for R; only the pedagogical ideas are shared, with thanks.

This is a personal project. The views in it are the author's own and do not represent any employer.
