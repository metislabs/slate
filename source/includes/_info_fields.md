## Info Fields

Retrieves additional information and statistics for related metrics.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/info_fields`
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
    "message": "Information Measurements & Statistics",
    "status_code": 200,
    "payload": [
        {
            "alert_level": 2,
            "color": "purple",
            "icon": "timelapse",
            "id": "until_next_stage",
            "label": "Until next stage",
            "position": 0,
            "prefix": None,
            "suffix": "minutes",
            "type": "operator",
            "value": 15
        },
        {
            "alert_level": 0,
            "color": "green",
            "icon": "trending_up",
            "id": "additional_demand",
            "label": "Additional demand",
            "position": 1,
            "prefix": None,
            "suffix": "tonnes",
            "type": "operator",
            "value": 3.24
        },
        {
            "alert_level": 0,
            "color": "blue",
            "icon": "filter_drama",
            "id": "current_steam_flow",
            "label": "Current steam flow",
            "position": 2,
            "prefix": None,
            "suffix": "tonnes",
            "type": "operator",
            "value": 3.66
        },
        {
            "alert_level": 0,
            "color": "green",
            "icon": "show_chart",
            "id": "stage_prediction_accuracy",
            "label": "Prediction accuracy",
            "position": 2,
            "prefix": None,
            "suffix": "accurate",
            "type": "supervisor",
            "value": "87%"
        }
    ]
}
```

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "Information Measurements & Statistics"
__status_code__ | int | 200

The `payload` attribute associated with a successful response will be available as an array of objects, each object will
represent the available metric.

 Attribute | Type | Value
---------:|:----:|:-----
__alert_level__ | int | The alert level of the metric, can be ignored.
__color__ | string | The color for the metric, can be ignored.
__icon__ | string | The icon for the metric, can be ignored.
__id__ | string | The id representation of the metric.
__label__ | string | The name of the metric.
__position__ | int | The positional placement of the metric to be rendered by the frontend interface, can be ignored.
__prefix__ | string or null | The unit prefix of the metric value, can be `null`.
__suffix__ | string or null | The unit suffix of the metric value, can be `null`.
__type__ | string | The authorization level for the metric, either `supervisor` or `operator`.
__value__ | string or float | A numerical or string value of the metric.
