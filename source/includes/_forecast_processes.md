## Forecast Processes
Retrieves information for forecasted processes. This provides the user with information on what processes are available, as well as if features such as [Subsystem Breakdown](#subsystem-breakdown) are available for subprocesses.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/forecast_processes`
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
    "message": "Forecast Types and Processes",
    "status_code": 200,
    "payload": [
        {
            "id": "steam",
            "name": "Steam Forecast",
            "processes": [{
                "id": "sub_process_1",
                "name": "Sub-process 1",
                "subsystem_breakdown": True
            }, {
                "id": "sub_process_2",
                "name": "Sub-process 2",
                "subsystem_breakdown": False
            }]
        }, {
            "id": "electricity",
            "name": "Electricity Forecast",
            "processes": [{
                "id": "sub_proccess_3",
                "name": "Sub-Processes",
                "subsystem_breakdown": False
            }]
        }
    ]
}
```

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "Forecast Types and Processes"
__status_code__ | int | 200

The `payload` attribute associated with a successful response will be available as an array of objects, each object will
represent the available forecasts and related info for a specific `process`.

 Attribute | Type | Value
---------:|:----:|:-----
__id__ | string | The `id` of the aggregated process.
__name__ | string | The process name for the aggregated process.
__processes__ | Object array | The `processes` attribute contains an array of objects described in the table below. Each object represents information regarding each seperate process within the aggregated process,

This table describes the attributes available for each `process` in the `processes` attribute:

 Attribute | Type | Value
---------:|:----:|:-----
__id__ | string | The `id` of the individual process.
__name__ | string | The process name for the individual process.
__subsystem_breakdown__ | boolean | This specifies if the process has its own subsystem breakdown.