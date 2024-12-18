# Instructions

> **Code of Conduct:** Before we start please be aware that contributors to this project are expected to act respectfully toward others in accordance with the [OSGeo Code of Conduct](https://www.osgeo.org/code_of_conduct/)


## Set up a birdhouse application based on PyGeoAPI 

> To be developed

## Set up a birdhouse application based on WPS 

If you are familiar with all the upper chapters you are ready to create
your own WPS. The WPS in birdhouse are named after birds, so this
section is giving you a guidline of how to make your own bird. Birds are
sorted thematically, so before setting up a new one, make sure it is not
already covered and just missing some processes and be clear in the new
thematic you would like to provide.

There is a [Cookiecutter]() template to create a new bird (PyWPS
application). It is the recommended and fastest way to create your own
bird:

::: gittoctree
<https://github.com/bird-house/cookiecutter-birdhouse.git>

docs/source/dev[guide.rst]{#guide.rst}
:::

::: gitinclude
<https://github.com/bird-house/cookiecutter-birdhouse/blob/master/%7B%7Bcookiecutter.project_repo_name%7D%7D/docs/source/dev_guide.rst>
:::

### Writing a WPS process

In birdhouse, we are using the [PyWPS]() implementation of a
`Web Processing Service`{.interpreted-text role="term"}. Please read the
[PyWPS
documentation](https://pywps.readthedocs.io/en/master/process.html) on
how to implement a WPS process.

:::: note
::: title
Note
:::

To get started quickly, you can try the [Emu]() WPS with some example
processes for PyWPS.
::::

![image](images/process_schema_1.png)

Another point to think about when designing a process is the possibility
of chaining processes together. The result of a process can be a final
result or be used as an input for another process. Chaining processes is
a common practice but depends on the user you are designing the service
for. Technically, for the development of WPS process chaining, here are
a few summary points:

-   the functional code should be modular and provide an
    interface/method for each single task
-   provide a wps process for each task
-   wps processes can be chained, manually or within the code, to run a
    complete workflow
-   wps chaining can be done manually, with workflow tools, direct wps
    chaining or with code scripts
-   a complete workflow chain could also be started by a wps process.

![image](images/wps_chain.png)

### Writing functions

A Process is calling several functions during the performance. Since WPS
is a autonom running process several eventualities needs to be taken
into account. If irregularities are occurring, it is a question of the
process design if the performance should stop and return an error or
continue with may be an modified result.

In practice, the functions should be encapsulated in **try** and
**except** calls and appropriate information given to the logfile or
shown as a status message. The logger has several options to to
influence the running code and the information writing to the logfile:

![image](_images/module_chain.png)

``` {.python linenos=""}
# the following two line needs to be in the beginning of the *.py file.
# The ._handler will find the appropriate logfile and include timestemps
# and module information into the log.

import logging
LOGGER = logging.getLogger("PYWPS")

# set a status message
per = 5  # 5 will be 5% in the status line
response.update_status('execution started at : {}'.fromat(dt.now()), per)

try:
    response.update_status('the process is doing something: {}'.fromat(dt.now()),10)
    result = 42
    LOGGER.info('found the answer of life')
except Exception as ex:
    msg = 'This failed but is obligatory for the output. The process stops now, because: {} '.format(ex)
    LOGGER.error(msg)

try:
    response.update_status('the process is doing something else : {}'.fromat(dt.now()), 20)
    interesting = True
    LOGGER.info(' Thanks for reading the guidelines ')
    LOGGER.debug(' I need to know some details of the process: {} '.format(interesting)
except Exception as ex:
    msg = 'This failed but is not obligatory for the output. The process will continue. Reason for the failure: {} '.format(ex)
    LOGGER.exception(msg)
```

### Writing tests

Writing tests is an essential part of software development. The WPS templates produced by Cookiecutter_ include the initial folders needed for units tests and basic dependencies in the environment.
There are two parts of tests:

* Unit tests:
python pytest to check the functionality of functions and processes. They are stored in the folder `{bird WPS}/tests` and appropriate test data  `{bird WPS}/tests/testdata`.

* notebook tests:
Code examples of the documentation to demonstrate the usage of WPS services. The examples are written in jupyter notebooks and stored in the documentation folder `{bird WPS}/docs/source/notebooks/`
```