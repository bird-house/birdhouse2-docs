# Birdhouse Docs

[![Documentation Status](https://img.shields.io/badge/docs-latest-brightgreen.svg)](http://birdhouse.readthedocs.io/en/latest/?badge=latest)
[![GitHub license](https://img.shields.io/github/license/bird-house/birdhouse2-docs.svg)](https://github.com/bird-house/birdhouse2-docs/blob/main/LICENSE)
[![Join the chat at Gitter](https://badges.gitter.im/bird-house/birdhouse.svg)](https://gitter.im/bird-house/birdhouse?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This is the Birdhouse documentation for the new generation of birds with [pygeoapi](https://pygeoapi.io/) (ogcapi-processes).

The legacy docs for birds with [PyWPS](https://pywps.org/) (Web Processing Service) can be found on [GitHub](https://github.com/bird-house/birdhouse-docs) and on [ReadTheDocs](https://birdhouse.readthedocs.io/en/latest/).

Birds are services providing processes for specific thematic subjects. For example to access climate data or to run a cyclone tracking tool. The services are using pygeoapi from the GeoPython project.

Birdhouse provides tools (cockiecutter-template, birdy client, docker, ...) to make it easier to build, use and deploy new thematic birds.

## Build the docs

Clone the docs repo from GitHub:
```console
git clone https://github.com/bird-house/birdhouse2-docs.git

cd birdhouse2-docs
```

Create conda environment:
```console
conda env create
conda activate birdhouse2-docs
```

Build the docs:
```console
mkdocs build

# html output is in folder site/
```

Or serve the docs for your browser:
```console
mkdocs serve
```

## Adding new pages

Please read the docs at [mkdocs](https://www.mkdocs.org/) and also at [mkdocs-material](https://squidfunk.github.io/mkdocs-material/).

There is a [user guide](https://www.mkdocs.org/user-guide/writing-your-docs/) on mkdocs describing how to add new pages with markdown.

## Convert rst to markdown

You can convert `rst` files to *markdown* using [pandoc](https://pandoc.org/).

```console
pandoc tutorial.rst -t markdown -o tutorial.md
```

Probably some edits are neccessary after the conversion.


