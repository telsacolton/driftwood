.. role:: bash(code)
    :language: bash

=========
Driftwood
=========
**A collection of python logging extensions**

Installing
==========
:bash:`pip install git+https://github.com/HurricaneLabs/driftwood.git`

Examples
========

JSON Formatter
--------------
This code example:

.. code-block:: python

    import logging
    from driftwood.formatters.json import JSONFormatter
    log = logging.getLogger("test")
    handler = logging.StreamHandler()
    json_formatter = JSONFormatter()
    handler.setFormatter(json_formatter)
    log.addHandler(handler)
    log.warning("uh oh")

Produces:

.. code-block:: json

    {"created": 1422386241.4394472, "pathname": "<stdin>", "message": "uh oh", "threadName": "MainThread", "levelname": "WARNING", "process": 4384, "module": "<stdin>", "thread": 139785634490176, "levelno": 30, "msecs": 439.44716453552246, "filename": "<stdin>", "lineno": 1, "relativeCreated": 52455.650329589844, "funcName": "<module>", "name": "test"}
