## Subsystem Breakdown
Retrieves a breakdown of aggregated `Readings`. This applies to all appropriate `FQNs` that are influential in the overall process.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/subsystem_breakdown`
__method(s)__ | `GET`

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

### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "Subsystem Breakdown"
__status_code__ | int | 200

The `payload` attribute associated with a successful response will be available as a list of `JSONs`, each `JSON` will
represent the system breakdown for a specific `FQN`. Here each `JSON` is described in more detail:

 Attribute | Type | Value
---------:|:----:|:-----
__fqn__ | string | The FQN that the readings are associated with.
__name__ | string | The process name for the FQN.
__color__ | JSON Array | The color codes for frontends to render the colour of the graphs. (This is can be ignored)
__readings__ | JSON Array | A list of `Readings` with the format specified in [Readings](#readings).

* If [SubsystemBreakdownNotFound](#client-based-errors) will be returned in the response, please contact customer support.