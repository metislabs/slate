## Comparison
Retrieves both `Readings` and the `interval`-th `Predictions` in the last `horizon` span specified.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/comparison`
__method(s)__ | `GET`

#### Parameters

The `Default` column specifies the value used when the user does not specify a parameter in the request.

Field | Type | Default | Limitation | Description
-----:|:----:|:---------:|:-----:|:-----------
__horizon__ | float | NA | x > 0 | A float value which represents the number of hours of `Readings` the user specifies in the request.
__interval__ | int | NA | x in (5, 10, 15) | An integer value which represents the set of `Predictions` to be retrieved, has to be either 5, 10 or 15.

* Each [Prediction](#predictions) is classed by the intervals it was made in.
* Currently only 5, 10 and 15 minute `Predictions` are available upon request.
* If the `horizon` and `interval` parameters are not specified or incorrectly specified, a [URLParameterError](#client-based-errors) will be returned in the response.

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "ML comparisons"
__status_code__ | int | 200

There will be an `payload` attribute populated with:

 Attribute | Type | Value
---------:|:----:|:-----
__fqn__ | string | The FQN that the predictions and readings are associated with.
__name__ | string | THe process name of the FQN.
__color__ | JSON | The color codes for frontends to render the colour of the graphs. (This is can be ignored)
__readings__ | JSON Arrary | An array of `Readings` with the format specified in [Readings](#readings).
__predictions__ | JSON Arrary | An array of `Predictions` with the format specified in [Predictions](#predictions).