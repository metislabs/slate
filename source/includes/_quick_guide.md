## Quick Guide

### Response Format

* All of the responses returned from the Metislabs API follow a standardized format.

Field | Type | Description
------:|:------:|:------------
__status__ | string | A brief description of the status of the response.
__status_code__ | int | The HTTP status code of the response. Please see [Errors](#errors) for more details.
__message__ | string | A more verbose, human readable version of the response status.
__payload__ | JSON |  Contains either the requested data from the in a JSON format or `null` if data is not found or available.

### Readings

* Most of the data that the Metislabs API exposes can be thought of as `Readings`. 
* Each `Reading` represents the recorded value(__value__) of an identified process(__fqn__) at a specific time(__timestamp__).

Field | Type | Description
------:|:------:|:------------
__fqn__ | string | The fully qualified name of the process.
__timestamp__ | int | An UNIX-timestamp representation of when the Reading was recorded.
__value__ | float | The recorded result of the measurement.

### Predictions

* The core of the Metislabs API provides different forms of `Predictions` for the user.
* `Predictions` are projected future `Readings` made from previously recorded `Readings`.
* In most cases, for each `Reading`, there are a set of `Predictions` associated with it.
* The set of represents the `Predictions` at different time intervals for each reading, for example, one `Reading` may have a
5 minute, 10 minute and a 15 minute `Prediction`.
* `Predictions` are represented exactly like `Readings`.

Field | Type | Description
------:|:------:|:------------
__fqn__ | string | The fully qualified name of the process.
__timestamp__ | int | An UNIX-timestamp representation of when the Prediction is expected to occur.
__value__ | float | The predicted result of the measurement.