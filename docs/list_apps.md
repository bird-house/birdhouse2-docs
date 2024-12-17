# Climate Services Application Packages

Here is a list of active software packages, applications and utilities to be used to spin off technical climate services information systems. 
Guidelines and tutorials with are realted to the workflows of WPS are documented in the [previous version of birdhouse](https://birdhouse.readthedocs.io/en/latest/)
The sources of the software packages are centralised in the GitHub Organisation [Bird-House](https://github.com/bird-house). Some applications are stored in different places due to the deveopment history, funding mechanism or intellectual property rights. 


This is the Birdhouse documentation for the new generation of birds with [pygeoapi](https://pygeoapi.io/) (ogcapi-processes).
The legacy docs for birds with [PyWPS](https://pywps.org/) (Web Processing Service) can be found on [GitHub](https://github.com/bird-house/birdhouse-docs) and on [ReadTheDocs](https://birdhouse.readthedocs.io/en/latest/).
Birds are services providing processes for specific thematic subjects. For example to access climate data or to run a cyclone tracking tool. The services are using pygeoapi from the GeoPython project. Birdhouse provides tools (cockiecutter-template, birdy client, docker, ...) to make it easier to build, use and deploy new thematic birds.


## Utilities, Clients and Frontend Components

| Name and Documentation  | Usage | Source |
| -------- | ------- | ------- |
| [Twitcher](http://twitcher.readthedocs.io/) | Security Proxy for WPS, WCS, WMS     | Deployed in [PAVICS](https://pavics-sdi.readthedocs.io/en/latest/)   | 
| [cookiecutter-birdhouse](https://cookiecutter-birdhouse.readthedocs.io) | Utility to create an OGC API Processes application package skeleton |  Version 0.5 | 
| [birdy](https://birdy.readthedocs.io)  |   Python WPS client to call a serverside deployed application package  |   Version 0.8.1  |
| [Phoenix](https://pyramid-phoenix.readthedocs.io/en/latest/)  | Graphical User Interphase Frontend   | Deployed at [CLINT Demonstrator](clint.dkrz.de)   |
| [Rooki](https://www.google.com/url?q=https://github.com/roocs/rooki&amp;sa=D&amp;source=editors&amp;ust=1660816924244993&amp;usg=AOvVaw1PeZJ1lymJDD331QwFM55x) |  PYTHON Library | | 


## PyGEO API

| Name and Documentation  | Usage | Source |
| -------- | ------- | ------- |
| [nandu](https://github.com/bird-house/nandu) | ------- | [Nandu Github repository](https://github.com/bird-house/nandu) |


## OGC API Processes

| Name and Documentation  | Usage | Source |
| -------- | ------- | ------- |
| [weaver](https://pavics-weaver.readthedocs.io/en/latest/) | Execution Management Service that allows the execution of workflows chaining various applications and Web Processing Services inputs and outputs | [Weaver GitHub Repository](https://github.com/crim-ca/weaver) |  

## Web Processing Services (WPS) including AI

| Name and Documentation  | Usage | Source |
| -------- | ------- | ------- |
| [duck](https://clint-duck.readthedocs.io/en/latest/) | AI enhanced process to Fill in missing values | [Duck GitHub Repository](https://github.com/climateintelligence/duck) | 
| [hawk](https://clint-hawk.readthedocs.io/en/latest/) | Causal analysis for climate data or, in general, for time-series | [Hawk Github Repository](https://github.com/climateintelligence/hawk)|
| [albatross](https://clint-albatross.readthedocs.io/en/latest/) | Climate resiliance application package for drought assessment | [Albatross GitHub Repository](https://github.com/climateintelligence/albatross) |
| [shearwater](https://shearwater.readthedocs.io/en/latest/)| Perform detection and forecast of tropical-cyclone activities | [Shearwater GitHub Repository](https://github.com/climateintelligence/shearwater) |
| [owl](https://clint-owl.readthedocs.io/en/latest/) | Heatwave magnitude index and warm nights| [Owl GitHub Repository](https://github.com/climateintelligence/owl) |
| [dipper](https://clint-dipper.readthedocs.io/en/latest/) | ------- | [Dipper GitHub Repository](https://github.com/climateintelligence/dipper) |

## Web Processing Services (WPS)

| Name and Documentation  | Usage | Source |
| -------- | ------- | ------- |
| [emu](https://emu.readthedocs.io/)  |    Demo and testing application for training purpose | Version 0.12 |
| [finch](https://pavics-sdi.readthedocs.io/) | application package for processing services to calculate climate indices | Deployed in    [Climatedata.ca](Climatedata.ca) and [PAVICS](https://pavics.ouranos.ca) | 
| [flyingpigon](https://flyingpigeon.readthedocs.io) | Test-suite |  Deployed in [PAVICS](https://pavics.ouranos.ca) | 
| [rooks](https://github.com/roocs) | Remote operations on climate simulations | Deployed in [COPERNICUS Climate Data Store (CDS)](https://cds.climate.copernicus.eu/#!/home) and CEDA | 
| [raven](https://pavics-sdi.readthedocs.io/projects/raven/en/latest/notebooks/index.html) | Hydrological modelling |  Deployed in [PAVICS](https://pavics.ouranos.ca) |
| [hummingbird](http://birdhouse-hummingbird.readthedocs.io/) | data compliance checker | DKRZ internal usage |
| [goldfinch](https://github.com/cedadev/goldfinch) | filtering and extraction of MIDAS data | Deployed at CEDA  |
| [pelican](https://github.com/bird-house/pelican) | WPS supporting ESGF compute API | | 
| [magpie](https://pavics-magpie.readthedocs.io/en/latest/)    |       |       |


<!-- 
| [OGC EO-Pilot](http://docs.opengeospatial.org/per/20-045.html%23_open_source_software_4&amp;sa=D&amp;source=editors&amp;ust=1660816924243900&amp;usg=AOvVaw22QBuuFacKi801Tvd-c-LC)  | | | 

 -->
