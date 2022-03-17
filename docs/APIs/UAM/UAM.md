# Login

This API authenticates the external client with the unique credentials shared earlier as part of initial setup. This API respond back with a session token & expiry time for the session token. This token is required in header of each subsequent API triggered by partner.

## Mandatory/Optional/Conditional: Mandatory

## Event Trigger:

* External client need to initiate a Login request to fetch session token before submitting any API to Fiserv backend system.

* Each session token is active for a specific amount of time as provided in ttl (time to live) field in response.

* If external client tries to use the token beyond the expiry, Fiserv backend system will respond back with an error response.

* External client need to initiate another login request to fetch fresh token to submit any new create user request.

## Endpoint

`/boardinggateway/boarding/auth/signin`

## Payload Example

### Request Payload

```json
{
  "username": "bocmuser1",
  "password": "December01"
}
*** Get Token from above api and need to pass the same token to other apies.***
}
``` 

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/boardinggateway/boarding/auth/signin).

The below table identifies the required parameters in the request payload.

| Variable | Passed as | Type | Length | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `username` | Json property | *String* | 15 | User Id / Fiserv Lan ID. |
| `Password ` | Json Property | *string* | 15 | Password. |

### Successful Response Payload

```json
{
  "status": {
    "statusCode": 200,
    "message": "Success"
  },
  "data": {
    "token": "Wl3iTXZWZVrhoqNIiFPNwLBYe32NyTvh",
    "userName": "bocmuser1"
  }
}
```

### Error Response Payload

```json
{
  "status": {
    "statusCode": 402,
    "message": "Bad Credential"
  },
  "data": {}
}
```

Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
| `401` | Authenticatin failed.|
| `402` | Bad Credential.|
