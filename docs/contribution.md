# Contribution

## Get in contact

In case of questions or trouble shooting, feel welcome to join the
[birdhouse chat](https://gitter.im/bird-house/birdhouse) and get into
contact with the developers directly.

## Contribute to Documentation

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

