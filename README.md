OASpy Server
============

HTTP API server for APIs based on OpenAPI specification.

[![Documentation Status](https://readthedocs.org/projects/oaspy-server/badge/?version=latest)](https://oaspy-server.readthedocs.io)
[![CI builds](https://b11c.semaphoreci.com/badges/oaspy-server.svg?style=shields)](https://b11c.semaphoreci.com/projects/oaspy-server)

**OASpy Server** is a [Starlette](https://www.starlette.io)-based framework for serving HTTP services based on the [OpenAPI Specification](https://swagger.io/resources/open-api/) standard.


Quick Start
-----------

### Endpoint Functions in Module

```python
from oaspy.server import Application
from some.path import endpoints

app = Application.from_file("path/to/openapi.yaml", module=endpoints)
```


### Decorated Endpoint Functions

```python
from oaspy.server import Application

app = Application.from_file("path/to/openapi.yaml")

@app.endpoint
def some_endpoint(request):
    ...
    
@app.endpoint(operation_id="someOtherOperationId"):
def another_endpoint(request):
    ...
```
