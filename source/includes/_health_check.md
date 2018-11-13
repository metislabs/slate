## Health Check

Retrieves the overall current health status of `Metislabs API`.

### Usage

* The expected response for a healthy Metislabs API is listed below in the responses section.
* Any other response indicates problems with the API, please contact the relevant support email for more information.
* This endpoint is publically available.

          | Value
---------:|:-----
__endpoint__ | `https://api.metislabs.tech/1.0/health_check`
__method(s)__ | `GET`


```json
{
    "status": "OK",
    "message": "All healthy!",
    "status_code": 200,
    "payload": None
}
```

#### Response

 Attribute | Type | Value
---------:|:----:|:-----
__status__ | string | "OK"
__message__ | string | "All healthy!"
__status_code__ | int | 200
__payload__ | JSON | null
