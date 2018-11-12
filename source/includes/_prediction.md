## Prediction
Retrieves the most recent set of `Predictions` along with the most recent `horizon` span of `Readings`.

### Usage

#### Parameters

The `Default Value` column specifies the value used when the user does not specify a parameter in the request.

Field | Type | Default | Limitation | Description
-----:|:----:|:---------:|:----------:|:-----------
__horizon__ | float | 2.5 | x > 0 | A float value which represents the number of hours of `Readings` the user specifies in the request.

#### Response

 Attribute | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/prediction`
__method(s)__ | `GET`
__status__ | "OK"
__message__ | "ML predictions"
__status_code__ | 200

There will be an `payload` attribute associated with a successful response with:

 Attribute | Value
---------:|:-----
__readings__ | A list of `Readings` with the format specified in [Readings](#readings).
__predictions__ | A list of `Predictions` with the format specified in [Predictions](#predictions).