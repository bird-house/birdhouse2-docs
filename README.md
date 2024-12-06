# Birdhouse Docs

[![Documentation Status](https://img.shields.io/badge/docs-latest-brightgreen.svg)](http://birdhouse.readthedocs.io/en/latest/?badge=latest)

[![GitHub license](https://img.shields.io/github/license/bird-house/birdhouse2-docs.svg)](https://github.com/bird-house/birdhouse2-docs/blob/main/LICENSE)

[![Join the chat at Gitter](https://badges.gitter.im/bird-house/birdhouse.svg)](https://gitter.im/bird-house/birdhouse?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This is the Birdhouse documentation for the new generation of birds with [pygeoapi](https://pygeoapi.io/) (ogcapi-processes).

The legacy docs for birds with [PyWPS](https://pywps.org/) (Web Processing Service) can be found on [GitHub](https://github.com/bird-house/birdhouse-docs) and on [ReadTheDocs](https://birdhouse.readthedocs.io/en/latest/).


## Quick Guide to build the docs

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
