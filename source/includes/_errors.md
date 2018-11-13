## Errors

* The Metislabs API returns the following error codes. All of the errors are returned in the standard format mentioned [here](#response-format). 
* All of the responses will return a `payload` attribute of `nil`.
* In the `message` attribute, there is a more verbose message detailing the situation and what went wrong.

```json
{
    "status": "page-not-found",
    "message": "<404 Page Not Found>: Your request did not contain the correct URL or format, please try again.", 
    "payload": None
}
```

### Client based errors

* Client based errors usually result from incorrect data input, wrong resources specified or unauthenticated access, if any of these occur, please check again how the resources are being accessed or used.

Status | Status Code | Meaning
---------------: | :-----------: | :--------
__url-parameter-error__ | 400 | The parameters supplied to the URL are incorrect or of a bad format.
__authentication-required__ | 401 | Authentication is required to access resources at the endpoint.
__permission-denied__ | 403 | The permissions level associated with the request was not sufficient to use the endpoint.
__page-not-found__ | 404 | The URL used in the request does not exist on the API.
__method-not-allowed__ | 405 | The HTTP method supplied in the request is not permitted on the endpoint.

### Server based errors

* Server based errors result from errors or bugs in the API, if any of these occur, please do not hesistate to contact the customer support email with appropriate details to replicate the issue.

Status | Status Code | Meaning
---------------: | :-----------: | :--------
__internal-server-error__ | 500 | A generic error in the server.
__customer-not-found__ | 500 | The specified customer was not found, please contact customer support.
__forecast-not-found__ | 500 | The specified forecast was not found, please contact customer support.
__subsystem-breakdown-not-found__ | 500 | The specified subsystem breakdown was not found, please contact customer support.
