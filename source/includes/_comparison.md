## Comparisons
Retrieves both `Readings` and the `interval`-th `Predictions` in the last `horizon` span specified.

### Usage

#### Parameters

The `Default` column specifies the value used when the user does not specify a parameter in the request.

Field | Type | Default | Limitation | Description
-----:|:----:|:---------:|:-----:|:-----------
__horizon__ | float | NA | x > 0 | A float value which represents the number of hours of `Readings` the user specifies in the request.
__interval__ | int | NA | x in (5, 10, 15) | An integer value which represents the set of `Predictions` to be retrieved, has to be either 5, 10 or 15.

* Each [Prediction](#predictions) is classed by the intervals it was made in.
* Currently only 5, 10 and 15 minute `Predictions`.
* If the `horizon` and `interval` parameters are not specified or incorrectly specified, a [URLParameterError](#client-based-errors) will be returned in the response.

#### Response

 Attribute | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/comparison`
__method(s)__ | `GET`
__status__ | "OK"
__message__ | "ML comparisons"
__status_code__ | 200

There will be an `payload` attribute populated with:

 Attribute | Value
---------:|:-----
__readings__ | A list of `Readings` with the format specified in [Readings](#readings).
__predictions__ | A list of `Predictions` with the format specified in [Predictions](#predictions).