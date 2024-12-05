# Birdhouse Docs

This is the Birdhouse documentation for the new generation of birds with [pygeoapi](https://pygeoapi.io/) (ogcapi-processes).

The legacy docs for birds with [PyWPS](https://pywps.org/) can be found on [GitHub](https://github.com/bird-house/birdhouse-docs) and on [ReadTheDocs](https://birdhouse.readthedocs.io/en/latest/).


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
