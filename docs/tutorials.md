# Tutorials

## Calling a Service (birdy)

[birdy](https://github.com/bird-house/birdy.git)

## Climate Indices (finch):

**Finch** is providing services to calculate climate indices widely used in climate change adaptation planing processes. Have a look on the examples of the finch documentation: [Climate Indices](https://pavics-sdi.readthedocs.io/projects/finch/en/latest/notebooks/index.html)

## Hydrological models (raven):

WPS raven is providing hydrological models for e.g. hydro-power controlling and sustainable planing. Have a look on the examples of the raven documentation: [Hydrological Model](https://pavics-raven.readthedocs.io/en/latest/notebooks/index.html)


<!-- 
docs/source/examples.rst

tutorial_basic tutorial_pywps tutorial_birdy tutorial_wps tutorial_finch
tutorial_raven tutorial_server tutorial_r

## Get familiar with birdhouse 
general tutorials 

## Calculate climate indices
Finch 

## Extreme weather event detection
CLINT summer school
 -->

## How to contribute to this documentation

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

### Adding new pages

Please read the docs at [mkdocs](https://www.mkdocs.org/) and also at [mkdocs-material](https://squidfunk.github.io/mkdocs-material/).

There is a [user guide](https://www.mkdocs.org/user-guide/writing-your-docs/) on mkdocs describing how to add new pages with markdown.

### Convert rst to markdown

You can convert `rst` files to *markdown* using [pandoc](https://pandoc.org/).

```console
pandoc tutorial.rst -t markdown -o tutorial.md
```

Probably some edits are neccessary after the conversion.

