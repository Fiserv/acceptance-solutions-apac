# Login

As part of the initial set-up, prior to integration, merchants would have received unique credentials as part of the set up process.
Login API authenticates merchants’ unique credentials, with a response that includes: -
A session token
- Expiry time of the session token
- This token is mandatory in the header submitted for each API being triggered. 


## API Category: Mandatory

## How it works

1. Merchants need to initiates a Login request to fetch a session token before submitting any APIs to Fiserv backend system.
2. Each session token is active for a specific amount of time provided in ttl (time to live) field in the response message.
3. If the merchant tries to use the token beyond the expiry, Fiserv backend system will return with an error response.
4. The merchant will then need to initiate another login request to request for a fresh token, in order to submit any creation of new user request.


## Endpoint

`/boardinggateway/boarding/auth/signin`

## Payload Examples

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

| Variable | Passed as | Type | Length | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
| `username` | Json Property | *string* | 15 | User ID |
| `Password ` | Json Property | *string* | 15 | Password |

### Successful Response in Payload

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

### Error Response in Payload

```json
{
  "status": {
    "statusCode": 402,
    "message": "Bad Credential"
  },
  "data": {}
}
```

The table below provides the list of error codes and description for this application.

| Error Code |  Description / Values |
| --------  | ------------------ |
| `401` | Authenticatin failed |
| `402` | Bad Credential |
|`200`| Token not found |   
|`403`| Forbidden |
|`404`|  Not found |  
|`400`| Generic Error |
