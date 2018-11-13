## Quick Guide

### Management

* Each `token` in the Metislabs API will belong to an `organisation`.
* Each `organisation` can have one or more `sites` associated with the `organisation`, in most cases, `sites` can be thought of individual factories.
* Each `site` contains multiple `processes` which may have `forecasts` associated with them.
* Trying to access `organisation`, `site`, `proccess` and `forecast` which are not authorised to the `token` will result in a
[PermissionDenied](#client-based-exceptions) exception.

### Response Format

* All of the responses returned from the Metislabs API follow a standardized format.

Field | Type | Description
------:|:------:|:------------
__status__ | string | A brief description of the status of the response.
__status_code__ | int | The HTTP status code of the response. Please see [Exceptions](#exceptions) for more details.
__message__ | string | A more verbose, human readable version of the response status.
__payload__ | Object |  Contains either the requested data in a JSON format or `null` if data is not found or available.

### Readings

* Most of the data that the Metislabs API exposes can be thought of as `Readings`. 
* Each `Reading` represents the recorded value(__value__) of an identified sensor(__fqn__) at a specific time(__timestamp__).

Field | Type | Description
------:|:------:|:------------
__fqn__ | string | The fully qualified name of the process.
__timestamp__ | int | An UNIX-timestamp representation of when the Reading was recorded.
__value__ | float | The recorded result of the measurement.

### Predictions 

* The core of the Metislabs API provides different forms of `Predictions` for the user.
* `Predictions` are projected future `Readings` made from previously recorded `Readings`.
* In most cases, for each `Reading`, there are a set of `Predictions` associated with it.
* Each `Prediction` belongs to an `interval` set as there are 5, 10 and 15 minute `Predictions` made from a `Reading`.
* `Predictions` are represented exactly like `Readings`.

Field | Type | Description
------:|:------:|:------------
__fqn__ | string | The fully qualified name of the process.
__timestamp__ | int | An UNIX-timestamp representation of when the Prediction is expected to occur.
__value__ | float | The predicted result of the measurement.
