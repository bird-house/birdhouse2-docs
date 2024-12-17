# Birdhouse Documentation

| ![](images/birdhouse-ecosphere.svg) |
| :--: |
| **Build your own Climate Services Information System for geospatial data analysis.** |

[![Documentation Status](https://img.shields.io/badge/docs-latest-brightgreen.svg)](http://birdhouse.readthedocs.io/en/latest/?badge=latest)
[![GitHub license](https://img.shields.io/github/license/bird-house/birdhouse2-docs.svg)](https://github.com/bird-house/birdhouse2-docs/blob/main/LICENSE)
[![Join the chat at Gitter](https://badges.gitter.im/bird-house/birdhouse.svg)](https://gitter.im/bird-house/birdhouse?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


# Climate Services Information Systems

The following sections are instructions, guidelines and backgrounds around **Climate Services Information Systems (CSIS)**.

## FAIR Climate Services

Climate datasets rapidly grow in volume and complexity and creating climate products requires high bandwidth, massive storage and large compute resources. For some regions, low bandwidth constitutes a real obstacle to developing climate services. Data volume also hinders reproducibility because very few institutions have the means to archive original data sets over the long term. Moreover, typical climate products often aggregate multiple sources of information, yet mechanisms to systematically track and document the provenance of all these data are only emerging. So although there is a general consensus that climate information should follow the **FAIR Principles** {cite:p}`Wilkinson2016,mons2017`, that is be **findable, accessible, interoperable, and reusable**, a number of obstacles hinder progress. The following principles can help set up efficient climate services information systems, and show how the four FAIR Principles not only apply to data, but also to analytical processes.

### Findable
Findable is the basic requirement for data and product usage and already an difficult obstacle with time intensive work for the data provider ensuring find-able data. On the production level finding algorithms requires open source software with intensive documentation.

**Finding data:**
Finding data requires a structured data repository and if possible an assigning of a globally unique and eternally persistent identifier (like a DOI or Handle), describing the data with rich metadata, and making sure it is find-able through discovery portals of search clients. It is recommended to establish data repository collecting and managing core input and output data enabling coordinated provisioning and sharing of data focusing on sustainable storage and management of core data collections. Depending on data importance a certified long-term archive can be managed. The identification of core data collections to be managed in centralized repositories might be realized with e.g the Research Data Management Organiser (RDMO) tool. https://rdmorganiser.github.io/

**Finding algorithms:**
In free and open source for geospatial (FOSS4G) developments workflows, independent developer groups are collaborating in a win-win situation and ensuring a high-quality software product {cite:p}`Bahamdain2015`. Public repositories enabling a work efficient participating and knowledge sharing approach {cite:p}`Bejoy2010`. A high certainty and quality of scientific evidence is needed for information in a juridical context to regulate the conflict between economic development and environmental protection {cite:p}`Brown2019`. Therefor backend solutions to provide climate information for decision makers, need to be as much as possible 'error free'. The challenge of high-quality software solutions is illustrated with Linus's law that "given enough eyeballs, all bugs are shallow". {cite:p}`Raymond2001`.

### Accessible
**Access to data:**
For data users, the prevailing *modus operandi* has traditionally been to download raw data locally to conduct analyses. As data volume grows, bandwidth and local storage capacity limits the type of science that individual scientists can perform.

**Access to algorithms:**
A high certainty and quality of scientific evidence is needed for information in a juridical context to regulate the conflict between economic development and environmental protection {cite:p}`Brown2019`. Therefor backend solutions to provide climate information for decision makers, need to be as much as possible *error free*. The challenge of high-quality software solutions is illustrated with Linus's law that "given enough eyeballs, all bugs are shallow". {cite:p}`Raymond2001`. In free and open source for geospatial (FOSS4G) developments workflows, independent developer groups are collaborating in a win-win situation and ensuring a high-quality software product {cite:p}`Bahamdain2015`. Public repositories enabling a work efficient participating and knowledge sharing approach {cite:p}`Bejoy2010`.

### Interoperable
Following the UNGGIM recommendations (2020) about 'Implementation and adoption of standards for the global geospatial information community' climate data should be organized following this [UNGIM recommendations](http://ggim.un.org/meetings/GGIM-committee/10th-Session/documents/E-C.20-2020-33-Add_1-Implementation-and-Adoption-of-Standards-21Jul2020.pdf).
Interoperabillity needs to be respected on two levels:

**Interoperable data :**
following the conventions regarding metadata.

**Interoperable structures:**
The OGC standardisation also enables communication between climate services information systems services.

### Reusable

Reusabillity is a major aspect to avoid duplication of work and to foster the dynamique of providing high quality products.

**Reusable data:**
The data should maintain its initial richness. The description of essential, recommended, and optional metadata elements should be machine processable and verifiable, use should be easy and data should be citable to sustain data sharing and recognize the value of data. Result output data from one service can be post-processed by another service where other component are provided.

**Reusable algorithms:**
Contrary to running analysis code on a local machine, it is recommended to use remote services have no direct control on the software they are running. The server's maintainer essentially decides when software and services are upgraded, meaning that within the time a scientist performs initial exploration and produces the final version of a figure for a paper, remote-services might have slightly changed or have been retired.

**Reproducabillity:**
This implies that reproducabillity results might not be easily reproducible if earlier versions of services are not available anymore. This puts an additional burden on scientists to carefully monitor the version of all the remote services used in the analysis to be able to explain discrepancies between results. Similar issues occur with data versions. If a scientist used version 1 for an analysis, there is no guarantee the source data will be archived over the long term if it has been superseded by version 2. In practice, climate services use ensembles of simulations, meaning that typical climate products aggregate hundreds or thousands of files, whose versions should ideally be tracked up until the final graphic or table. This capability to uniquely identify simulation files, errata and updates is available in CMIP6 {cite:p}`Stockhause2017,Weigel2013`, but it is the responsibility of climate service providers to embed this information into the products they develop.


<!-- In the following sections we are using the [Duck](https://github.com/climateintelligence/duck) software as example to guide you through the different stepps necessay to set up an application package to be deployed in an CRIS and used for **Climate Services**.

Here we understand **Application Packages for CRIS** as standalone software in line to the [OGC API standards](https://developer.ogc.org). Several of this climate application packages can be found in the [Birdhouse](http://bird-house.github.io/) organisation which is a collection on OGC Standards based software. These software blocks can be used to build customised Climate Resilience Information System. The building blocks for climate services can be named with birdnames.

The demo web-application has been created by Carsten Ehbrecht and Étienne Plésiat in the framework of the work package 8 of the [CLINT](https://climateintelligence.eu/) H2020 project. Duck provides an AI-enhanced service to infill missing values in climate datasets. -->
