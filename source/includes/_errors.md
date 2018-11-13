## Errors
Retrieves information for errors and discrepancy in the Metislabs API. This should provide the user with information on why certain `Readings` or `Predictions` are missing.

### Usage

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/errors`
__method(s)__ | `GET`

#### Parameters

Field | Type | Default | Limitation | Description
-----:|:----:|:---------:|:----------:|:-----------
__organisation__ | string | NA | NA | The organisation that the user belongs to.
__site__ | string | First site available to the user | NA | The site that the user wants to retrieve data from.


```json
{

    "status_code": 200,
    "message":"Errors",
    "payload":[
        {
            "category":"ingestion",
            "end_timestamp":2,
            "message":"Unable to retrieve historian data.",
            "start_timestamp":1
        },
        {
            "category":"predict_handler",
            "end_timestamp":2,
            "message":"Response error from the /config endpoint",
            "start_timestamp":1
        }
    ],
    "status":"OK"
}
```

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "Errors"
__status_code__ | int | 200

The `payload` attribute associated with a successful response will be available as an array of `JSONs`, each `JSON` will
represent more information for a specific `error`.

 Attribute | Type | Value
---------:|:----:|:-----
__category__ | string | The category of the error.
__message__ | string | Message of what went wrong.
__end_timestamp__ | int or null | The UNIX-timestamp representation of when the error was resolved.
__start_timestamp__ | int | The UNIX-timestamp representation of when the error was started.

* The __end_timestamp__ attribute can be `null` which means that the error is currently unresolved, errors which are resolved will return a valid timestamp.
* Currently there are two categories of errors, they can be understood by:

 Category | Meaning 
---------:|:--------
__ingestion__ | Issues with data ingestion, this could range from network issues to historian issues.
__predict_handler__ | Issues with making predictions, this could range from network issues to poor quality data being ingested.
