# Tutorials

Here you can find a collection of tutorials, provided by the several contributing initiatives.

## Getting started: Calling a Service with python 

To call a service within a python code, [birdy](https://github.com/bird-house/birdy.git) is provided as a client to do this job. 

``` python 
from birdy import WPSClient
emu = WPSClient(url="http://localhost:5000/wps")
emu_i = WPSClient(url="http://localhost:5000/wps", progress=True)
emu.hello(name="Birdy").get()[0]
# Run a long running process
result = emu_i.sleep(delay="1.0")
result.get()[0]
```
> Further tutorials on how to run the birdy client can be found at [birdy documentation] (https://birdy.readthedocs.io/en/latest/examples.html)

## Calculating Climate Indices
**Finch** is providing services to calculate climate indices widely used in climate change adaptation planing processes. Have a look on the examples of the [finch documentation](https://pavics-sdi.readthedocs.io/projects/finch/en/latest/notebooks/index.html), where executable *jupyter notebooks* are provided on how to calculate climate indices. 

## Running hydrological models
**raven** is providing hydrological models for e.g. hydro-power controlling and sustainable planing. Have a look on the examples of the raven documentation: [Hydrological Model](https://pavics-raven.readthedocs.io/en/latest/notebooks/index.html)

## Artificial Intelligence enhanced climate servies
Extreme event detection and prediction for cyclon activity, droughts, heatwaves or floods, using artificial intelligence methodes has been developed in the CLINT Project. Juypter Notebooks on how to handle and run this proceses are proviced in the [Climate Intelligence CLINT Project](https://github.com/climateintelligence/CLINT-tutorials) 

<!-- 
docs/source/examples.rst
tutorial_basic tutorial_pywps tutorial_wps tutorial_server tutorial_r


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

