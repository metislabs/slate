## Prediction
Retrieves the most recent set of `Predictions` along with the most recent `horizon` span of `Readings`.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/prediction`
__method(s)__ | `GET`

#### Parameters

The `Default` column specifies the value used when the user does not specify a parameter in the request.

Field | Type | Default | Limitation | Description
-----:|:----:|:---------:|:----------:|:-----------
__horizon__ | float | 2.5 | x > 0 | A float value which represents the number of hours of `Readings` the user specifies in the request.

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "ML predictions"
__status_code__ | int | 200

There will be an `payload` attribute associated with a successful response with:

 Attribute | Type | Value
---------:|:----:|:-----
__fqn__ | string | The FQN that the predictions and readings are associated with.
__name__ | string | The process name for the FQN.
__color__ | JSON | The color codes for frontends to render the colour of the graphs. (This is can be ignored)
__readings__ | JSON Array | A list of `Readings` with the format specified in [Readings](#readings).
__predictions__ | JSON Array | A list of `Predictions` with the format specified in [Predictions](#predictions).