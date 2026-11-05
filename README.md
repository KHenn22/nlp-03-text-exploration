# nlp-03-text-exploration

[![Python 3.14](https://img.shields.io/badge/python-3.14%2B-blue?logo=python)](pyproject.toml)
[![CI](https://github.com/KHenn22/nlp-03-text-exploration/actions/workflows/ci-python-zensical.yml/badge.svg)](https://github.com/KHenn22/nlp-03-text-exploration/actions/workflows/ci-python-zensical.yml)
[![Documentation](https://img.shields.io/badge/docs-site-blue?logo=github)](https://denisecase.github.io/nlp-03-text-exploration/)
[![uv managed](https://img.shields.io/badge/uv-managed-DE5FE9)](https://docs.astral.sh/uv/)
[![ty type checked](https://img.shields.io/badge/ty-type_checked-2F80ED)](https://docs.astral.sh/ty/)
[![MIT](https://img.shields.io/badge/license-MIT-yellow.svg)](LICENSE)

> Exploratory text analysis using a small labeled corpus to reveal frequencies, category patterns, and word context.

## Overview

This project is the third assignment in the Web Mining and Applied NLP course. It shows how to perform exploratory data analysis on a text corpus before moving into more advanced NLP techniques such as embeddings or model-based pipelines.

The main script builds a simple corpus of short texts, cleans and tokenizes the text, and then measures how words and word pairs differ across categories.

## What the project demonstrates

- A document corpus with category labels
- Tokenization and punctuation cleanup
- Global token frequency counts
- Category-by-category comparison of vocabulary
- Top tokens per category
- Bigram creation and co-occurrence analysis
- Basic plotting and logging for result inspection

## Repository layout

- [src/nlp/nlp_corpus_explore.py](src/nlp/nlp_corpus_explore.py) - main exploratory analysis script
- [src/nlp/nlp_corpus_explore_modification.py](src/nlp/nlp_corpus_explore_modification.py) - alternate version of the analysis workflow
- [notebooks/aviation_safety_analysis.ipynb](notebooks/aviation_safety_analysis.ipynb) - custom aviation safety analysis notebook
- [notebooks/nlp_corpus_explore_modification.ipynb](notebooks/nlp_corpus_explore_modification.ipynb) - notebook version of the exploratory workflow
- [tests/test_smoke.py](tests/test_smoke.py) - smoke test for the core behavior
- [docs/](docs/) - documentation and project report content
- [.github/workflows/](.github/workflows/) - CI and documentation automation
- [pyproject.toml](pyproject.toml) - project metadata and Python dependencies
- [zensical.toml](zensical.toml) - documentation site configuration

## Dataset

The analysis uses a small, controlled corpus defined directly in the Python script. It contains 22 short documents distributed across four categories:

- Dog
- Cat
- Car
- Truck

Each document includes a category label and short text that reflects the topic. No external dataset or network access is required.

## Quick start

From the project root, install dependencies and run the project:

```shell
uv sync
uv run python -m nlp.nlp_corpus_explore
```

The script prints summary tables for the token distribution, category comparisons, top tokens, and co-occurrence patterns. If you run it in a local terminal, close any matplotlib windows after viewing them so the script can continue.

## Validation

Run the automated smoke test:

```shell
uv run python -m pytest
```

## Results

The analysis produces counts such as:

- global token frequencies
- top tokens by category
- co-occurrence context data
- bigram frequencies

These outputs help reveal patterns in vocabulary and word proximity before introducing machine learning or language models.

## Documentation and automation

This repository includes a hosted documentation site and CI automation:

- [Hosted documentation](https://denisecase.github.io/nlp-03-text-exploration/)
- [CI workflow](https://github.com/KHenn22/nlp-03-text-exploration/actions/workflows/ci-python-zensical.yml)
- [Documentation deployment workflow](https://github.com/KHenn22/nlp-03-text-exploration/actions/workflows/deploy-zensical.yml)

## Development notes

These commands are useful during development:

```shell
uvx pup-clean --delete
uv self update
uv python pin 3.14
uv python install
uv lock --upgrade
uv sync
uv audit
```

Run linting, formatting, type checking, and tests:

```shell
uv run ruff check . --fix
uv run ruff format .
uv run ty check
uv run python -m pytest
```

## License

This project is released under the [MIT License](LICENSE).

## Citation

See [CITATION.cff](CITATION.cff) for citation metadata.
