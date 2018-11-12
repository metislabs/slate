## Forecast Processes
Retrieves information for forecasted processes. This provides the user with information on what processes are available, as well as if features such as Subsytem Breakdown are available.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/forecast_processes`
__method(s)__ | `GET`

### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "Forecast Types and Processes"
__status_code__ | int | 200

The `payload` attribute associated with a successful response will be available as an array of `JSONs`, each `JSON` will
represent the available forecasts and related info for a specific `process`.

 Attribute | Type | Value
---------:|:----:|:-----
__id__ | string | The `id` of the aggregated process.
__name__ | string | The process name for the aggregated process.
__processes__ | JSON Array | The `processes` attribute contains an array of `JSONs` described in the table below. Each `JSON` represents information regarding each seperate process within the aggregated process,

This table describes the attributes available for each `process` in the `processes` attribute:

 Attribute | Type | Value
---------:|:----:|:-----
__id__ | string | The `id` of the individual process.
__name__ | string | The process name for the individual process.
__subsystem_breakdown__ | boolean | This value indicates if the individual process is included in the [Subsystem breakdown](#subsystem-breakdown).

* If [ForecastNotFound](#client-based-errors) will be returned in the response, please contact customer support.
