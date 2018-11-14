## Authentication

Authentication is a two stage process, first we retrieve an access token from
the authentication server and then use that access token to make requests from
the API.

Your organisation should have been supplied with a client ID and a client
secret, if you don't have these please contact Metis Labs support.

To get an access token we make a POST request to
`https://auth0.metislabs.tech/oauth/token` containing
JSON formatted data, with the following keys and values:

```json
{
    "grant_type": "client_credentials",
    "client_id": "YOUR_CLIENT_ID",
    "client_secret": "YOUR_CLIENT_SECRET",
    "audience": "https://api.metislabs.tech"
}
```

```shell
curl --request POST \
  --url 'https://auth0.metislabs.tech/oauth/token' \
  --header 'content-type: application/json' \
  --data '{"grant_type": "client_credentials",
           "client_id": "YOUR_CLIENT_ID",
           "client_secret": "YOUR_CLIENT_SECRET",
           "audience": "https://api.metislabs.tech"}'
```

Key       | Value
---------:|:-----
__grant_type__    | "client\_credentials"
__client_id__     | "YOUR\_CLIENT\_ID"
__client_secret__ | "YOUR\_CLIENT\_SECRET"
__audience__      | "https://api.metislabs.tech"

This will return an access token, which can then be used to make API requests.

```shell
curl --request GET \
  --url https://api.metislabs.tech/1.0/forecast_processes \
  --header 'Authorization: Bearer YOUR_ACCESS_TOKEN'
```

When making calls to the Metis Labs API the access token should be provided
via an `Authorization` header containing `Bearer` followed by
`YOUR_ACCESS_TOKEN`.
