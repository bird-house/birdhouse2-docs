# Deployment of Services

> Extended explanation of deployment options including entire scripts are available in the [birdhouse-deploy repository](https://birdhouse-deploy.readthedocs.io/en/latest/) 

## Example: Duck Demo App

Duck is a demo web-application for the *CLINT* project.

Smartduck is a demo web-application of AI-enhanced Climate Science.
It is based on the [Phoenix](https://pyramid-phoenix.readthedocs.io/en/latest/) web-application from the [Birdhouse](http://bird-house.github.io/) collection and makes use of the [PyWPS](https://pywps.org/) Python package, which is an implementation of the [Web Processing Service](https://www.ogc.org/standards/wps) standard from the [Open Geospatial Consortium](https://www.ogc.org/).

Smartduck uses [CRAI](https://github.com/FREVA-CLINT/climatereconstructionAI/tree/clint), a state-of-the-art deep learning based inpainting technology to infill missing values in climate datasets[^1].

The current demo gives the possibility to infill near-surface air temperature anomalies in the [HadCRUT4](https://www.metoffice.gov.uk/hadobs/hadcrut4/) and [HadCRUT5](https://www.metoffice.gov.uk/hadobs/hadcrut5/) datasets. The input and output netCDF files are handled through an intuitive user interface.

[^1]: [Kadow, C. *et al.*, *Nature Geoscience* 13, 408–413 (2020)](http://dx.doi.org/10.1038/s41561-020-0582-5)


The current demo gives the possibility to infill near-surface air temperature anomalies in the [HadCRUT4](https://www.metoffice.gov.uk/hadobs/hadcrut4/) and [HadCRUT5](https://www.metoffice.gov.uk/hadobs/hadcrut5/) datasets.

## Install duck with conda

We need `mamba` to install the requirements.
Use your existing `mamba` or install it from here:
https://github.com/conda-forge/miniforge

Get the source:
```
git clone https://github.com/climateintelligence/duck.git
cd duck
```

Create the conda environment for duck:
```
mamba env create
```

Activate the duck environment:
```
conda activate duck
```

Install duck in this environment:
```
pip install -e .
```

Start your duck as a web service:
```
duck start -d
```

See it is responding by sending a WPS `GetCapabilities` request:

http://localhost:5000?service=WPS&request=GetCapabilities

You can stop the service with:
```
duck stop
```


## Set up a birdhouse ecosystem server {#birdhouse_ecosystem}

If you are already familiar with installing single standalone WPS
(follow the `installation`{.interpreted-text role="ref"} guides in the
documentations of e.g. emu), then you are ready to set up a birdhouse
containing flyingpigeon (providing scientific analyses methods),
malleefowl (to search and fetch data) and the pheonix (a graphic
interface for a web browser including a WMS).

### General Remarks

| Check the `requirements`{.interpreted-text role="ref"} of your system!
| The installation is done as **normal user**, root rights are causing
  conflicts.

### Prepare Installation

It is recommended to collect the repositories in a separate folder (e.g.
birdhouse, but can have a name of your choice):

    $ mkdir birdhouse
    $ cd birdhouse

### Get the source code from GitHub

``` ini
$ git clone https://github.com/bird-house/flyingpigeon.git
$ git clone https://github.com/bird-house/pyramid-phoenix.git
$ git clone https://github.com/bird-house/malleefowl.git
```

### Run Installation

You can run the installation with default settings. It will create a
conda environment and deploy all required software dependencies there.

:::: note
::: title
Note
:::

Read the *changing the default configuration* if you want to customize
the configuration.
::::

In **all** of the tree folders (malleefowl, flyingpigeon and
pyramid-phoenix) run:

    $ make install

This installation will take some minutes to fetch all dependencies and
install them into separate conda environments.


### Start the Services

in **all** of the birds run:

    $ make start

### Launching the Phoenix Web App

If the services are running, you can launch the GUI in a common web
browser. By default, phoenix is set to port 8081:

    firefox http://localhost:8081

or:

    firefox https://localhost:8443/

Now you can log in (upper right corner) with your Phoenix password
created previously. Phoenix is just a graphical interface with no more
function than looking nice ;-).

### Register a service in Phoenix Web App

:::: note
::: title
Note
:::

Please read the [Phoenix
documentation](https://pyramid-phoenix.readthedocs.io/en/latest/user_guide.html#)
::::

Your first administration step is to register *flyingpigeon* as a
service. For that, log in with your phoenix password. In the upper right
corner is a tool symbol to open the [settings]{.title-ref}. Click on
[Services]{.title-ref} and the [Register a Service]{.title-ref}.

Flyingpigeon is per default on port 8093.

The appropriate url is:

    http://localhost:8093/wps

Provide service title and name as you like: \* Service Title:
Flyingpigeon \* Service Name: flyingpigeon

check \`Service Type\`: [Web Processing Service]{.title-ref} (default)
and register.

Optionally, you can check [Public access?]{.title-ref}, to allow
unregistered users to launch jobs. (**NOT recommended**)

### Launching a Job

Now your birdhouse ecosysem is set up. The also installed malleefowl is
already running in the background and will do a lot of work silently.
There is **no need to register malleefowl** manually!

Launching a job can be performed as a process (Process menu) or with the
wizard. To get familliar with the processes provided by each of the
birds, read the approriate documentation for each of the services listed
in the [overview:](http://birdhouse.readthedocs.io/en/latest/index.html)

### Changing the default configuration

You can customize the configuration of the service. Please read the
documentation, for example:

-   [Phoenix
    documentation](https://pyramid-phoenix.readthedocs.io/en/latest/configuration.html)
-   [Flyingpigeon
    documentation](https://flyingpigeon.readthedocs.io/en/latest/configuration.html)

Furthermore, you might change the hostname (to make your service
accessible from outside), ESGF-node connection, the port or the
log-level for more/less information in the administrator logfiles. Here
is an example \`pyramid-phoenix/custom.cfg\`:

``` ini
[settings]
hostname = localhost
http-port = 8081
https-port = 8443
log-level = DEBUG
# run 'make passwd' and to generate password hash
phoenix-password = sha256:513....
# generate secret
# python -c "import os; print(''.join('%02x' % ord(x) for x in os.urandom(16)))"
phoenix-secret = d5e8417....30
esgf-search-url = https://esgf-data.dkrz.de/esg-search
wps-url = http://localhost:8091/wps
```

### Update Phoenix Password

To be able to log into the Phoenix GUI once the services are running, it
is necessary to generate a password: go into the pyramid-phoenix folder
and run:

    $ make passwd

This will automatically write a password hash into
pyramid-phoenix/custom.cfg

## Backups

See the [mongodb
documentation](https://docs.mongodb.com/manual/core/backups/) on how to
backup the database. With the following command you can make a dump of
the `users` collection of the Phoenix database:

    $ mongodump --port 27027 --db phoenix_db --collection users
