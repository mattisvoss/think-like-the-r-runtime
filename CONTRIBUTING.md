# Contributing

Thank you for considering a contribution. This book aims to be the clearest possible first-principles explanation of how R works, for the statistical and machine learning community. Contributions that serve that aim are very welcome.

## What is especially welcome

- **Corrections.** Factual errors about R internals, mistakes in code, or claims that are misleading. Mechanism matters here, so precision matters.
- **Clearer examples.** If you can replace an example with one that is easier for a newcomer to follow without losing rigour, please do.
- **New exercises**, especially ones that make an abstraction physical by having the reader observe a mechanism directly.
- **Accessibility improvements:** clearer prose, better alt text on figures, anything that widens the audience.

## The guiding principles

1. **Explain by mechanism.** Prefer "this happens because the runtime does X with memory" over "this is just how R works". The whole point of the book is that there is no magic.
2. **Build from first principles.** Do not assume knowledge the book has not yet introduced. If you need a concept, either use one from an earlier chapter or introduce it plainly.
3. **Prefer a clear example to a clever one.** The reader's understanding is the only thing being optimised.
4. **No em-dashes.** A house-style choice; please use commas, colons, or parentheses instead.

## How to propose a change

1. Open an issue describing the problem or idea first, especially for anything larger than a typo. This avoids duplicated effort.
2. Fork the repository and make your change on a branch.
3. Render locally with `quarto render` to check that it still builds. You do not need R installed, because the code blocks are not executed during the build.
4. Open a pull request explaining what you changed and why.

## A note on the code blocks

Code blocks are written as plain ```` ```r ```` fences and are **not executed** during the build. This keeps the build fast and dependency-free, and expected output is shown inline as comments. Turning selected examples into executed, output-checked chunks is a welcome future enhancement; please open an issue to discuss the approach first, since it changes the build's requirements.

## Licensing of contributions

By contributing, you agree that your prose contributions are licensed under CC BY 4.0 and your code contributions under the MIT License, matching the rest of the book. See `LICENSE` and `LICENSE-CODE`.
