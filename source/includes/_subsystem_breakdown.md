## Subsystem Breakdown
Retrieves a breakdown of aggregated `Readings`. This applies to all appropriate `FQNs` that are influential in the overall process.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/subsystem_breakdown`
__method(s)__ | `GET`


#### Parameters

The `Default` column specifies the value used when the user does not specify a parameter in the request.

Field | Type | Default | Limitation | Description
-----:|:----:|:---------:|:----------:|:-----------
__site__ | string | NA | NA | The site that the user wants to retrieve data from.
__process__ | string | None  | NA | The process that the user wants to retrieve data from.
__forecast__ | stirng | None | NA | The forecast that the user wants to retrieve data from.

```json
{
    "status": "OK",
    "message": "Subsystem Breakdown",
    "status_code": 200,
    "payload": [
        {
            "fqn": "fqn1",
            "name": "FQN 1",
            "color": {
                "readings": "red",
                "predictions": "blue"
            },
            "readings": [
                {"value": 55.2, "timestamp": 0},
                {"value": 32.16, "timestamp": 1},
                {"value": 6.53, "timestamp": 2},
            ]
        },
        {
            "fqn": "fqn2",
            "name": "FQN 2",
            "color": {
                "readings": "red",
                "predictions": "blue"
            },
            "readings": [
                {"value": 324.0, "timestamp": 0},
                {"value": 1.44, "timestamp": 1},
                {"value": 56.11, "timestamp": 2},
            ]
        },
    ]
}
```

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "Subsystem Breakdown"
__status_code__ | int | 200

The `payload` attribute associated with a successful response will be available as a list of objects, each object will
represent the system breakdown for a specific `FQN`. Here each object is described in more detail:

 Attribute | Type | Value
---------:|:----:|:-----
__fqn__ | string | The FQN that the readings are associated with.
__name__ | string | The process name for the FQN.
__color__ | Object array | The color codes for frontends to render the colour of the graphs. (This is can be ignored)
__readings__ | Object array | A list of `Readings` with the format specified in [Readings](#readings).
__predictions__ | Object array | A list of `Predictions` with the format specified in [Predictions](#predictions).
